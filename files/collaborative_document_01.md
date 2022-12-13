# Collaborative Document. Day 1, May 17th
2021-05-17-swc-R-nlesc

Welcome to The Workshop Collaborative Document


This Document is synchronized as you type, so that everyone viewing this page sees the same text. This allows you to collaborate seamlessly on documents.

All content is publicly available under the Creative Commons Attribution License

https://creativecommons.org/licenses/by/4.0/

 ----------------------------------------------------------------------------

This is the Document for today: [link](https://tinyurl.com/2021-05-17-swc-R-nlesc-01)

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

For more details, see [here](https://docs.carpentries.org/topic_folders/policies/code-of-conduct.html).

Want to report a Code of Conduct incident and you prefer to do it anonymously? You can do it [here](https://goo.gl/forms/KoUfO53Za3apOuOK2).



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
[link](https://escience-academy.github.io/2021-05-17-swc-R-nlesc/#dataset-shell)


## 👩‍🏫👩‍💻🎓 Instructors

Pablo Rodríguez-Sánchez, Alessio Sclocco, Barbara Vreede


## 🧑‍🙋 Helpers

Lieke de Boer, Thijs van Lankveld


## 🗓️ Agenda

Day 1, May 17th
|        |                                                  |
|:-------|:-------------------------------------------------|
| Before | Welcome and pre-workshop survey                  |
| 09:00  | Automating Tasks with the Unix Shell             |
| 10:15  | Coffee break                                     |
| 10:30  | Automating Tasks with the Unix Shell (Continued) |
| 11:30  | Coffee break                                     |
| 11:45  | Automating Tasks with the Unix Shell (Continued) |
| 12:45  | Wrap-up                                          |
| 13:00  | END                                              |



## 🧠 Collaborative Notes

### Command log
```shell=
pwd # print working directory
ls # list (files)
ls -F # list with an option `-F`, to see the type of the object
clear
ls -F /
ls Desktop/data-shell
ls -S Desktop/data-shell/data # -S to order by size
ls --help # get help for `ls` command
man ls # manual pages, use 'q' to exit manual pages
pwd # that's where you are (current working direcotory)
cd Desktop # change directory to Desktop
pwd
cd data-shell
ls -F
cd data # move to data directory
ls -F
cd .. # move one directory up
pwd
ls -a
ls -a .
cd # go to `home`
cd ~ # go to 'home' too, '~' stands for home directory
clear # clears the terminal
mkdir thesis # make directory thesis
ls -F thesis # what is in the thesis directory - it is empty
mkdir -p thesis/chapter_1/section_1/subsection_1 # creates all the directories in the path we specify
ls -F -R # lists recursively 
cd thesis # there is only chapter_1 directory inside
nano draft.txt # open nano, a command line text editor, and open a file draft.txt for edit
cd ..
pwd # we should be in `data` directory
mv thesis/draft.txt thesis/quotes.txt # move works as renaming if the new file name is used, in this case `draft.txt` will be renamed to `quotes.txt`
ls thesis
mv -i # is interactive, will ask you if you are sure about reaming
mv -i aninals.txt morse.txt
mv thesis/quotes.txt . # move from thesis direcotory to the current one
ls -F
cp # copy
cp quotes.txt thesis/quotations.txt # make a copy of the quotes.txt file, put it in the thesis directory, name it quotations.txt
ls thesis
cp thesis thesis_backup
cp -r thesis thesis-backup
ls thesis
ls thesis_backup
ls thesis thesis_backup
man ls
rm # remove, be careful, the file is completely gone, does not go into the `bin`
rm quotes.txt # will remove quotes.txt file
rm -i morse.txt # will ask you if you're sure
rm thesis # this will not work, rm does not work with directories
rm -r thesis # rm -ri is safer to do, -r will remove the folder with all inside
ls
ls *th*
wc # word count
wc cubane.pdb # will list nubmer of lines, words and characters in the cubane.pdb file
wc *.pdb # 
wc -m *.pdb
wc -w *.pdb # count words
wc -l *.pdb # count lines
wc -l *.pdb * > length.txt # print the number of lines and redirect to the file
ls length.txt
cat length.txt # print out the content of the length.txt file
less length.txt # display the content of the file, allow to scroll
sort length.txt # sorts the content of the file in alphabitical order
sort -n length.txt # sorts the file in the numerical order
sort -n length.txt > sorted-length.txt
cat sorted-length.txt
head -n 1 sorted-length.txt
tail -n 1 sorted-length.txt
head -n 2 sorted-length.txt
head -n 2 sorted-length.txt > subset-sorted-length.txt
cat subset-sorted-length.txt
tail -n 2 sorted-length.txt >> subset-sorted-length.txt
cat subset-sorted-length.txt
sort -n length.txt
sort -n length.txt | head -n 1 # pipe means we are redirecting output of one comand as an input to the second command, in this case the output of the sort command becomes an input for the head command
wc -l *.pdb | sort -n | head -n 1

# looping (iterating over a collection or set of elements)
cd creatures
ls
wc -l *

# while typing in, ignore `>` shell will add it for you at the beging of each line untill you type `done`
for filename in basilisk.dat minotaur.dat unicorn.dat
> do
> head -n 2 $filename | tail -n 1
> done

for filename in *.dat
> do
> echo $filename
> head -n 100 $filename | tail -20 
> done

cp *.dat original-*.dat # will not work
# above can be achieved with a loop
for filename in *.dat
> do
> cp $filename original-$filename
> done

for filename in *.dat; do echo "removing original"; rm -i original-$filename; done
```


### please check the following to confirm that Git is installed:
```
git --help
```
if you get many options: you're good. If you get an error: please let us know!



-------
### Other Notes
- Shell (what we see in the terminal window) os a way to interact with your computer.
- Terminal - is an application we type in cammands in
- Shell - is a command line interface we can use to *talk* to the computer
- Bash is a type of shell
- `/` stands for the `root` the upper most location in your file system, that's where all the files and directories (folders) are located
- The collab document can work slightly faster when you use the 'edit' option (the pencil in the top-left). This is especially the case when a lot of people are working on it at the same time.
- The touch command can not just be used to create a file before working on it. It can also be used to check whether you have write access in the directory, or to create multiple files before editing any.
- Moving files is the same as renaming files.
- Making commands interactive can be done with the -i option. For example, `mv -i` for interactively moving a file.
- Moving a file to a directory will be interpreted as moving the file into the directory. For example, `mv my_directory/my_file.txt .` will move the file to be at `./my_file.txt`.
- Several commands use similar option letters for similar functionality, like `-r` or `-R` for recursive application. If you forgot which one applies to which command, you can always look at the manual for that command, for example `man ls`.
- Be careful with the `rm` command: it will remove files without asking whether you're sure and without moving it to some trashcan folder.
- When participating in the exercises, try to type out the commands instead of copy-pasting them. You will learn more this way, for example by making mistakes and correcting them.
- Wildcards can be a powerful way of specifying multiple options, for example when listing files that conform to some pattern. The `*` wildcard matches to 0 or more characters, the `?` wildcard matches to exactly one character. For example, `e*mple` or `e??mple` both match to `example`.
- At least on Mac, the bash shell doesn't state your current directory before the `$` sign. This can make it so you cannot find the files you were expecting, because you may not be in the directory you were expecting. When you're 'lost' like this, try using `pwd` to find out your current directory.
- When using the `>` operator, be careful not to write ouput to your input file, for example don't do `sort -n length.txt > length.txt`. This operation where a file is read and written to at the same time, will usually not give the desired result. Better to write to a new file, like `sort -n length.txt > sorted-length.txt`.
- The difference between the `>` and `>>` operators is that the first one replaces the content if the file already exists and the second appends to any existing content.

#### rules for naming files
- we should use descriptive file names, eg. thesis.txt is better than file_1
- don't start a file name with `-` shell will interpret it as an option
- if you use space, you will need to *escape* the spaces, better to use `_` underscore instead of space

### Exercise

Starting from `/Users/amanda/data`, which of the following commands could Amanda use to navigate to her home directory, which is `/Users/amanda`?

1. `cd .`
2. `cd /`
3. `cd /home/amanda`
4. `cd ../..`
5. `cd ~`
6. `cd home`
7. `cd ~/data/..`
8. `cd`
9. `cd ..`


### Break 10:15 - 10:30

### Exercise

We have seen how to create text files using the nano editor. Now, try the following command:

```bash=
touch my_file.txt
```

1. What did the `touch` command do? When you look at your current directory using the GUI file explorer, does the file show up?
2. Use `ls -l` to inspect the files. How large is `my_file.txt`?
3. When might you want to create a file this way

- 1. `touch` modifies the editing time of the file. Yes, it dose show up under thesis folder. 2. `ls-l` gives the detailed information about the files under current folder. The size is 0. 
- 1. Yes, a new file is created named 'my_file.txt'. 2. It is empty (0kb). 3. Simply create a new file?
- 1. It created a file names "my_file.txt". Yes, it shows up. 2. It is O size as it is empty. 3. If we wish to create the file without opening in nano text editor.
- 1. a new file "my_file.txt" appears in thesis folder. 2. it lists all the files in thesis folder with the file sizes & time created. 0 bytes. 3. When you just want to create a file and insert the content later?`
- 1.yes  2.It says "totla 8" 3. Creates, empty file.
- 1. there is now a file my_file.txt 2. it is 0 kb. 3. maybe something with the date or time, a timestamp. 
- 1. there is a new file named my_file.txt 2. It is 0KB
- 1. creates a new file named my_filet.txt 2. 0 kb, 3. Creates an empty file which an be edited later, maybe you can also check this way if you can edit a directory, before you make changes to other files. 
- 1. the touch command creates a new file called my_file.txt and this shows up in the current directory. 2. the file size is 0kb. 3. To create an empty file.
- 1.yes 2. 0 3. 
- 1. It created a file named my_file.txt 2. Size is zero 3. Ceate a file without opening it in nano
- A new, blank text file was created. It is 0 Kb.
- yes a blank file (o kb)was made. You could use it to write data to later.
- An empty file was created with this command. It shows up if I do ls and it is 0 kb. It might be useful to keep track of when a file was created?
- touch created a .txt file in the directory. it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0 it is 0
- 1. creates a new file 2. it is 0 kb 3. prepare file to fill it with the information later
- the file of size 0 was created
- 1) It created a new text file in my cd. 2) It's 0 kb. 3) When you know you want specific files (even multiple similar files) but might want to add content later. 
- 1) The file appears in the GUI 2) The file is 0 in size 3) This might be useful if I want to test if I have access and/or edit rights to a directory, or if I want a file as a placeholder to add content later


### Exercise 3

Suppose that you created a plain-text file in your current directory to contain a list of the statistical tests you will need to do to analyze your data, and named it `statstics.txt`

After creating and saving this file you realize you misspelled the filename! You want to correct the mistake, which of the following commands could you use to do so?

1. `cp statstics.txt statistics.txt`
2. `mv statstics.txt statistics.txt`
3. `mv statstics.txt .`
4. `cp statstics.txt .`

- 2

### Exercise 7

When run in the `molecules` directory, which `ls` command(s) will produce this output?

```bash=
ethane.pdb methane.pdb
```

1. `ls *t*ane.pdb`
2. `ls *t?ne.*`
3. `ls *t??ne.pdb`
4. `ls ethane.*`

- 3


### ☕ Tea break 11:30 - 11:45 ☕

### Exercise 3

In our current directory, we want to find the 3 files which have the least number of lines. Which command listed below would work?

1. `wc -l * > sort -n > head -n 3`
2. `wc -l * | sort -n | head -n 1-3`
3. `wc -l * | head -n 3 | sort -n`
4. `wc -l * | sort -n | head -n 3`

- 4

### Exercise 4

A file called `animals.txt` (in the `data-shell/data` folder) contains the following data:

```
2012-11-05,deer
2012-11-05,rabbit
2012-11-05,raccoon
2012-11-06,rabbit
2012-11-06,deer
2012-11-06,fox
2012-11-07,rabbit
2012-11-07,bear
```

What text passes through each of the pipes and the final redirect in the pipeline below?

```
cat animals.txt | head -n 5 | tail -n 3 | sort -r > final.txt
```

Hint: build the pipeline up one command at a time to test your understanding

- Yifang 1. list all animals in the file; 2. first 5 lines in the file; 3. the last 3 lines of the first 5 lines; 4. sort the last 3 lines 
- Nadine 1) Returns the file content; 2) Returns the first 5 lines of the file; 3) Returns the last 3 lines of the file; 4) sorts the three lines and saves it as a file named 'final.txt'. 
- Bhuwan 1. Using cat animals.txt returns all the content od the file. 2. cat animals.txt | head -n 5 returns the first 5 lines of the file. 3. cat animals.txt | head -n 5 | tail -n 3 returns the bottom 3 lines of the first 5 lines of the file. 4. Sorts the three lines and saves in final.txt file.
- Stella head -5 takes the first five, tail -n 3 takes the last 3 from the five outputs. sort -r sorts un reverse order, > final.txt saves the file.
- Cameron Gets cat animals text, shows the top 5 rows, takes the last 3 lines and sorts by file size nad saves it as final.txt. 
- Laura G-M  
            - takes the last 3 lines from the first 5 lines of animals.txt file and sorts them and saves the output on the final.txt
- 
- Laura W 1. shows the content 2. shows the first 5 lines 3. shows the last 3 lines 4. sorts the file  and the sorted file is saved into a new file called final
- Raquel it shows the content of the file, then it takes the first 5 items, then the 3 last items from that last output, then it sorts the output (last three items) from high to low and saves them in a final.txt file
- Mara opens the file, shows the firt 5 items, shows the last three items, sorts the files in 'reverse'/descending, saves it into a new file callled final.txt
- Ankita 1. shows the content of the file 2. selects the first 5 items in the file 3. of these 5 items, it selects the last 3 items 4. sorts the three items in descending order (?) 5. pastes the output in a file called final.txt.
- Xiaoran
- Sobhan It takes the first 5 lines of animals.txt together with the last 3 lines; sort them and saves them in a new file called final.txt
- Marcelo It shows the content of the file, then it shows the first 5 lines; from those, it lists the bottom 3 animals, orders them and saving this selction in a file called final.txt
- Floor - give me the first 5 lines, then the bottom 3 of those than sort them from big to small that write to a file
- Laura
- Melanie paste what is in animals.txt to terminal| paste first 5 lines of previous output file| paste last 3 lines of previous output file| sort output file on ? | save output to a file
- Harm                                              
- Yuliia - 1) all animals, 2) first 5 in the numerically sorted list, 3) last three from the previous step, 4) sort in reverse, 5) write to a file. (items 5,4,3 from the numerically sorted list of all animals)
- Marina
- Patricia - 1) the original txt file 2) the first 5 items in the list 3) the last 3 items in the list 4) the new list of 5+3 items sorted into (?) order 5) redirect into a new txt file
- Zefi: 1) All text of animals.txt 2) First 5 lines sorted numerically 3) The last 3 lines of the previous 5 lines sorted numerically 4) These 3 lines in reversed sorted order 5) Print these in a file


### please check the following to confirm that Git is installed:
```
git --help
```
if you get many options: you're good. If you get an error: please let us know!


## Tip/Top
### Tip
- make sure that people in breakout rooms can keep up with the main room
- would like to see first the complex problem, and then see how that can be solved (example with a research problem)
- collaborative doc can be chaotic
- when lost, it was hard to keep up
- at the beginning, explain more on the terminal, how to navigate it
- schedule 15 minutes of welcome and sorting things out
- the beginning was a bit chaotic
- sometimes not able to follow the instructions
- small tips for the terminal would be useful
- info on what we are going to do, explain the reason why we use the terminal interface
- resources (servers, cloud environments etc)

### Top
- good interactive
- breakout room for help
- like the pace, not too fast, not too slow
- the breaks are really good
- collaborative document was very useful
- great number of helpers, all questions answered, also questions from helpers
- colaborative doc helped
- pauses
- useful topics


## 📚 Resources

The data used in this workshop can be found at http://swcarpentry.github.io/shell-novice/data/data-shell.zip

Manual Pages in the web browser:
https://linux.die.net/man/
