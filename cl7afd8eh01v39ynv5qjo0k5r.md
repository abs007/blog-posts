# Terminal vs Bash vs Command Line vs Command Prompt

## Terminal 

Also can be called a **terminal emulator**, it emulates what a classic and old school terminal window used to look like. The **terminal** is the program/window that pops up whenever we try to run commands. Key bindings can be changed here. The terminal by itself doesn't know what to do with the input we provide. That is the **shell**'s job.


![Screenshot (57).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653918266620/woBkFD03S.png align="left")

## Bash

Bash is the default **shell** language that is used in **terminals**. It is the shell's job (bash in this case) to interpret the command, run the program that we need to run and then send the output back to the **terminal**. If you don't know what **shell** language you're using, you're most probably using Bash. Though, you can always find that out by typing in ` echo $0 ` in your **command line interface**. Other popular shell scripting languages include zsh(an extension of bash), Powershell, python etc.

![Screenshot (58).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653918429322/GfKcKzKpQ.png align="left")

*Bash is being used here, though you could use other languages too.*

## Command Line/Command Line Interface (CLI)

The **CLI** is the tool that we use for interacting with the computer and typing out our commands. It consists of the command prompt, the cursor and the user inputted command. You can consider the entire line you type in to be an instance of the CLI. The CLI isn't restricted to the language you might be running. You could be running python in another CLI if needed.  

![Screenshot (59).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653918999542/U1kaoGii1.png align="left")

## Command Prompt

Bash (or any other shell scripting language) upon starting will look at the shell's **config** file for the particular configuration that you need. One such thing that you can change is the command prompt. Different users can display what they need. Some might display the current path, some might go for the system time or some might display a bunch of emojis. It's completely up to you. It is sometimes called a **PS1** because we can set the variable `PS1= "Wazzup: "` and temporarily change the prompt to `Wazzup: `

![Screenshot (57).png](https://cdn.hashnode.com/res/hashnode/image/upload/v1653919163976/DC735SCjk.png align="left")

*I configured my prompt to look decorative with the coffee emoji ☕*

Hope you liked the blog :))