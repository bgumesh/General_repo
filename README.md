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

