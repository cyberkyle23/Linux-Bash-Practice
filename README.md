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
