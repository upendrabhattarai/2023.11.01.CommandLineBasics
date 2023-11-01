# Crash Course on Introduction to Command Line
## Objectives

- Describe key reasons for learning the command line.
- Discuss common confusion about the Command line, Terminal, and shell.
- Navigate your file system using the command line.
- Learn the basics of working with files and folders.
  
---


## Why learn to use the command line?

<details>
  <summary> **# Greater control**</summary>

    The Graphical user interface (GUI) of an operating system (OS) does make everything look nice, easy, and pretty, however, using the command line is sort of having back-end access to the system. So you can do things that you can't typically do with the GUI. For example, if you are having trouble with your computer, the command line can be a lifesaver to check error logs and run diagnostic tools. You can manage permissions and user access through the command line and perform complex tasks where the command line can be the only way to do it.

</details>

<details>
  <summary> **# Speed and Efficiency**</summary>
  
    Though one of the biggest drawbacks of the command line is its steep learning curve, however, learning to navigate your system through the command line allows you to do things easily and quickly. For example, if you have hundreds or thousands of files to process through a pipeline, it might take hours or even days to manually handle them one by one through GUI, instead, you can automate such repetitive tasks with the command line. The command line makes work less error-prone. you can also alias commonly used command to make it even faster. You don't have to go back and forth between mouse and keyboard. So working with the command line can be much more efficient in many ways.

</details>

<details>
  <summary> **# Access remote servers** </summary>
  
    If you are working with big data like High throughput sequencing data, a lot of times you will need to access high-performance computing clusters for bigger computing power, because your PC won't be able to process those millions of sequencing reads you have. In such case, you need to access remote servers and you can do that with the command line interface.
    
</details>


<details>
  <summary> **# Command line tools**</summary>
  
    There are so many tools especially when it comes to dealing with omics data you simply don't have any GUI options. To install and use those tools you must go through the command line interface. Some tools have more features and parameter options that are not available in their GUI version. eg. BLAST, for which many of the advanced functions are only accessible through the command line.

</details>

---

## Few terminologies:

`Command line` or the `Terminal` is the interface in a machine that allows you to enter commands and get output. `Command line` is mostly used in Windows OS where they call their version of `Terminal` the `command line` or `CMD`. Whereas `Terminal` is the command line interface that is built in Mac OS. Another term we frequently encounter in the command line is the `shell`. It is basically the program behind the command line or command line interface which reads the input and displays the output. Different shells have different capabilities and different ways of entering commands, so you can sort of think of the shell as the operating system of the terminal. Bash is the most common shell program and is usually the default on most Linux and Unix systems and was the default on Mac for a long time, up until recently they switched from bash to `zsh`.

---

## How to access the shell

On a Mac or Linux machine, you can access a shell through a program called "Terminal", which is already available
on your computer. The Terminal is a window into which we will type commands. If you're using Windows,
you'll need to download a separate program to access the shell, like `gitbash`. 
