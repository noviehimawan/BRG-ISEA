# Lab 1b-3 -- File Search, Analysis & Archiving in Linux 

This lab activity uses command-line toold to locate, inspect, and search through test files.

### Archive Extracted Successfully

I downloaded the file in `.zip` so I had to extract then create TAR archive and compress it.

<img width="1600" height="504" alt="image" src="https://github.com/user-attachments/assets/157db822-5210-476f-b67e-31fe69bc8aeb" />

Then continued with `bunzip2 1b-3-Gutenberg.tar.bz2` and `tar-xvf 1b-3-Gutenberg.tar`

### File Listing of Extracted Directory 

I used `ls -l` to show contents of where Gutenberg extracted to.

<img width="1600" height="770" alt="image" src="https://github.com/user-attachments/assets/9a9d6be7-26c7-46e9-8678-36f53ba9f316" />

### Filename Search Demonstrated

I used `find ./1b-3-Gutenberg -name "*.txt"`

<img width="1600" height="868" alt="image" src="https://github.com/user-attachments/assets/ee43bea8-20e7-43b6-973a-d076d62b71b3" />

### Text Search via Grep

I used `grep -r "Ishmael"` to demonstrate file search. I used Ishmael instead of verdigris to demonstrate if the string exists.

<img width="1600" height="972" alt="image" src="https://github.com/user-attachments/assets/b66f091a-17c6-4089-acf6-a719962c3e6e" />

### Contextual Text Search

This is the activity demonstrating contextual text search. Since I have no content match to "Next day there was a surprise for Jack", there was no output given.

<img width="1600" height="160" alt="image" src="https://github.com/user-attachments/assets/5a8ef7ee-b7ff-4f06-9e25-6f8434c0a68d" />

### Date-Based File Searches

This activity is about demonstrating file search based on creation/modification date. I used `find . -type f -printf '%T+ %p\n' | sort | sed -n '3p'` it sorts the oldest being the first and only print the 3rd line.

<img width="1600" height="738" alt="image" src="https://github.com/user-attachments/assets/3d693173-cdcd-4bf3-aee2-5bc3963a919c" />


### Size-Based File Searches 

This activity is demonstrating file search based on file size. The commands I used were:

```Bash
find . -type f -size 255258c -exec ls -lh {} \;
find . -type f -size +512k -exec ls -lh {} \;
```

<img width="1600" height="940" alt="image" src="https://github.com/user-attachments/assets/1bafd949-0a9b-4977-99f6-813ca92b576d" />

### Largest Files Found

This activity is demonstrating largest file found in the file  by using this command `du -a ./Gutenberg | sort -nr | head`

<img width="1086" height="351" alt="image" src="https://github.com/user-attachments/assets/4abf2b25-4636-4661-b3e9-029c02afb9ac" />

### Text Frequency Analysis Performed 


I tested the text frequency using `sed -e 's/\s/\n/g' < test.txt`

<img width="1600" height="1054" alt="image" src="https://github.com/user-attachments/assets/6401943c-8f5c-4c10-8348-cea3f4038fe9" />

### Answers to Questions Provided

How many times does the string “verdigris” appear? (enter a number only) 0

- What is the surname of the author of the filename “1107.txt”? (case sensitive) NIL

- What is the surname of the author of the file that is exactly 255258 bytes? (case sensitive) NIL

- What is the filename of the file with the 3rd oldest creation date? twocities.txt

- Find the word that follows the text: “Next day there was a surprise for Jack” (Case-sensitive, no spaces) NIL

# Reflection

During this activity, I found grep to be the most useful command because it quickly searched for specific text within multiple files. These search tools are valuable in cybersecurity investigations as they help locate important information, suspicious files, or keywords efficiently. I also learned that scripting can automate repetitive search tasks, saving time and reducing errors. One limitation I encountered was that grep and find require the correct syntax and file paths, and searching large directories can sometimes produce too much output, making it harder to identify the required information.








