# Crash Course on Introduction to Command Line
## Objectives

- Describe key reasons for learning the command line.
- Discuss common confusion about the Command line, Terminal, and shell.
- Navigate your file system using the command line.
- Learn the basics of working with files and folders.
  
---

## Why learn to use the command line?

<details>
  <summary> Greater control</summary>

    The Graphical user interface (GUI) of an operating system (OS) does make everything look nice, easy, and pretty, however, using the command line is sort of having back-end access to the system. So you can do things that you can't typically do with the GUI. For example, if you are having trouble with your computer, the command line can be a lifesaver to check error logs and run diagnostic tools. You can manage permissions and user access through the command line and perform complex tasks where the command line can be the only way to do it.


</details>

<details>
  <summary> Speed and Efficiency</summary>
  
    Though one of the biggest drawbacks of the command line is its steep learning curve, however, learning to navigate your system through the command line allows you to do things easily and quickly. For example, if you have hundreds or thousands of files to process through a pipeline, it might take hours or even days to manually handle them one by one through GUI, instead, you can automate such repetitive tasks with the command line. The command line makes work less error-prone. you can also alias commonly used command to make it even faster. You don't have to go back and forth between mouse and keyboard. So working with the command line can be much more efficient in many ways.

</details>


<details>
  <summary> Access remote servers</summary>
  
    If you are working with big data like High throughput sequencing data, a lot of times you will need to access high-performance computing clusters for bigger computing power, because your PC won't be able to process those millions of sequencing reads you have. In such case, you need to access remote servers and you can do that with the command line interface.
    
</details>


<details>
  <summary> Command line tools</summary>
  
    There are so many tools especially when it comes to dealing with omics data you simply don't have any GUI options. To install and use those tools you must go through the command line interface. Some tools have more features and parameter options that are not available in their GUI version. eg. BLAST, for which many of the advanced functions are only accessible through the command line.

</details>

---

## Few terminologies:

`Command line` or the `Terminal` is the interface in a machine that allows you to enter commands and get output. `Command line` is mostly used in Windows OS where they call their version of `Terminal` the `command line` or `CMD`. Whereas `Terminal` is the command line interface that is built in Mac OS. 
`Shell` is basically the program behind the command line interface which reads the input and displays the output. So it is called `interpreter`. `Bash` is the most common shell program and is usually the default on most Unix/Linux systems and was the default on Mac for a long time, up until recently they switched from `bash` to `zsh`.

---

## How to access the shell

On a Mac or Linux machine, you can access a shell through "Terminal", which is already available on your computer. If you're using Windows, you'll need to download a separate program to access the shell, like `Git Bash`. 

---

## Key Commands & Navigation

Before we look at some common commands, I just want to note a few keyboard commands that are very helpful:

- `Up Arrow`: Will show your last command
- `Down Arrow`: Will show your next command
- `Tab`: Will auto-complete your command
- `Ctrl + L`: Will clear the screen
- `Ctrl + C`: Will cancel a command
- `Ctrl + R`: Will search for a command
- `Ctrl + D`: Will exit the terminal

---

### Manual Command

On Linux and Mac, the `man` command is used to show the **manual** of any command that you can run in the terminal. So if you want to know more about the `ls` command, you could run:

```bash
  man ls
```

Unfortunately, if you are on Windows and using Git Bash, the `man` command is not included, however, you can just type the command that you want to know more about and then `--help` and you will get similar info:

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

Commands to navigate your file system are very important. You will be using them all the time. You won't remember every single command that you use, but these are the ones that you should remember.

