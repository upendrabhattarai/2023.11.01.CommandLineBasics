# Crash Course in Command Line Basics

## Course content:

[Introduction to the command line](#introduction)

[Navigating the file system](#navigating_the_file_system)

[Working with files and folders](#working_with_files_and_folders)

[Searching and redirecting outputs](#searching_and_redirecting_outputs)

[For loops in the shell](#for_loops_in_the_shell)


## Objectives

- Explain the importance of learning the command line.
- Navigate the file system using the command line.
- Learn the basics of working with files and folders.
- Use a `for` loop to automate repetitive tasks.

---
# Introduction
# Navigating the file system
# Working with files a
---
## Why learn to use the command line?

<details>
  <summary> Greater control</summary>

While the Graphical user interface (GUI) of an operating system (OS) offers a user-friendly and visually appealing experience, the command line provides a way to access the system's backend. This grants you the ability to perform tasks that may not be readily achievable through the GUI. For instance, when encountering computer issues, the command line can be a valuable tool for checking error logs and running diagnostic tools. It also allows you to manage permissions, and user access, and execute complex tasks that might only be possible via the command line.

</details>

<details>
  <summary> Speed and Efficiency</summary>
  
Despite its steep learning curve, the command line offers efficient and quick ways to navigate your system. For example, when dealing with hundreds or thousands of files that require processing through a pipeline, manually handling them through a GUI could take hours or even days. In contrast, the command line allows you to automate these repetitive tasks, reducing the likelihood of errors. You can also create aliases for frequently used commands to enhance speed and efficiency. This eliminates the need to switch back and forth between the mouse and keyboard, making command line work significantly more efficient in many respects.

</details>


<details>
  <summary> Access remote servers</summary>

When working with large datasets, such as high-throughput sequencing data, there are instances where your local PC may not have the processing capacity to handle the millions of sequencing reads effectively. In such situations, you often need to access high-performance computing clusters for enhanced computing power. This can be achieved through the command-line interface, allowing you to connect to remote servers and leverage their computational resources.
    
</details>


<details>
  <summary> Command line tools</summary>
  
There are so many tools especially when it comes to dealing with omics data you simply don't have any GUI options. To install and use these tools, you must rely on the command line interface. In many cases, the command line versions offer additional features and parameter options that are not present in their GUI versions. For example, BLAST provides advanced functions that can only be accessed through the command line.

</details>


---

## Few terminologies:

**Command line** or the **Terminal** is the interface in a computer system that allows you to enter commands and receive output. **Command line** is predominantly used in Windows OS, where their version of the **Terminal** is known as the **Command line** or **CMD**. In contrast, **Terminal** is the default command line interface for Mac and Unix-based OS. 
The **Shell** is essentially the program that operates behind the command line interface, interpreting user input and displaying output. Commonly referred to as an **interpreter**. **Bash** is one of the most widely used shell programs and is typically the default on many Unix/Linux systems. Notably, it was the default shell on Mac for an extended period, but more recently, they transitioned from **Bash** to **Zsh**.

---

## How to access the shell

On a Mac or Linux machine, you can access a shell through "Terminal", which is already available on your computer. If you're using Windows, you'll need to download a separate program to access the shell, like `Git Bash`.

[Download link: Git Bash](https://gitforwindows.org/) 

[Installation instructions](HowToInstallGitBash.md)

---
# Navigating_the_file_system

---

## Key Commands & Navigation

Before we look at some common commands, I just want to note a few keyboard commands that are very helpful:

- `Up Arrow`: Will show your last command
- `Down Arrow`: Will show your next command
- `Tab`: Will auto-complete your command
- `Ctrl + L`: Will clear the screen
- `Ctrl + C`: Will cancel a command


---

### Manual Command

On Linux and Mac, the `man` command is used to show the **manual** of any command that you can run in the terminal. So if you want to know more about the `ls` command, you could run:

```bash
man ls
```

If you are on Windows and using **Git Bash**, the `man` command is not included, however, you can just type the command that you want to know more about and then `--help` and you will get similar info:

```bash
ls --help
```

You should be able to use the arrow keys or page up and down. When you are ready to exit, just press `q`.

---

### The `whoami` Command

The `whoami` command will show you the current user that you are logged in as.

```bash
whoami
```
---

### The `date` Command

Another really simple one is the `date` command, which, will show you the current date and time.

```bash
date
```
---

## File System Navigation

Setup:

```bash
cd
mkdir -p Desktop/dir_1/dir_2/dir_3
```

Commands to navigate your file system are very important. You will be using them all the time. Below are some of the navigation commands that are used very frequently.

| Command                             | Description                                                                       |
| ----------------------------------- | --------------------------------------------------------------------------------- |
| pwd                                 | Lists the path to the working directory                                           |
| ls                                  | List directory contents                                                           |
| ls -l                               | List contents with more info including permissions (long listing)                 |
| ls -r                               | List contents reverse order                                                       |
| cd                                  | Change directory to home                                                          |
| cd [dirname]                        | Change directory to specific directory                                            |
| cd ~                                | Change to home directory                                                          |
| cd ..                               | Change to parent directory                                                        |
| cd -                                | Change to previous directory (which could be different than the parent of course) |

Of course, you can group flags together. For example, if I want to see more info and view hidden files, I could do `ls -l -a` and even shorten it to `ls -la`.


## Challenge-1: Find hidden items

### Finding hidden files and directories in your home folder.

First navigate to your `home` directory, if you are not already there. Explore the options for `ls` to
find out how to see hidden directories. List the contents of the directory with the option to display all the hidden items there.

<details>
  <summary>::::::::::::::: Hint</summary>

  
Hint: hidden files and folders in Unix start with `.`, for example: `.my_hidden_directory` or `.my_hidden_file`. \  
  
You can open the manual page or help page for the `ls` command and search inside using a keyword: `dot`. \
You can type `/` followed by your keyword `dot` to search the manual page and you can see what option to use.


</details>

<details>
  <summary>::::::::::::::: solution</summary>
  

First, use the `man` command to look at the options for `ls`.
  

```bash
man ls
```

The `-a` option is short for `all` and says that it causes `ls` to "not ignore entries starting with ." This is the option we want.


```bash
ls -a
```

You will see all the files and folders that were hidden and start with `.`
  

</details>

## Full vs. Relative Paths

The `cd` command takes an argument which is a directory
name. Directories can be specified using either a *relative* path or a
full *absolute* path. The directories on the computer are arranged into a
hierarchy. The full path tells you where a directory is in that
hierarchy. Navigate to the home directory, then enter the `pwd`
command.

```bash
cd  
pwd  
```

You will see:


```output
/home/<your_user_name>
```

This is the full name of your home directory. This tells you that you
are in a directory called `your_user_name`, which sits inside a directory called
`home` which sits inside the very top directory in the hierarchy. The
very top of the hierarchy is a directory called `/` which is usually
referred to as the *root directory*. So, to summarize: the home folder for your user is a
directory in `home` which is a directory in `/`.

---

To navigate to the `dir_3` directory that you just created before:

```bash
cd /Users/<your_user_name>/Desktop/dir_1/dir_2/dir_3/
```

Or

```bash
cd Desktop/dir_1/dir_2/dir_3/
```

These two commands have the same effect, they both take us to the `dir_3` directory.
The first uses the absolute path, giving the full address from the root directory. The
second uses a relative path, giving only the address from your working directory in this case your home directory. A full
path always starts with a `/`. A relative path does not.

A relative path is like getting directions from someone on the street. They tell you to
"go right at the stop sign, and then turn left on Main Street". That works great if
you're standing there together, but not so well if you're trying to tell someone how to
get there from another country. A full path is like GPS coordinates. It tells you exactly
where something is no matter where you are right now.

You can usually use either a full path or a relative path depending on what is most convenient.

Over time, it will become easier for you to keep a mental note of the
structure of the directories that you are using and how to quickly
navigate amongst them.


## Challenge-2: Relative path resolution

Using the filesystem diagram below, if `pwd` displays `/Users/thing`,
what will `ls ../backup` display?


1. `../backup: No such file or directory`
2. `2012-12-01 2013-01-08 2013-01-27`
3. `2012-12-01/ 2013-01-08/ 2013-01-27/`
4. `original pnas_final pnas_sub`

![](fig/filesystem-challenge.svg)

<details>
  <summary>::::::::::::::: Solution</summary>


1. No: there *is* a directory `backup` in `/Users`.
   
2. No: this is the content of `Users/thing/backup`,
  but with `..` we asked for one level further up.

3. No: see previous explanation.
  Also, we did not specify `-F` to display `/` at the end of the directory names.

4. Yes: `../backup` refers to `/Users/backup`.
   

</details>

---
# Working_with_files_and_folders

---

## Modifying Files & folders

| Command                     | Description                                         |
| --------------------------- | --------------------------------------------------- |
| mkdir [dirname]             | Make directory                                      |
| touch [filename]            | Create file                                         |
| rm [filename]               | Remove file                                         |
| rm -i [filename]            | Remove file, but ask before                    |
| rm -r [dirname]             | Remove directory                                    |
| rm -rf [dirname]            | Remove directory with contents                      |
| rm ./\*                     | Remove everything in the current folder             |
| cp [filename] [dirname]     | Copy file                                           |
| mv [filename] [dirname]     | Move file                                           |
| mv [dirname] [dirname]      | Move directory                                      |
| mv [filename] [filename]    | Rename file or folder                               |


We can also do multiple commands at once with the `&&` operator:

```bash
cd test2 && mkdir test3
```

---

## The `touch` Command
You can create files using touch command.

```bash
touch file-1.txt
```

you can also create multiple files.


```bash
touch file-{001..100}.txt
```

Now we have 100 .txt files in the current directory. Something that would have taken a lot longer to do in the GUI.

---
## The `nano` Command

The `nano` command is a text editor that is installed by default on most Linux distributions, MacOS and you can even use it with Git Bash on Windows. It is very similar to the `vim` editor, but it is much easier to use.

You can open an existing file to edit or create a new file and open it with:

```bash
nano [filename]
```

When you're ready to exit, just hit `Ctrl + X` and then `Y` to save and `N` to not save.

---

## The `head` and `tail` Commands

The `head` command is used to output the first part of files. By default, it outputs the first 10 lines of each file. You can also specify the number of lines to output.

Setup:

```bash
seq 100 200 > test.txt
```
Seq command is used to generate numbers from FIRST to LAST in steps of INCREMENT. It is a very useful command where we have to generate a list of numbers.

```bash
head [filename]
```

You can also specify the number of lines to output:

```bash
head -n 5 [filename]
```

The `tail` command is used to output the last part of files. By default, it outputs the last 10 lines of each file. You can also specify the number of lines to output.

```bash
tail [filename]
```

You can also specify the number of lines to output:

```bash
tail -n 5 [filename]
```
---

## The `less` Command

The `less` command is used to view the contents of a file. It is similar to the `cat` command, but it allows you to scroll up and down.

```bash
less [filename]
```

To exit the `less` command, just press `q`.

---

# Searching_and_redirecting_outputs

---

## The `cat` (concatenate) Command

The cat command is a very common command and allows you to create single or multiple files, view the content of a file, concatenate files, and redirect output in the terminal or files.

The most common thing cat is used for is to display the contents of a file:

```bash
cat [filename]
```
You can also create a file using the `cat` command:

```bash
cat > [filename]
```

This will open up a new file and you can start typing. When you are done, you can press `Ctrl + D` to save and exit.

You can also view the contents of multiple files:

```bash
cat [filename] [filename]
```

You can also append to a file:

```bash
cat >> [filename]
```

This will open up the file and you can start typing. When you are done, you can press `Ctrl + D` to save and exit.

You can use it to show line numbers:

```bash
cat -n [filename]
```

There are other uses of cat command, you can check its manual for more details.


---

## The `echo` Command

The `echo` command is used to display messages or to create and write to files. It is similar to the `cat` command, but it is used to display a single line of text.

```bash
echo "Hello World"
```

You can also use it to create a file:

```bash
echo "Hello World" > [filename]
```

You can also append to a file:

```bash
echo "Hello World" >> [filename]
```
---

## The `grep` Command

The `grep` command is used to search for a text pattern in a file. It is very powerful and can be used to search for a string or regular expression in a file or set of files.

```bash
grep [searchterm] [filename]
```

You can also search for a string in multiple files:

```bash
grep [searchterm] [filename] [filename]
```

`grep` is a powerful command and there is so much more that you can do with it.

---

## The `find` command

The `find` command is extremely powerful and is used to find the location of files and directories based on the conditions that you specify.

To start off by creating something to work with. Let's create 100 files in the current directory. This is one of those things that I talked about earlier where you can do certain things much faster than you could in the GUI. We already know that the `touch` command will create a file. It can also be used to create multiple files.

```bash
touch file-{001..100}.txt
```

Now we have 100 .txt files in the current directory. Something that would have taken a lot longer to do in the GUI.

Let's do something very simple and find a specific file. The format looks like this:

```bash
find [dirname] -name [filename]
```

Let's find the file called `file-001.txt`:

```bash
find . -name "file-001.txt"
```

This will look in the current directory, which is represented with a dot.

We can look in other directories as well. Let's create a file in our home folder called test.txt

```bash
touch ~/test.txt
```

To find that file:

```bash
find ~/ -name "test.txt"
```

We can look for files that match a certain pattern as well. Let's find all files that start with `file-`:

```bash
find . -name "file-*"
```

We can search for files that are empty:

```bash
find . -empty
```

Let's append some text to the file `file-002.txt`. We could use the `cat` command, like I showed you earlier, but we can also use the `echo` command:

```bash
echo "Hello World" >> file-002.txt
```

Now if we find the empty files again, we will see that `file-002.txt` is no longer empty:

```bash
find . -empty
```

We can remove all of the files that we created with this command:

```bash
find . -name "file-*" -delete
rm -f file-* # This will also work
```

There is so much more that you can do with the `find` command, but it goes beyond the scope of this tutorial.

---

## The `history` Command

Used to display the history of commands that you have run.

```bash
history
```
This might only print the last 15 commands from your history if you are in a new updated Mac OS. If that's the case to get all the history in your shell you can type:

```bash
history 1
```

You can also use the `!` to run a command from the history.

```bash
!100
```

This will run the command that is in the 100th position in the history.

---

# For_loops_in_the_shell

---
## Objectives

- Understand the concept of loops in shell scripting.

- Learn how to automate tasks using `for` loops.
  
- Explore the fundamentals and encourage further exploration.

---

Loops are a powerful programming construct that enables us to execute a block of code repeatedly over a set of items. Most programming languages support loops, and they are essential for automating repetitive tasks, eliminating the need to duplicate code.

---

## Syntax of For loop

In shell scripting, a `for` loop follows a specific structure:

```bash
for <variable> in <list>
do
  <block of code>
done
```
- The keywords `for`, `in`, `do`, and `done` are essential components of the `for` loop.
- `<variable` represents each item in the `<list>`/
- `<list>` can be numbers, strings, or files.
- `<block of code>` consists of the commands to be executed for each item in the `<list>`.

---

## How Do Loops Work?
Let's walk through an example:

```bash
for numbers in 1 2 3 4
do
  echo $numbers
done
```

In this example:
- `numbers` is the variable.
- The list  includes numbers 1, 2, 3, and 4.
- The block of code prints each number using `echo` command.

We have this `for` loop written in multiple lines with some indentation for readability; however, it can also be written in a single line or without indentation. You might notice that when you start a `for` loop and press enter after the first line, the second line starts with the `>` sign instead of the regular command prompt `$` or `%`. This `>` simply means that the shell is awaiting further commands to complete it.

---

## Multiple commands in the block of code

Let's expand the block of code in the above example to execute more commands.
This time we will use the `sleep` command to add 1 second delay for the execution of each iteration.

<details>
    <summary>::::sleep command::::</summary>


The `sleep` command suspends execution for an interval of time.

Usage: `sleep [seconds]`

For example, `sleep 1` for a 1-second delay.

</details>


```bash
for numbers in {1..4}
do
  echo $numbers
  sleep 1
done
```

**Note:**
variable names can be anything; you don't have to use `numbers` as a variable name for `1 2 3 4` as in the above two examples. You can replace this variable name: `numbers` with anything, eg., `x` or `i` or any other random letters, words, or even numbers. However, having a meaningful variable name will increase the interpretability of the codes.


---

## Exercises 

### 1. Creating multiple files at once.

Create 10 empty files using the `touch` command.

```bash
touch {1..10}.txt
```

Type `ls` to display the output.

#### Challenge 1:
Use `touch` with a `for` loop to create 10 more text files `{11..20}.txt`

<details>
    <summary>::::Solution::::</summary>

```bash
for numbers in {11..20}
do
  touch ${numbers}.txt
done
```

</details>

Use `ls` to display the output from the above `for` loop.


---

### 2. Setting up a Scenario-1.
Suppose you are a Principal Investigator (PI) in your lab, and you have five new graduate students this year: `Allison, Jeff, Sam, Eunji, and Oskar`. You want to set up a folder for each of your students to share files between the two of you. You also want to create a text file, `Meeting_notes.txt` inside each of your students' folders to record your meeting agendas and notes. Create a folder named `students` on your desktop and prepare the file system inside it using a for loop.

Commands you will be using: `mkdir` and `touch`.

 
```bash
for students in Allison Jeff Sam Eunji Oskar
do
  mkdir ${students}
  touch ${students}/Meeting_notes.txt
done
```

---

#### Challenge 2:

Now you want to send a note to everyone on the meeting day to put their agendas on the file `Meeting_notes.txt`. Write a `for` loop to do it. Your message could include: `Hi <student name>, I am looking forward to our meeting today. Please put your agendas for today's meeting below.` You can also print the date with `date` command `$(date)`.


<details>
    <summary>::::Hints::::</summary>

`\n` indicates a line break.

$(): Commands inside Dollar single parentheses get executed and you get then output gets placed into whatever string you are building.

${}: The dollar braces is for variable interpolation. You use it when normal string interpolation could get weird.

We can use `>` to direct the output from a command to a file. However, redirecting another output of a command to the same file will overwrite the content of the file. So, in order to append a new output/content in the same file, we can use `>>`.

</details>


<details>
    <summary>::::Solution::::</summary>

```bash
for students in Mandy Oskar Jeff Allison Eunji
do
  echo "$(date)\n Hi ${students}! I am looking forward to our meeting today.\n Please put on your agendas for today's meeting below." >> ${students}/meeting_notes.txt
done
```

</details>

---

### 3. Setting up a Scenario 2:

First, let's create three fasta files with the `touch` command.
`file_1.fasta`, `file_2.fasta`, `file_3.fasta`

```bash
touch file_{1..3}.fasta
```
Now insert the following sequences into each file using the `for` loop. You can use wild card `*` to specify the list of fasta files.

```bash
>Sequence1\nACGTAGCTAGCTAGCTAGCTAGCTTAGCTAGCTAGAGCTAGCTAGCTGCTAGCT\n>Sequence2\nGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCAGCTAGCTTAGCTAGGCAGCTAGA\n>Sequence3\nTAGCTAGCTAGCTAGCTAGCTATAGCTAGCTAGCTCTAGCTAGCTAGCTGCTGT
```


<details>
    <summary>::::Hints::::</summary>
  
The wild card `*.fasta` can specify all the files that end with .fasta inside the working directory.

</details>   



<details>
    <summary>::::Solution::::</summary>

```bash
for files in *.fasta
do
  echo ">Sequence1\nACGTAGCTAGCTAGCTAGCTAGCTTAGCTAGCTAGAGCTAGCTAGCTGCTAGCT\n>Sequence2\nGCTAGCTAGCTAGCTAGCTAGCTAGCTAGCAGCTAGCTTAGCTAGGCAGCTAG\n>Sequence3\nTAGCTAGCTAGCTAGCTAGCTATAGCTAGCTAGCTCTAGCTAGCTAGCTGCT" > $files
done
```
</details>

Fasta file usually contains nucleotide or amino acid sequences. We do not usually generate these sequences with codes. These files are generated through a sequencing machine after sequencing the biological samples. For now, let's assume that we received these three fasta files from a sequencing core. 
Now, using a `for` loop, count how many sequences are there in each fasta file. 

Command you will be using: `grep`

<details>
    <summary>::::Hint::::</summary>

The `grep` command can be used to search a specified pattern in the specified file. As we know each fasta sequence has a header line and each header starts with a `>` sign. we can use `grep` with `-c` option to count the occurrence of `>` at the start of the line to get the number of sequences.

</details>

<details>
    <summary>::::Solution::::</summary>
  
```bash
for files in *.fasta
do
  echo $files
  grep -c "^>" $files
done
```
</details>
