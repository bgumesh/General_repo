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

/////////////////////////////////////////CN//////////////////////////////////////////


