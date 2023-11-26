#this is my second repo
Git commonds
•	git: for check git is present in desktop<br>
•	git --verson: to check git version<br>
•	sudo apt update : for to update git<br>
•	sudo apt install git : for installation of git<br>
•	a.Broken installition (for checking for broken things)<br>
	i. sudo apt --fix-broken install<br>
	b.Success<br>
		i. git --version (for checking version)<br>
•	Initalize the setting locally(configure username and email)<br>
	a. git config --global user.name naik-amar(username which is used in<br> 		git hub website)<br>
	b. git config --global user.email amar.naik@gcssanquelim.ac.in<br>
	amar.naik@gcssanquelim.ac.in(register email id on git hub)<br>
	c. to see global config<br>
	: git  config --list(for checking the list of username and email list)<br>
•	integrate local environment with Github<br>
•	we push from local repository  and  we pull from remote repository<br>
•	Login to your git hub account<br>
A.	login to your git hub account<br>
B.	create repo<br>
C.	In Ubuntu create a directory(workplace)<br>
D.	Execute git clone commond<br>
	git clone https://github.com/naik-amar/firstrepo.git<br>
Navigate to repo locally in Ubuntu<br>
	a. cd reponame<br>
create a  python code file<br>
	touch first.py<br>
git status(untracked file)(run next commond to add)(it shows in which dect. You are)<br>
git add first.py,two.py(python file)(this will added in the stagging area)<br>
a.	git status<br>
a.	git commit  –m  “first.py python file committed”(from stagging area file comitted to local repository)<br>
b.	git commit first.py  –m  “first.py python file committed” (in case file not staged  directly commited in local repo).<br>
push local changes to remote repo<br>
a.	git push origin master(this generate error)<br>
b.	second methods<br>
profile>setting>developer setting>git hub apps>token>generate classic token>note(give reason for push)>use for 1 day>select all<br> permisssion>click on generate token>copy it andsave it samewhere><br>
set url with the help of url<br>
c.	git remote set-url origin https://(token paste here)@github.com/username/(repository name on gitweb)<br>
d.	git push origin main(to push from local to remote repo)<br>
Branching And Merging<br>
-git branch feature<br>
-git branch –a<br>
-git checkout feature<br>
 git status<br>
git checkout main(main branch open and we are in main branch)<br>
now merge using<br>
git merge feature<br>
in main branch open and add some things and commit<br>
to delete feature branch<br>
git branch  -d (branch name to delete)<br>
fork commond= to get access to other repository<br>
current branch(master branch)<br>
target branch(local branch)<br>
Umesh@123_321
/////////////////////////////////////////////////////////
10.	Generating java doc<br>
Step 1: Select your project and click on project on menu bar and select Generate<br> 
Step 2: Click on project name and give destination path for saving javadoc and click finish<br>
//////////////////////////////////////////<br>
Selenium Code:<br>
package selenium;<br>

import org.openqa.selenium.By;<br>
import org.openqa.selenium.WebDriver;<br>
import org.openqa.selenium.chrome.ChromeDriver;<br>

public class WebsiteLogin {<br>

	public static void main(String[] args) throws Throwable{<br>
		// TODO Auto-generated method stub<br>
		System.setProperty("Webdriver.chrome.driver", "C:\\Users\\Abhishek\\Documents\\study material\\TYBSC\\Software enginering\\Selenium Project\\chromedriver-win64\\chromedriver.exe");<br>
		WebDriver driver = new ChromeDriver();<br>
		driver.get("https://www.saucedemo.com/");<br>
		driver.manage().window().maximize();<br>
		driver.findElement(By.id("user-name")).sendKeys("standard_user");<br>
		Thread.sleep(1000);<br>
		driver.findElement(By.id("password")).sendKeys("secret_sauce");<br>
		Thread.sleep(1000);<br>
		driver.findElement(By.id("login-button")).click();<br>
	}
}
////////////////////
Step1: Click on file menu and select project<br> 
Step2: Right click on project and create class (e.g., circle)<br> 
Step3: Declare a data member (e.g., float radius) <br>
Step4: Right click on class i.e., circle ->go to source->click on generate getters and setters<br>
Step5: Create a function i.e., area (implement the function) <br>
Circle Class:<br>
package junit;<br>

