# Collaborative Document. Day 2, May 18th
2021-05-17-swc-R-nlesc

Welcome to The Workshop Collaborative Document


This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

All content is publicly available under the Creative Commons Attribution License

https://creativecommons.org/licenses/by/4.0/

 ----------------------------------------------------------------------------

This is the Document for today: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-02)

Collaborative Document day 1: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-01)

Collaborative Document day 2: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-02)

Collaborative Document day 3: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-03)

Collaborative Document day 4: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-04)



## 👮Code of Conduct

* Participants are expected to follow those guidelines:
* Use welcoming and inclusive language
* Be respectful of different viewpoints and experiences
* Gracefully accept constructive criticism
* Focus on what is best for the community
* Show courtesy and respect towards other community members


## ⚖️ License

All content is publicly available under the Creative Commons Attribution License: https://creativecommons.org/licenses/by/4.0/



## 🙋Getting help
to ask a question, type `/hand` in the chat window

to get help, type `/help` in the chat window

you can ask questions in the document or chat window and helpers will try to help you


## 🖥 Workshop website

[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/)

🛠 Setup
[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/#setup)

Download files
[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/#setup)


## 👩‍🏫👩‍💻🎓 Instructors

Pablo Rodríguez-Sánchez, Alessio Sclocco, Barbara Vreede


## 🧑‍🙋 Helpers

Lieke de Boer


## 🗓️ Agenda
Day 2, May 18th
|        |                                                  |
|:-------|:-------------------------------------------------|
| 09:00  | Version Control with Git                         |
| 10:15  | Coffee break                                     |
| 10:30  | Version Control with Git (Continued)             |
| 11:30  | Coffee break                                     |
| 11:45  | Version Control with Git (Continued)             |
| 12:45  | Wrap-up                                          |
| 13:00  | END                                              |


## 🧠 Collaborative Notes

### Command Log

```bash
# Helper for git
git --help
# Create a new project in directory gitlesson
cd code
mkdir gitlesson
cd gitlesson
git init
# Configure git
## Only necessary the first time you use git
git config -l
git config --global user.name "My Name"
git config --global user.email "my.email@address.here"
## Line termination for Windows users
git config --global core.autocrlf true
## Line termination for MacOS or Linux
git config --global core.autocrlf input
# Create a file
git status
nano mars.txt
cat mars.txt
# Add the just created file to the git repository
git status
git add mars.txt
git commit -m "Hello world!"
# Check the log of commits
git log
git log --oneline --graph
# Made changes to an existing file
nano mars.txt
git status
git diff
git add mars.txt
git commit -m "Add information about satellites"
# The following command is to look at a specific commit
## You need to replace <commit id> with the id of a commit
git show <commit id>
# The following command is to compare two commits
## You need to replace <commit id> with the id of a commit
git diff <commit id> <commit id>
# The following command is to compare the previous with the current state
git diff HEAD~1 HEAD
# Go back in time to a specific commit
git log --oneline
## You need to replace <commit id> with the id of a commit
git checkout <commit id> mars.txt
cat mars.txt
# And then back to the future
git diff --staged
git reset HEAD mars.txt
git status
git checkout -- mars.txt
cat mars.txt
# How to tell git to ignore the existence of files
## You need to replace <file> with the file you want to ignore
echo "<file>" >> .gitignore
## You can also edit .gitignore with your editor
nano .gitignore
## .gitignore can also be versioned with git
git add .gitignore
git commit -m "Added .gitignore file"
# Change the branch name from master (or anything else) to main
git branch -M main
# Set the remote repository on GitHub
## You need to replace <URL> with the https or ssh url of your repository
git remote add origin <URL>
# Send changes to remote repository
## After the first time, just git push is enough (without the "-u origin main")
git push -u origin main
# Retrieve changes from remote repository
git pull
# Adding another file and upload the commit to GitHub
nano earth.txt
git add earth.txt
git commit -m "Hello heart!"
git push
```


### Exercise (10 minutes)

1. Create a file called venus.txt
2. Write "Venus looks cool, but it is very warm"
3. Add it to git
4. Commit it with a message 

### Exercise

Copy the commit message you used.

### Exercise (2 min)

What command would you use to compare the current state with the first one?

* git diff HEAD HEAD~2

### Exercise (2 minutes)

Past your `git remove -v` output.

## Feedback

### Top

Something that you liked!

* I really like the interactiveness and the fact that you're also running into things on the go so we see how you solve that
* Very informative, great start to continue learning.
* Very interactive, and easy to follow even though I haven't done this before. The link with Github was very clear.
* It was really nice that individual questions were given enough attention (it is difficult but very appreciated), and also that the level and tone of instruction was not assuming any previous knowledge (even if it was there in some cases)
* I had been meaning to learn git and github but i was a bit intimidated by it - this was a very clear instruction, and I also more clearly see how it will help me to structure and document my research steps.
* I really liked that it was a good overview of basic functions that one commonly encounters in working on a project. The content discussed were all relevant to me.
* The exercises in between the session to check the skills learnt.
* Very nice instruction about Git, very informative and useful. The helpers are definatly giving great help to us. Very appreciated.
* It was a nice workshop, I liked that you started with the command line tools and then proceeded to GitHub. Everything was clear to me. I'll definitely incorporate git in my everyday toolbox
* It was a nice workshop, so thank YOU! It really highlights the possibility for collaborative work, especially now when people are working separately from home. Version control is an issue I always struggle with. This seems like a really good panacea for that.
* I liked veray much the way to talked us through everything, for me at the right pace, and it just makes it easy to grasp and listen along while you guide us through. 
* Very usfull course, but I think we should have made a bit more exercises to get use to it
* Toggling between 3 screens is quite a challenge, but is necessary when done online.
* This HackMD thing is amazing

### Tip

Something we should improve.

* Perhaps a bit less details. In some partts that might be confusing. 
* Not sure how to control that, I lost five or so minutes in the breakroom and was totally lost after that. I went running behind you and the result was not the expected. But I got the general idea, so that is Ok
* There could have been some more excercises to get a better feel for the material
* When you are doing thngs it would be good to repeat what you are doing multiple times so it sticks with us eg I pressed up arrow to get last command so we get more confortable with the shortcuts. It will also slow you down a bit as you are quite quick when writing code. 
* It would be great to link a bit more with rstudio (just because it's something more people are familiar with) -- at least it motivated me that it's more 'tangible'
* the problems some people encountered were now dealed with in the group in contrast to yesterday in the break-out rooms. that had my preference, to not delay or all get a bit confused
* Maybe more exercises? But otherwise it was pretty informative, and I do appreciate the extras actually. It would be great to have another more advanced course too.
* Again we need time before it starts to sort out bugs of the simple kind before we get into the lesson.
* I would like to learn more about "pull" functions especially when I work with other developers.
* More exercises, and a bit more information regarding the link with RStudio. That would have been interesting, especially because most of us have had experience with R before. 
* In the end it was a bit messy with everyone fixing their bugs, and I had nothing to do for 10-15 minutes, so I got distracted at some point, because there was nothing for me. But that's a minor detail. In general, everything was really good. 
* I felt that I needed more exercises to get in the rythym of working with github (create-add-commit) before I can do a subsequent series of actions like deleting, modifying, etc. 
* agree with previous comment - I do still need to practice a bit with all the steps to be able to integrate it into my work flow. (not really a 'tip' maybe a second course :)
* Perhaps more emphasis in the nomenclature?
* Could a pdf of the Hackmd collaborative document be sent round after each day as you can only save it as pdf if you have hackmd installed...
* The pace is a bit quick for me if I need to ask question through chat section. 

## 📚 Resources

* [git](https://git-scm.com/)
* [GitHub](https://github.com)