| Command                             | Description                                                                       |
| ----------------------------------- | --------------------------------------------------------------------------------- |
| pwd                                 | Lists the path to the working directory                                           |
| ls                                  | List directory contents                                                           |
| ls -a                               | List contents including hidden files (Files that begin with a dot)                |
| ls -l                               | List contents with more info including permissions (long listing)                 |
| ls -r                               | List contents reverse order                                                       |
| cd                                  | Change directory to home                                                          |
| cd [dirname]                        | Change directory to specific directory                                            |
| cd ~                                | Change to home directory                                                          |
| cd ..                               | Change to parent directory                                                        |
| cd -                                | Change to previous directory (which could be different than the parent of course) |
| find [dirtosearch] -name [filename] | Find location of a program                                                        |

Of course, you can group flags together. For example, if I want to see more info and view hidden files, I could do `ls -l -a` and even shorten it to `ls -la`.

---

## Modifying Files & Directories

| Command                     | Description                                         |
| --------------------------- | --------------------------------------------------- |
| mkdir [dirname]             | Make directory                                      |
| touch [filename]            | Create file                                         |
| rm [filename]               | Remove file                                         |
| rm -i [filename]            | Remove directory, but ask before                    |
| rm -r [dirname]             | Remove directory                                    |
| rm -rf [dirname]            | Remove directory with contents                      |
| rm ./\*                     | Remove everything in the current folder             |
| cp [filename] [dirname]     | Copy file                                           |
| mv [filename] [dirname]     | Move file                                           |
| mv [dirname] [dirname]      | Move directory                                      |
| mv [filename] [filename]    | Rename file or folder                               |
| mv [filename] [filename] -v | Rename Verbose - print source/destination directory |

We can also do multiple commands at once with the `&&` operator:

```bash
cd test2 && mkdir test3
```
---

## Right angle bracket >

This symbol tells the system to output results into whatever you specify next. The target is usually a filename. You can use this symbol by itself to create a new file:

```bash
> [filename]
```

When you are done, hit `ctrl+D`

---

## The `cat` (concatenate) Command

The cat command is a very common command and allows you to create single or multiple files, view content of a file, concatenate files and redirect output in terminal or files.

The most common thing I use it for is to display the contents of a file:

```bash
  cat [filename]
```

You can also view the contents of multiple files:

```bash
  cat [filename] [filename]
```

You can also create a file using the `cat` command:

```bash
  cat > [filename]
```

This will open up a new file and you can start typing. When you are done, you can press `Ctrl + D` to save and exit.

You can also append to a file:

```bash
  cat >> [filename]
```

This will open up the file and you can start typing. When you are done, you can press `Ctrl + D` to save and exit.

You can use it to show line numbers:

```bash
  cat -n [filename]
```

There are other uses as well, but as you can see, the `cat` command is very powerful.

---

## The `less` Command

The `less` command is used to view the contents of a file. It is similar to the `cat` command, but it allows you to scroll up and down.

```bash
  less [filename]
```

To exit the `less` command, just press `q`.

---

## The `echo` Command

The `echo` command is used to display messages, or to create and write to files. It is similar to the `cat` command, but it is used to display a single line of text.

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

## The `grep` Command

The `grep` command is used to search for a text pattern in a file. It is very powerful and can be used to search for a string or regular expression in a file or set of files.

```bash
  grep [searchterm] [filename]
```

You can also search for a string in multiple files:

```bash
  grep [searchterm] [filename] [filename]
```

There are a lot more things that you can do with the `grep` command, but it's a but more advanced.
---


## The `find` command

The `find` command is extremely powerful and is used to find the location of files and directories based on conditions that you specify.

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

```
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

## Piping
Piping is very powerful. It is a way of redirecting standard output to another destination, such as another file. Let's actually use the find command to find a list of files and then pipe them into a new file.

First, we'll create 10 files:

```bash
touch file-{001..010}.txt
```

Now, let's pipe the result from our find into a new file named `output.txt`

```bash
find . -name "file-0*" > output.txt
```

You can see the results now in the new file:

```bash
cat output.txt
```

---


## The `history` Command

Used to display the history of commands that you have run.

```bash
  history
```

You can also use the `!` to run a command from the history.

```bash
  !100
```

This will run the command that is in the 100th position in the history.