public class Circle {<br>
	public float radius;<br>

	public float getRadius() {<br>
		return radius;<br>
	}<br>

	public void setRadius(float radius) {<br>
		this.radius = radius;<br>
	}<br>
	
	public float area() {<br>
		 return (float)(3.14 * this.radius * this.radius);<br>
	}
}
Step6: Right click on package ->click new->click on Junit<br> 
Step7: Write the class name for Junit testcase and browse the class i.e., circle<br>
Step8. Click next button right down the window <br>
Step9. Select all the methods on which you want write the testcase i.e. setradius() and area()<br> 
Step10: Create instance of class which function are to be tested<br>
Circle Testcase class:<br>
package junit;<br>

import org.junit.jupiter.api.Test;<br>
import junit.framework.TestCase;<br>

class CircleTestCase extends TestCase{<br>

	@Test<br>
	void testSetRadius() {<br>
		Circle circle = new Circle();<br>
		circle.setRadius(2.0f);<br>
		assertEquals(12.56f,circle.area());<br>
	}
}

Step 11: Run testcase class i.e. Right click on testcase class and click on Run as ->Junit<br>
 
To run one or more testcases together we create suite:<br>
Right click on package-> new-> other-> Java-> Junit-> Junit Suite  Browse the package name in which classes are created  Select all the testcase classes need to be run -> Click Finish<br> 
To execute: Right Click on suite class (All Test) -> Run it as Junit<br>

 //////////////////////
Requirements:
•	Sign Up
•	Login
•	Buying of products
•	Cancellation of products
•	Payments
•	Wishlist
•	Add to cart
•	Searching
•	Tracking of products
•	Profile changing
Sign Up<br>
User Story:<br>
As a person<br>
I want to sign up i.e., create my account<br>
so that I have an account<br>

Acceptance Criteria:<br>
Given a person<br>
When I Click on sign up button and fill the required detail<br>
Then my account is created<br>

Login<br>
User Story:<br>
As a user<br>
I want to login in my account<br>
so that I can access my account<br>

Acceptance Criteria:<br>
Given a login button<br>
When I click on login button and fill the correct details<br>
Then I should be able to access my account<br>

Buying Of Products<br>
User story:
As a user
I want to buy a product
So that I can have it

Acceptance Criteria:<br>
Given a user who wants to buy products
When I click on buy now button
Then I should be able to have that product

Cancellation of Products<br>
User story:
As a user
I want to cancel a product
So that I don’t want that product

Acceptance Criteria:<br>
Given a user who wants to cancel the product
When I click on cancel product button
Then I should be able to cancel the buying product

Payment<br>
User Story:
As a user
I want to pay for my product
So that I can purchase that product

Acceptance Criteria:<br>
Given a payment button
When I click on payment button 
Then I should be able to purchase the product

Wishlist<br>
User story:
As a user 
I want to buy the product later
So that I can Wishlist that product

Acceptance Criteria:<br>
Given a Wishlist button
When I want to buy a product later so that I click on Wishlist button
Then I should be able to Wishlist that product

Add to cart<br>
User Story:
As a user
I want to have a cart
So that I can buy multiple products at once

Acceptance Criteria:<br>
Given a add to cart button
When I want buy multiple products
Then I should have a Wishlist

Searching<br>
User story:
As a user
I want to search the products
So that I can see desired product

Acceptance Criteria:<br>
Given a search bar
When I click on search button
Then I should be able to see desired product
 
Tracking of products<br>
User story:
As a user
I want to track the products
So that I can see the time for delivery

Acceptance Criteria:<br>
Given a user who wants to track his product
When I click on track product button
Then I should be able to see time for delivery
 
Profile changing<br>
User story:
As a user
I want to change my profile
So that I update details

Acceptance Criteria:<br>
Given a profile button
When I click on change profile button
Then I should be able to update the details
////////<br>
online commonds<br>
setting git locally on machine<br>
1  git congif -- global user.name("bgumesh")<br>
2 git config -- global user.email("umeshgadad6@gmail.com")<br>
3 git config --list<br>
clone:cloning the repository on our local machine<br>
1 git clone (link of remote repository)<br>
status: display the state of the code<br>
1 git status<br>
 new file or changed file (add and stagged)<br>
