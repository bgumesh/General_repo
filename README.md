const express = require('express')
const cors = require('cors')
const app = express()
const port = 5000
app.use(express.json())
app.use(cors())
const mongodb = require('mongodb')
const MongoClient = mongodb.MongoClient
const connectionURL = 'mongodb://127.0.0.1:27017'
const databaseName = 'Students'


app.post('/insert', (req, res) => {
    MongoClient.connect(connectionURL, { useNewUrlParser: true }, (error, client) => {
        if (error) {
            return console.log('Unable to connect to database!')
        }
        const db = client.db(databaseName)
        db.collection('studentDetails').insertOne({
            s_name:req.body.s_name,
            s_class:req.body.s_class,
            total_marks:req.body.total_marks
        })
    })
    
    const posted=[{posted:'Yes'}];
    res.send(posted);
    res.redirect('/display');
});


app.get('/display', (req, res) => {
    MongoClient.connect(connectionURL, { useNewUrlParser: true }, (error, client) => {
        if (error) {
            return console.log('Unable to connect to database!')
        }
      const db = client.db(databaseName)
      db.collection('studentDetails').find().toArray(function(err, results) {
        console.log(results)
        res.send(results)
          })
    })
});


app.post('/delete', (req, res) => {
    console.log(req.body.student_to_delete)
    MongoClient.connect(connectionURL, { useNewUrlParser: true }, (error, client) => {
        if (error) {
            return console.log('Unable to connect to database!')
        }
        const db = client.db(databaseName)
        const myquery = { s_name:req.body.student_to_delete};
        db.collection('studentDetails').deleteOne(myquery,function(err, res) {
            if (err) throw err;
            console.log("student details deleted!");
          });
        
    })
    const posted=[{posted:'Yes'}];
    res.send(posted);
});



app.post('/update', (req, res) => {
    console.log(req.body.student_to_update)
    console.log(req.body.new_class)
    console.log(req.body.new_total_marks)
    MongoClient.connect(connectionURL, { useNewUrlParser: true }, (error, client) => {
        if (error) {
            return console.log('Unable to connect to database!')
        }
        const db = client.db(databaseName)
        const myquery = { s_name:req.body.student_to_update};
        const newvalues = { $set: {
            s_class:req.body.new_class,
            total_marks:req.body.new_total_marks
        } };
        db.collection('studentDetails').updateOne(myquery, newvalues, function(err, res) {
            if (err) throw err;
            console.log("student details updated");
          });
        
    })
    const posted=[{posted:'Yes'}];
    res.send(posted);
});

//search student with marks
app.post('/search', (req, res) => {
    MongoClient.connect(connectionURL, { useNewUrlParser: true }, (error, client) => {
        if (error) {
            return console.log('Unable to connect to database!')
        }
      const db = client.db(databaseName)
      db.collection('studentDetails').find().toArray(function(err, results) {
        console.log(results)
        res.send(results)
          })
    })
});

app.listen(port, () => console.log(`App listening on port ${port}!`))
////////////////////////////////server.js/////////////////////
import React, { Component } from "react";
import axios from "axios";

class Create extends Component {
  state = {
    s_name:"",
    s_class:"",
    total_marks:null
  };

  OnChange=e=>{
    this.setState({
        [e.target.name]:e.target.value
    })
  }
  
  handleSubmit = e => {
    e.preventDefault();
    const data = {
        s_name:this.state.s_name,
        s_class:this.state.s_class,
        total_marks:this.state.total_marks
    };
    axios
      .post("http://127.0.0.1:5000/Create", data)
      .then(res => console.log(res))
      .catch(err => console.log(err));
  };
 
 render() {
    return (
      <div>
        <form  onSubmit={this.handleSubmit}>
         <label>Student Name</label>
          <input
            type="text"  name="s_name" value={this.state.s_name} onChange={this.OnChange}
            required
          />
            <br/>
            <label>Class</label>
          <input
             type="text"  name="s_class" value={this.state.s_class} onChange={this.OnChange}
            required
          />
          <br/>
           <label>Total marks</label>
          <input
             type="number"  name="total_marks" value={this.state.total_marks} onChange={this.OnChange}
            required
          />
         <br/>
          <button type="submit">submit</button>
        </form>
      </div>
    );
  }
}


export default Create;
/////////////////////////////create.jsx////////////////////////////
  import React from 'react'
