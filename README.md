# Linux-Bash-Practice
Write ups of all my bash exercises.
6/25/26 - Script practice.

I completed the Linus Shells room in THM.

I wrote the locker script in the exercise as practice after completing the other tasks.  The final task I was given a script with missing information that I needed to fill in.  I wanted to log my flow, mistakes and eventual discovery of the answer.

The file was: flag_hunt.sh I used the nano command to open the file.

The script was:

directory= " "
flag= " "

echo "FLag search in directory: $directory in progress..."
for file in " "/*.log; do
    if grep -q "$flag" "$file"; then
        echo "Flag found in: $(basename "$file")"
  fi
done

I was given two things:
Flag: thm-flag01-script
Directory: /var/log
I was also given a hint to look for double quotes (" ") and fill them with no spaces.

I filled the the directory and the flag with the information given.  The last double quotes was for the file to search.  This is where I was confused.  I kept entering /var/, var/, var and other versions of this.  I even entered the flag file name but nothing worked.  I stepped away several times in frustration because I knew the answer was somewhere in the script I just didn't know what.  I almost gave up and searched for the answer online but I didn't.  Kept at it and read the script over and over.  Finally, it hit me.  I entered in variable just to see if it would work.

"$directory"

I got the right response.  The file that had the key word was "authentication.log" which was the first right answer. The second question asked "Where is the cat sleeping?" This was difficult because I knew it lied in that file.  I tried to use cat authentication.log but it didn't work.  After trying several other things that didn't work I remembered I had to move directories. So I entered cd /var/log. Then I input the "ls" command and saw the file. I then used the "cat" command on the authentication.log file.

That gave me the answer: "The cat is sleeping under the table"

This was the final answer and I completed the Practical Exercise.  I was proud of myself for the following:

1. I didn't quit or give up.
2. I didn't search online and cheat. I kept at it, thinking, and failing until I got it right.
3. I allowed myself the leeway to fail and becuase of that finding it on my own was a greater victory.

I learned alot.
1. The commands: cd, ls, cat, nano, chmod +x "file name", and making sure you input ./ before your script.

This was a great first introduction to script building and I look forward to learning to build more.

07/02/26 - Password Reset Ubuntu Server User

I created an Ubuntu server VM a while ago and forgot the password when I went to SSH into this morning.  Below are the steps I used to reset my password.

1. I accessed the GRUB (BIOS) by holding down shift when starting up the VM.
2. I chose Recovery Mode in the menu.
3. After recovery I choose the root shell so I could give myself rewrite permission instead of read only.
4. Once in the shell I used this command: mount -rw -o remount /   (I didn't know what this meant I looked this up and I learned that this is telling the mounted system to change to read-write permissions and telling the file system to remount instead of mounting another one)
5. Now I had to change my acutal password and thought my user name was "klm23" and was getting the return "klm23 does not exist". I tried different versions until I did a ls command and saw my user name was "kyle"

<img width="1676" height="856" alt="image" src="https://github.com/user-attachments/assets/be736bd5-b5a0-4b10-8eab-9a7e471c4179" />

6. I used the command: passwd username (where the user name is "kyle")
7. I entered the new password twice. Success.
8. I then typed "exit" to go back to the GRUB menu.
9. I selected "resume in normal boot"

<img width="1565" height="880" alt="image" src="https://github.com/user-attachments/assets/adf605c6-8602-45c2-8da8-209853d330e0" />

I entered in the new password and now have access again.

<img width="1528" height="856" alt="image" src="https://github.com/user-attachments/assets/e4608324-170b-4ad8-85d5-dcf2f90998a8" />