1 git add (file name) or git add . <br>
2 git commit -m "some message" <br>
push(from local to remote push file changes)<br>
1 git push origin main(othersied it)<br>
make new dictory<br>
1 mkdir name(localrepo)<br>
 to make this git repo use(go on that repo and run following comond)<br>
	git init <br>
after adding new files in it and add and push commit do following steps<br>
create new repo on github(keep same name)<br>
	from that local repo run folling commond<br>
	git removte add origin (link of that new repo)<br>
	git removte -v(to check it is right or not)<br>
	git branch(to check in which branch we are in currently<br>
	git branch -M main(to change branch name to other name(master to main))<br>
	git push origin main(to push all changes of localrepo to github)<br>
Branch commonds<br>
	1 git branch(to ckech in which branch we are in)<br>
	2 git branch -M main(to rename the branch<br>
	3 git checkout (branch name) (to navigate/move from one branch to other)<br> 
	4 git checkout -b(new branch name) (to create new branch)<br>
	5 git branch -d (branch name) (to delete branch)<br>
merge commonds<br>
	1 git diff (branch name)(to know diff one branch in another branch)<br>
	2 git merge (branch name)(to merge to branches)<br>
	second way<br>
	create PR(pull request which tell other that we made changes to the main branch)<br>
now to bring those remote changes to local machine run following commond<br>
	1 git pull origin main<br>
 merge conflict<br>
	in both main and feature1 change the code same<br>
	and add and commit them<br>
	now merge commit(solve mannually)<br>
	1 git merge (branch name)<br>
	then<br>
	git add and merge  and commit<br>
	then push them on origin main<br>
undoing changes<br>
	stagged changes(means move back from stagging area)<br>
	1 git reset (file name)<br>
	or<br>
	2 git reset(to all files moves back)<br>
commited changes to uncommit them<br>
	1 git reset HEAD~1(usethis commond)(it moves back from one previous commit)<br>
git log(to check all commit)<br>
to jump whichever previous commit we madethen usefollowing steps<br>
	1 git reset(copy hash)(by git log you will get hash code copy and paste)<br>
to remove all other changes after jumping many steps back then <br>
	1 git reset --hrad (hash code)<br>
fork means exeect copy of the repo<br>
step>>select any project>>fork>.save in ypur repo>>done<br>
/////////////////////////////////////////////////junit tastcase/////////////////
package network;<br>

public class circle {<br>
	private float radius;<br>

	public float getRadius() {<br>
		return radius;<br>
	}<br>

	public void setRadius(float radius) {<br>
		this.radius = radius;<br>
	}<br>
	public void area()<br>
	{<br>
		System.out.println("Area of circle is: " + 3.14*this.radius*this.radius);<br>
		}<br>

}<br>


package network;<br>

import static org.junit.jupiter.api.Assertions.*;<br>


import org.junit.jupiter.api.AfterEach;<br>
import org.junit.jupiter.api.BeforeEach;<br>
import org.junit.jupiter.api.Test;<br>

class networktestcase {<br>

	@BeforeEach<br>
	/*void setUp() throws Exception {<br>
	}<br>

	@AfterEach<br>
	void tearDown() throws Exception {<br>
	}*<br>

	@Test
	void test() {<br>
//		fail("Not yet implemented");<br> 
		circle c = new circle();<br>
		c.setRadius(6);<br>
		c.area();<br>
	}<br>

}


/////////////////////////////////////////CN//////////////////////////////////////////
Write a C Program to simulate Character Stuffing with<br>
CharacterFlag Bytes {Let us assume capital ‘A’ is used as<br>
flagbyte}<br>
//character stuffing<br>
#include<stdio.h><br>
#include<string.h><br>
void main() {<br>
char x[20],y[20];<br>
int i=0,j=0;<br>
printf("Enter the string:");<br>
scanf("%s",x);<br>
y[j]='A';<br>
for (i=0,j=1;x[i]!='\0';i++,j++) {<br>
y[j]=x[i];<br>
if (x[i]=='A') {<br>
j++;<br>
y[j]='A';<br>
}<br>
}<br>
j+1;<br>
y[j]='A';<br>
printf("The Character Stuffed String:%s",y);<br>
}<br>
2) Write a c Program to simulate Character Destuffing with<br>
Character Flag Bytes {Let us assume capital ‘A’ is used as<br>
flagbyte}<br>
//CHARACTER DESTUFFING<br>
#include<stdio.h><br>
#include<string.h><br>
void main() {<br>
char x[20],y[20];<br>
int i=0,j=0;<br>
printf("Enter the string:");<br>
scanf("%s",x);<br>
for(i=1;x[i+1]!='\0';i++,j++)<br>
{<br>
y[j]=x[i];<br>
if (x[i]=='A')<br>

{<br>
i++;<br>
}<br>
}<br>
printf("\nThe destuffed string:%s",y);<br>
}<br>
3) Write a c Program to simulate Character Stuffing and<br>
Destuffing with Character Flag Bytes {Let us assume capital<br>
‘A’ is used as flagbyte}<br>
//character stuffing and Destuffing<br>
#include<stdio.h><br>
#include<string.h><br>
void main() {<br>
char x[20],y[20],z[20];<br>
int i=0,j=0,k=0;<br>
printf("Enter the string:");<br>
scanf("%s",x);<br>
y[j]='A';<br>
for (i=0,j=1;x[i]!='\0';i++,j++) {<br>
y[j]=x[i];<br>
if (x[i]=='A') {<br>
j++;<br>
y[j]='A';<br>
}<br>
}<br>
j+1;<br>
y[j]='A';<br>
printf("The Character Stuffed String:%s",y);<br>
//character destuffing<br>
for(j=1;y[j+1]!='\0';j++,k++)<br>
{<br>
z[k]=y[j];<br>
if (y[j]=='A')<br>
{<br>
j++;<br>
}<br>
}<br>
printf("\nThe destuffed string:%s",z);<br>
}<br>

4) Write a C program to simulate bit stuffing method of
framing techniques.<br>
//program to simulate BIT STUFFING<br>
#include<stdio.h><br>
void main()<br>
{<br>
char a[100],b[100];<br>
int i=0,j=0,c=0;<br>
printf("Enter the data:\n");<br>
scanf("%s",a);<br>
b[0]='0';<br>
b[1]='1';<br>
b[2]='1';<br>
b[3]='1';<br>
b[4]='1';<br>
b[5]='1';<br>
b[6]='1';<br>
b[7]='0';<br>
for (i=0,j=8;a[i]!='\0';i++,j++)<br>
{<br>
if (a[i]=='1')<br>
c++;<br><br>
else<br>
c=0;<br>
b[j]=a[i];<br>
if(c==5)<br>
{<br>
b[++j]='0';<br>
c=0;<br>
}<br>
}<br>
b[j++]='0';<br>
b[j++]='1';<br>
b[j++]='1';<br>
b[j++]='1';<br>
b[j++]='1';<br>
b[j++]='1';<br>
b[j++]='1';<br>
b[j++]='0';<br>
printf("The array after bit stuffing:%s",b);<br>
}<br>
5) Write a C program to simulate bit de-stuffing method of<br>
framing techniques.<br>
//bit destuffing<br>
#include<stdio.h><br>
void main()<br>
{<br>
char b[100],c[100];<br>
int j=0,k=0,d=0,cc=0;<br>
printf("Enter the data:\n");<br>
scanf("%s",b);<br>
while(b[j]!='\0')<br>
{<br>
d++; //count<br>
j++;<br>
}<br>
for(j=8,k=0;j<d-8;j++,k++)<br>
{<br>
if (b[j]=='1')<br>
cc++;<br>
else<br>
cc=0;<br>
c[k]=b[j];<br>
if(cc==5)<br>
{<br>
j++;<br>
cc=0;<br>
}<br>
}<br>
c[k]='\0';<br>
printf("The count:%d",d);<br>
printf("\nThe array after destuffing:%s",c);<br>
}<br>
6) Write a C program to stimulate the IP address fragmentation<br>
#include<stdio.h><br>
void main()<br>
{<br>
int dsize, mtusize, psize, ndsize,oset, flag=1, mf=1,i;<br>
char ident='X';<br>
FILE *f;<br>
f=fopen("out.txt","wt");<br>
printf("Enter the size of the date:");<br>
scanf("%d",&dsize);<br>
while(flag==1)<br>
{<br>
printf("Enter the maximum transfer unit size:");<br>
scanf("%d",&mtusize);<br>
if((mtusize-20)%8==0)<br>
flag=0;<br>
}<br>
oset=0;<br>
psize=mtusize-20;<br>
for(i=1;oset<dsize;i++)<br>
{<br>
fprintf(f,"%d %c %d %d %d\n",i,ident,mf,oset,psize);<br>
oset=oset+psize;<br>
}<br>
if(oset>=dsize)<br>
{<br>
mf=0;<br>
oset=oset-psize;<br>
ndsize=dsize-oset;<br>
if(dsize==oset)<br>
ndsize=psize;<br>
fprintf(f,"%d %c %d %d<br>
%d\n",i,ident,mf,dsize,ndsize);<br>
fclose(f);<br>
}<br>
}<br>
7) Write a C program to stimulate IP address reassembling.<br>
#include<stdio.h><br>
#include<stdlib.h><br>
#include<conio.h><br>
void main()<br>
{<br>
int a[30], c[30], d[30], e[30], i, l, nol=0, fin;<br>
char b[30], line[80];<br>
FILE *file;<br>
file = fopen("out.txt","r");<br>
while(fgets(line,80,file)!=NULL)<br>
nol++;<br>
fclose(file);<br>
file = fopen("out.txt","r");<br>
while(!feof(file))<br>
{<br>
for(i=0;i<nol;i++)<br>
{<br>
fscanf(file,"%d %c %d %d %d", &a[i], &b[i], &c[i],<br>
&d[i], &e[i]);<br>
}<br>
}<br>
for(i=0;i<nol;i++)<br>
printf("\n%d%c%d%d%d", a[i], b[i], c[i], d[i], e[i]);<br>
for(i=0;i<nol;i++)<br>
{<br>
if(a[i]!=i+1)<br>
{<br>
printf("Error in a column");<br>
exit(1);<br>
}<br>
}<br>
for(i=0;i<nol-1;i++)<br>
{<br>
if(b[i]!=b[i+1])<br>
{<br>
printf("Error in b column");<br>
exit(1);<br>
}<br>
}<br>
for(i=0;i<nol-1;i++)<br>
{<br>
if(c[i]!=1||(c[nol-1]!=0))<br>
{<br>
printf("Error in c column");<br>
exit(1);<br>
}<br>
}<br>
for(i=0;i<nol-2;i++)<br>
{<br>
if(e[i]!=e[i+1])<br>
{<br>
printf("Error in e column");<br>
exit(1);<br>
}<br>
}<br>
fin=0;<br>
for(i=1;i<nol;i++)<br>
{<br>
if(d[i]!=fin+e[i])<br>
{<br>
printf("Error in d column");<br>
exit(1);<br>
}<br>
else<br>
{<br>
fin=d[i];<br>
}<br>
}<br>
printf("n Packet reassembled\n");<br>
printf("Size of packet=%d",d[nol-1]);<br>
fclose(file);<br>
//return 0;<br>
}<br>
8) Write a C program to Implement the Dijkstra's Algorithm.<br>
//implementation of Dijkstra's shortest path algorithm<br>
#include<stdio.h><br>
#include<string.h><br>
#define IN 99<br>
#define N 4<br>
int dijkstra(int cost[][N],int source,int target)<br>
{<br>
int dist[N],prev[N],selected[N]={0},i,m,min,start,d,j;<br>
char path[N];<br>
for(i=0;i<N;i++){<br>
dist[i]=IN;<br>
prev[i]=-1;<br>
}<br>
start = source;<br>
selected[start]=1;<br>
dist[start]=0;<br>
while(selected[target]==0){<br>
min=IN;<br>
m=0;<br>
for(i=0;i<N;i++){<br>
d=dist[start]+cost[start][i];<br>
if((d<dist[i]) && (selected[i]==0)){<br>
dist[i]=d;<br>
prev[i]=start;<br>
}<br>
if((min>dist[i]) && (selected[i]==0)){<br>
min=dist[i];<br>
m=i;<br>
}<br>
}<br>
start = m;<br>
selected[start] = 1;<br>
}<br>
start=target;<br>
j=0;<br>
while(start != -1){<br>
path[j++] = start+65;<br>
start=prev[start];<br>
}v
path[j]='\0';<br>
strrev(path);<br>
printf("%s",path);<br>
return(dist[target]);<br>
}<br>
void main(){<br>
int cost[N][N],i,j,w,ch,co;<br>
int source,target,x,y;<br>
printf("\tShortest Path Algorithm DIJKSTRA's\n\n");<br>
for(i=0;i<N;i++){<br>
for(j=1;j<N;j++){<br>
cost[i][j]=IN;<br>
}<br>
}<br>
for(x=0;x<N;x++){<br>
for(y=x+1;y<N;y++){<br>
printf("Enter the weight of the path between node<br>
%d and %d : ",x,y);<br>
scanf("%d",&w);<br>
cost[x][y]=cost[y][x]=w;<br>
}<br>
printf("\n");<br>
}<br>
printf("Enter the Source : ");<br>
scanf("%d",&source);<br>
printf("\nEnter the target ");<br>
scanf("%d",&target);<br>
co=dijkstra(cost,source,target);<br>
printf("Shortest Path %d\n",co);<br>
}<br>
9) Write a C program to simulate the IP address manipulation<br>
-Extract net id and host id.<br>
//IP address manipulation<br>
#include<stdio.h><br>
void main()<br>
{<br>
int i,p,q,r,a,b,c,d;<br>
printf("Enter the IP address:");<br>
scanf("%d",&i);<br>
scanf("%d",&p);<br>
scanf("%d",&q);<br>
scanf("%d",&r);<br>
printf("Your IP address id %d.%d.%d.%d",i,p,q,r);<br>
if (p<=255 && q<=255 && r<=255)<br>
{<br>
if (i<=127)<br>
{<br>
if (i>0)<br>
{<br>
a=255;<br>
b=0;<br>
c=0;<br>
d=0;<br>
printf("\n CLASS A \n");<br>
a=a&i;<br>
b=b&p;<br>
c=c&q;<br>
d=d&r;<br>
printf("Network ID is %d.%d.%d.%d\n",a,b,c,d);<br>
printf("Host ID is %d.%d.%d\n",p,q,r);<br>
}<br>
}<br>
else if (i<=191)<br>
{<br>
if (i>127)<br>
{<br>
a=255;<br>
b=255;<br>
c=0;<br>
d=0;<br>
printf("\n CLASS B \n");<br>
a=a&i;<br>
b=b&p;<br>
c=c&q;<br>
12<br>
d=d&r;<br>
printf("Network ID is %d.%d.%d.%d\n",a,b,c,d);<br>
printf("Host ID is %d.%d\n",q,r);<br>
}<br>
}<br>
else if (i<=223)<br>
{<br>
if (i>191)<br>
{<br>
a=255;<br>
b=255;<br>
c=255;<br>
d=0;<br>
printf("\n CLASS C \n");<br>
a=a&i;<br>
b=b&p;<br>
c=c&q;<br>
d=d&r;<br>
printf("Network ID is %d.%d.%d.%d\n",a,b,c,d);<br>
printf("Host ID is %d\n",r);<br>
}<br>
}<br>
else if (i>223)<br>
{<br>
printf("Wrong IP Address!");<br>
}<br>
}<br><br>
}<br>

10) Write a C program to show Simple TCP client and server<br>
application (Single server-single client) – arithmetic<br>
operations.<br>
HEADER FILE:<br>
#include <stdio.h><br>
#include <string.h><br>
#include <stdlib.h><br>
#include <sys/types.h><br>
#include <sys/socket.h><br>
#include <netinet/in.h><br>
#include <arpa/inet.h><br>
#define SERV_TCP_PORT 6020<br>
#define SERV_UDP_PORT 6021<br>
#define SERV_HOST_ADDR "127.0.0.1"<br>
SERVER:<br>
#include "inet.h"<br>
#define MAXLINE 512<br>
int main()<br>
{<br>
int cnt,n,i,no,y=1;<br>
int p,out,opnd1,opnd2,op;<br>
char buf1[MAXLINE];<br>
int sockfd,newsockfd,clilen,childpaid;<br>
struct sockaddr_in serv_addr,cli_addr;<br>
if((sockfd=socket(AF_INET,SOCK_STREAM,0))<0)<br>
{<br>
perror("Server can't open socker:\n");<br>
printf("Sockfd:%d\n",sockfd);<br>
exit(0);<br>
}<br>
bzero((char*)&serv_addr,sizeof(serv_addr));<br>
serv_addr.sin_family=AF_INET;<br>
serv_addr.sin_addr.s_addr=htonl(INADDR_ANY);<br>
serv_addr.sin_port=htons(SERV_TCP_PORT);<br>
if(bind(sockfd,(struct<br>
sockaddr*)&serv_addr,sizeof(serv_addr))<0)<br>
{<br>
perror("server can't bind address:");<br>
printf("sockfd:%d\n",sockfd);<br>
exit(0);<br>
}<br>
listen(sockfd,5);<br>
clilen=sizeof(cli_addr);<br>
printf("server sockfd:%d\n",sockfd);<br>
newsockfd=accept(sockfd,(struct sockaddr*)&cli_addr,&clilen);<br>
printf("newsockfd for clint:%d\n",newsockfd);<br>
while(y!=0)<br>
{<br>
n=read(newsockfd,buf1,MAXLINE);<br>
sscanf(buf1,"%d %d %d",&op,&opnd1,&opnd2);<br>
bzero(buf1,MAXLINE);<br>
switch(op)<br>
{<br>
case 1:<br>
{<br>
out=opnd1+opnd2;<br>
sprintf(buf1,"output of Addition:%d",out);<br>
break;<br>
}<br>
case 2:<br>
{<br>
if(opnd1>opnd2)<br>
{<br>
out=opnd1-opnd2;<br>
sprintf(buf1,"output of substraction:%d",out);<br>
}<br>
else<br>
sprintf(buf1,"error opnd1 must be greater then opnd2");<br>
break;<br>
}<br>
case 3:<br>
{<br>
out=opnd1*opnd2;<br>
sprintf(buf1,"output of multiplication:%d",out);<br>
break;<br>
}<br>
case 4:<br>
{<br>
if(opnd1>opnd2 &&opnd2!=0)<br>
{<br>
out=opnd1/opnd2;<br>
sprintf(buf1,"output of division:%d",out);<br>
}<br>
else<br>
if(opnd1<opnd1)<br>
sprintf(buf1,"error in I/P opnd1 must be greater then opnd2");<br>
else<br>
if(opnd2==0)<br>
sprintf(buf1,"error in I/P opnd2!=0");<br>
break;<br>
}<br>
case 5:<br>
exit(0);<br>
}<br>
n=strlen(buf1);<br>
no=write(newsockfd,buf1,n);<br>
bzero(buf1,MAXLINE);<br>
}<br>
close(newsockfd);<br>
close(sockfd);<br>
}<br>
CLIENT:<br>
#include "inet.h"<br>
#define MAXLINE 512<br>
main()<br>
{<br>
int n,i,no,y=1;<br>
int opnd1,opnd2,ch=0;<br>
char buf[MAXLINE];<br>
int sockfd,servlen;<br>
struct sockaddr_in serv_addr,cli_addr;<br>
bzero((char*)&serv_addr,sizeof(serv_addr));<br>
serv_addr.sin_family=AF_INET;<br>
serv_addr.sin_addr.s_addr=inet_addr(SERV_HOST_ADDR);<br>
serv_addr.sin_port=htons(SERV_TCP_PORT);<br>
if ((sockfd=socket(AF_INET,SOCK_STREAM,0))<0)<br>
{<br>
perror("client can't open socket");<br>
}<br>
if (no=connect(sockfd,(struct<br>
sockaddr*)&serv_addr,sizeof(serv_addr))<0)<br>
{<br>
perror("client can't connect to server");<br>
printf("sockfd:%d\n",sockfd);<br>
exit(0);<br>
}<br>
servlen=sizeof(serv_addr);<br>
printf("Connection setup with sockfd:%d\n",sockfd);<br>
while(y!=0)<br>
{<br>
bzero(buf,MAXLINE);<br>
printf("\n1: Addition");<br>
printf("\n2: Subtraction");<br>
printf("\n3: Multiplication");<br>
printf("\n4: Division");<br>
printf("\n5: Exit");<br>
printf("\nEnter your choice : \t");<br>
scanf("%d",&ch);<br>
if(ch >= 5)<br>
{<br>
if (ch > 5)<br>
printf("\nInvalid choice : \t");<br>
exit(1);<br>
}<br>
printf("\n Enter the first operand:");<br>
scanf("%d",&opnd1);<br>
printf("\n Enter the second operand:");<br>
scanf("%d",&opnd2);<br>
if(ch!=0)<br>
{<br>
bzero(buf,MAXLINE);<br>
sprintf(buf,"%d %d %d",ch,opnd1,opnd2);<br>
n=strlen(buf);<br>
buf[n]='\0';<br>
write(sockfd,buf,n);<br>
bzero(buf,MAXLINE);<br>
n=read(sockfd,buf,MAXLINE);<br>
printf("CLIENT reading at sockfd: %s\n",buf);<br>
bzero(buf,MAXLINE);<br>
}<br>
else<br>
y=0;<br>
}<br>
close(sockfd);<br>
exit(0);<br>
}<br>
11) Write a C program to show Simple UDP client and server<br>
application (Single server-single client) – String<br>
manipulation<br>
SERVER:<br>
#include<stdio.h><br>
#include<sys/types.h><br>
#include<sys/socket.h><br>
#include<netinet/in.h><br>
#include<string.h><br>
int main()<br>
{<br>
int serv_sockfd,cli_sockfd,client3_sockfd;<br>
int serv_len,cli_len;<br>
struct sockaddr_in serv_address;<br>
struct sockaddr_in cli_address;<br>
serv_sockfd=socket(AF_INET,SOCK_DGRAM,0);<br>
bzero((char *)&serv_address,sizeof(serv_address));<br>
serv_address.sin_family=AF_INET;<br>
serv_address.sin_port=2002;<br>
serv_len=sizeof(serv_address);<br>
if(bind(serv_sockfd,(struct<br>
sockaddr*)&serv_address,serv_len)==-1)<br>
{<br>
printf("some error here....");<br>
close(1);<br>
}<br>
while(1)<br>
{<br>
char str[256];<br>
int l=0,h=1,j;<br>
cli_len=sizeof(cli_address);<br>
printf("\n server is ready \n");<br>
int n=recvfrom(serv_sockfd,str,sizeof str,0,(struct<br>
sockaddr*)&cli_address,(socklen_t*)&cli_len);<br>
n-=1;<br>
write(1,str,n);<br>
write(1,"\n\n",2);<br>
bzero(str,sizeof(str));<br>
sprintf(str,"%d",n);<br>
n=strlen(str);<br>
sendto(serv_sockfd,str,n,0,(struct<br>
sockaddr*)&cli_address,cli_len);<br>
}<br>
close(client3_sockfd);<br>
}<br>
CLIENT:<br>
#include<stdio.h><br>
#include<sys/types.h><br>
#include<sys/socket.h><br>
#include<netinet/in.h><br>
#include<string.h><br>
int main()<br>
{<br>
int sockfd,len,len1,nc;<br>
struct sockaddr_in servaddr;<br>
struct sockaddr_in cliaddr;<br>
char ch[256];<br>
sockfd=socket(AF_INET,SOCK_DGRAM,0);<br>
servaddr.sin_family=AF_INET;<br>
servaddr.sin_addr.s_addr=inet_addr("127.0.0.1");<br>
servaddr.sin_port=2002;<br>
len=sizeof(servaddr);<br>
cliaddr.sin_family=AF_INET;<br>
cliaddr.sin_addr.s_addr=htonl(INADDR_ANY);<br>
cliaddr.sin_port=htonl(0);<br>
len1=sizeof(cliaddr);<br>
bind(sockfd,(struct sockaddr*)&cliaddr,len1);<br>
printf("enter the string to find its length: \n");<br>
fgets(ch,256,stdin);<br>
sendto(sockfd,ch,strlen(ch),0,(struct sockaddr*)&servaddr,len);<br>
bzero(ch,256);<br>
int n=recvfrom(sockfd,ch,256,0,(struct<br>
sockaddr*)&servaddr,(int*)&len);<br>
ch[n]='\0';<br>
printf("the length Calculated by Server is: ");<br>
fputs(ch,stdout);<br>
printf("\n");<br>
close(sockfd);<br>
return(0);<br>
}<br>