import axios from 'axios'
class Display extends React.Component{
constructor(props){
    super(props);
    this.state={Data: []}
}
componentDidMount(){
    axios.get('http://127.0.0.1:5000/display')
    .then((res)=>{
        const list = res.data;
        this.setState({ Data: list})
    });
}
render()
{
    return(
        <table border="1px">
            <tr>
                <th>Name</th><th>Class</th><th>Total Marks</th>
            </tr>
            {this.state.Data.map((i) => {
                return (
                    <tr key={i._id}>
                        <td>{i.s_name}</td>
                        <td>{i.s_class}</td>
                        <td>{i.total_marks}</td>
                    </tr>
                )
            })}
        </table>    )
}}
export default Display
///////////////////////////Display.jsx////////////////////////////////
import React, { Component } from "react";
import axios from "axios";

class Update extends Component {
  state = {
    student_to_update:"",
    new_class:"",
    new_total_marks:null
  };

  OnChange=e=>{
    this.setState({
        [e.target.name]:e.target.value
    })
  }
  handleSubmit = e => {
    e.preventDefault();
    const data = {
        student_to_update:this.state.student_to_update,
        new_class:this.state.new_class,
        new_total_marks:this.state.new_total_marks
    };
    axios
      .post("http://127.0.0.1:5000/update", data)
      .then(res => console.log(res))
      .catch(err => console.log(err));
  };
 
 render() {
    return (
      <div>
        <form  onSubmit={this.handleSubmit}>
         <label>Enter Name</label>
          <input
             type="text"  name="student_to_update" value={this.state.student_to_update} onChange={this.OnChange}
            required
          />
          <br/>
          <label>Enter class </label>
          <input
         type="text"  name="new_class" value={this.state.new_class} onChange={this.OnChange}
            required
          />
          <br/>
          <label>Enter total marks</label>
          <input
             type="number"  name="new_total_marks" value={this.state.new_total_marks} onChange={this.OnChange}
            required
          />
         <br/>
          <button type="submit">Update</button>
        </form>
      </div>
    );
  }
}


export default Update
///////////////////////////update.jsx///////////////////////
import React from 'react'
import axios from 'axios'

class DeleteCourse extends React.Component{
    state={
        student_to_delete:""
    }
    onDelete=e=>{
        this.setState(
            {student_to_delete:e.target.value}
        )
    }
    
    handleSubmit=e=>{
        e.preventDefault();
        const data={
            student_to_delete:this.state.student_to_delete
        }
        axios.post("http://127.0.0.1:5000/delete",data)
        .then(res=>console.log(res))
        .catch(err=>console.log(err))
    }

    render(){
        return(
            <form onSubmit={this.handleSubmit}>
                <label>Enter Name: </label>
                <input
                    type='text'
                    value={this.state.student_to_delete}
                    onChange={this.onDelete}
                    required
                />
                <button type='submit'>Delete</button>
            </form>
        )
    }
}

export default DeleteCourse;
//////////////////////////////delete.jsx////////////////////////////////
import React from 'react'
import { NavLink } from 'react-router-dom'
const Navbar = () =>{
    return(
<nav >
    <div >
<ul className="right">
            <li><NavLink to="/insert">Insert</NavLink></li>
            <li><NavLink to="/display">Display</NavLink></li>
            <li><NavLink to="/delete">Delete</NavLink></li>
            <li><NavLink to="/update">Update</NavLink></li>
       </ul>
    </div>
</nav>    )
}


export default Navbar
//////////////////navbar.jsx/////////////////////
import React from 'react';
import { BrowserRouter, Routes, Route } from 'react-router-dom'
import './App.css';

import Navbar from './component/ISA2/navbar';
import Create from './component/ISA2/Insertion';
import Display from './component/ISA2/Selection';
import DeleteCourse from './component/ISA2/deletion';
import Update from './component/ISA2/Updation';


function App() {
  return (
    <BrowserRouter>
    <div>
      <Navbar />
      <Routes>
        <Route exact path="/insert" element={<Create/>} />
        <Route exact path="/display" element={<Display/>} />
        <Route exact path="/delete" element={<DeleteCourse/>} />
        <Route exact path="/update" element={<Update/>} />
      </Routes>
    </div>
    </BrowserRouter>
  );
}


export default App;
/////////////////app.jsx////////////////////////
