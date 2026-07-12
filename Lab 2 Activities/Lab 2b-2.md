# Lab 2b-2 -- Introduction to Bash Scripting & System Automation 

This activity introduces basic bash scripting and automating system tasks on Linux.

### Directory and File Operations Completed 

```Bash
mkdir LabFiles  // To create LabFiles directory
cd LabFiles
echo "This is a Bash scripting lab" > notes.txt
cat notes.txt   // View note.txt content
cp notes. txt notes2.txt // To duplicate notes.txt to notes2.txt
mv notes2.txt notes3.txt // To rename notes2.txt to notes3.txt
rm notes3.txt // To remove notes3.txt
```

<img width="1906" height="1086" alt="image" src="https://github.com/user-attachments/assets/1f1fc6e4-287a-428e-b8f0-da9708095615" />

Picture shown is the commands inputted.

### Reflection: File System Commands

• What command did you use to create a directory? 

**cd**

• How can you view file content without a GUI editor? 

**cat**

• What is the difference between cp and mv? 

**cp is to duplicate file mv is for renaming file**

### Basic Bash Script Created and Run

I created a script using these commands:

```Bash
nano hello_world.sh
chmod 777 hello_world.sh
./hello_world.sh
```
This is the output of the commands: 

<img width="1857" height="1150" alt="image" src="https://github.com/user-attachments/assets/774f90b8-d99b-46f9-93d2-4dee525a79f1" />

<img width="1763" height="1116" alt="image" src="https://github.com/user-attachments/assets/0132a492-bdb4-44fa-bb39-9f464d120b5d" />

### Reflection: Script Basics

• What is chmod +x for? 

**Allow file execution permission**

• Why is #!/bin/bash used? 

**It tells Linux to use the Bash shell**

• How can you personalize script output?

**By Modifying the echo line**

### Loop and Conditional Script

```Bash
nano system_info.sh
chmof 777 system_info.sh
./system_info.sh
```

This is the input of my commands:

<img width="1724" height="1028" alt="image" src="https://github.com/user-attachments/assets/f1dde401-1bd7-4cff-8a3d-1bea24244b5b" />

This is the terminal input:


<img width="1442" height="892" alt="image" src="https://github.com/user-attachments/assets/5d4d7305-5291-42f3-8383-21c74c3fe06c" />


### Reflection: Loops and Conditionals 

• How does the for loop work? 

**The for loop repeats a block of commands for each value in a specified range.**

• What happens if number > 10? 

**It will show the output "You entered an invalid number!"

• How could invalid input be handled more gracefully? 

**By repeatedly prompting the user until a valid number is entered, instead of terminating after one invalid attempt.**

### System Monitoring Script Created and Run

```Bash
nano resource_monitor.sh
chmod 777 resource_monitor.sh
./resource_monitor.sh
```

<img width="1459" height="869" alt="image" src="https://github.com/user-attachments/assets/5ddca667-a34e-457c-baa0-b870e16623f2" />

The picture above is the inputted commands and the output of resource_monitor

<img width="1347" height="839" alt="image" src="https://github.com/user-attachments/assets/b8e38663-2135-42d5-abe9-d3a81f506d20" />

Picture above is the input for the nano file.

Reflection: Monitoring Automation

• What does free -h show? 

**Displays the system's memory usage in a human-readable format.**

• How can this script be modified to monitor network usage? 

**By adding ip-s to the script**

• Why is automation important for admins?

**It reduces repetitive manual tasks, saves time, minimizes human error, and ensures tasks are performed consistently.**

# Reflection Questions

- What command did you use to create a new directory? **mkdir**

- How can you view the contents of a file without opening it in a GUI? **cat filename.txt**

- What is the purpose of `chmod 777`? **Gives the owner, group, and all other users full read, write, and execute permissions on a file or directory.**

- What does `#!/bin/bash` do at the start of a script? **It tells the OS to use Bash shell**

- What happens when invalid input is entered into a script? **The script checks the input against its validation rules.**

- What output does `free -h` show? **Displays the system's memory usage in a human-readable format**

- How would you monitor network bandwidth in a Bash script? **Using commands such as ip -s link**





















