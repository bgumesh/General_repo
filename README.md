/////////////////DBHelper///////////////////////////////
package com.example.db1;

import android.content.ContentValues;
import android.content.Context;
import android.database.Cursor;
import android.database.sqlite.SQLiteDatabase;
import android.database.sqlite.SQLiteOpenHelper;

import androidx.annotation.Nullable;

public class DBhelper extends SQLiteOpenHelper {
    public static final String dbname = "MyDATABASE";
    public DBhelper(Context context) {
        super(context, dbname, null, 1);
    }

    @Override
    public void onCreate(SQLiteDatabase db) {

        db.execSQL("create Table userdata(name Text primary key, age Text )");

    }

    @Override
    public void onUpgrade(SQLiteDatabase db, int oldVersion, int newVersion) {
        db.execSQL("drop Table if exists userdata");
    }

    public  Boolean insertUser(String name, String age){
        SQLiteDatabase db=getWritableDatabase();

        ContentValues con= new ContentValues();
        con.put("name",name);
        con.put("age",age);
        long res=db.insert("userdata",null,con);
        if(res==-1){
            return false;
        }
        else{
            return true;
        }


    }

    public  Boolean updateUser(String name, String age){
        SQLiteDatabase db=getWritableDatabase();

        ContentValues con= new ContentValues();
        con.put("age",age);
        Cursor cur=db.rawQuery("Select * from userdata where name=?",new String[]{name});
        if(cur.getCount()>0){
            long result= db.update("userdata",con,"name=?",new String[]{name});
            if(result==-1){
                return false;
            }
            else{
                return true;
            }
        }
        else{
            return false;
        }
    }

    public  Boolean deleteUser(String name){
        SQLiteDatabase db=getWritableDatabase();

        ContentValues con= new ContentValues();
        Cursor cur=db.rawQuery("Select * from userdata where name=?",new String[]{name});
        if(cur.getCount()>0){
            long result= db.delete("userdata","name=?",new String[]{name});
            if(result==-1){
                return false;
            }
            else{
                return true;
            }
        }
        else{
            return false;
        }
    }

    public Cursor Display(){
        SQLiteDatabase DB=getWritableDatabase();

        Cursor cur=DB.rawQuery("Select * from userdata",null);
        return cur;
    }

}


/////////////////////////////////MainActivity.java//////////////////////////////////////////
package com.example.db1;

import androidx.appcompat.app.AppCompatActivity;

import android.database.Cursor;
import android.os.Bundle;
import android.view.View;
import android.widget.Button;
import android.widget.EditText;
import android.widget.Toast;

public class MainActivity extends AppCompatActivity {

    EditText name,age;
    Button insert,update,delete,view;

    DBhelper Db;

    @Override
    protected void onCreate(Bundle savedInstanceState) {
        super.onCreate(savedInstanceState);
        setContentView(R.layout.activity_main);

        name= findViewById(R.id.name);
        age= findViewById(R.id.age);


        insert= findViewById(R.id.btnInsert);
        update= findViewById(R.id.btnUpdate);
        delete= findViewById(R.id.btnDelete);
        view= findViewById(R.id.btnView);

        Db= new DBhelper(this);

        insert.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {

                String nameText= name.getText().toString();
                String ageText=age.getText().toString();

                Boolean check=Db.insertUser(nameText,ageText);
                if(check){
                    Toast.makeText(MainActivity.this, "inserted", Toast.LENGTH_SHORT).show();
                }
                else{
                    Toast.makeText(MainActivity.this, "no inserted", Toast.LENGTH_SHORT).show();
                }


            }
        });

        update.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String nameText= name.getText().toString();
                String ageText=age.getText().toString();
                Boolean check=Db.updateUser(nameText,ageText);
                if(check){
                    Toast.makeText(MainActivity.this, "updated", Toast.LENGTH_SHORT).show();
                }
                else{
                    Toast.makeText(MainActivity.this, "no updated", Toast.LENGTH_SHORT).show();
                }


            }
        });

        delete.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                String nameText= name.getText().toString();

                Boolean check=Db.deleteUser(nameText);
                if(check){
                    Toast.makeText(MainActivity.this, "deleted", Toast.LENGTH_SHORT).show();
                }
                else{
                    Toast.makeText(MainActivity.this, "no delete", Toast.LENGTH_SHORT).show();
                }


            }
        });

        view.setOnClickListener(new View.OnClickListener() {
            @Override
            public void onClick(View v) {
                Cursor cur=Db.Display();

                if(cur.getCount()>0){
                    StringBuffer buffer = new StringBuffer();
                    while(cur.moveToNext()){
                        buffer.append(cur.getString(0)+"\n");
                        buffer.append(cur.getString(1)+"\n");

                    }
                    Toast.makeText(MainActivity.this, buffer.toString(), Toast.LENGTH_SHORT).show();
                }
                else{
                    Toast.makeText(MainActivity.this, "no display", Toast.LENGTH_SHORT).show();
                }


            }
        });




    }

}


/////////////////////xml file////////////////////////////////

<?xml version="1.0" encoding="utf-8"?>
<RelativeLayout xmlns:android="http://schemas.android.com/apk/res/android"
    xmlns:app="http://schemas.android.com/apk/res-auto"
    xmlns:tools="http://schemas.android.com/tools"
    android:layout_width="match_parent"
    android:layout_height="match_parent"
    android:padding="10dp"
    tools:context=".MainActivity">

    <TextView
        android:id="@+id/texttitle"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:text="Please enter the details below"
        android:textSize="24dp"/>
    <EditText
        android:id="@+id/name"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Name"
        android:textSize="24dp"
        android:layout_below="@+id/texttitle"
        android:inputType="textPersonName"
        />



    <EditText
        android:id="@+id/age"
        android:layout_width="match_parent"
        android:layout_height="wrap_content"
        android:hint="Date of birth"
        android:textSize="24dp"
        android:layout_below="@+id/name"
        android:inputType="number"
        />

    <Button
        android:id="@+id/btnInsert"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24dp"
        android:text="Insert"

        android:layout_below="@+id/age"/>
    <Button
        android:id="@+id/btnUpdate"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24dp"
        android:text="Update"

        android:layout_below="@+id/btnInsert"/>
    <Button
        android:id="@+id/btnDelete"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24dp"
        android:text="Delete"

        android:layout_below="@+id/btnUpdate"/>
    <Button
        android:id="@+id/btnView"
        android:layout_width="wrap_content"
        android:layout_height="wrap_content"
        android:textSize="24dp"
        android:text="Display"

        android:layout_below="@+id/btnDelete"/>

</RelativeLayout>


