<img width="515" alt="Screen Shot 2023-10-04 at 5 17 09 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/55a1a1f7-9315-4d36-95f8-0ea1262dad88">
### Refactored Assignment on Unix Commands

#### Introduction to Basic Unix Commands: `cd`, `ls`, `cat`
- **`cd`**: Executing `cd` without any arguments doesn't change the directory because I am already in the home directory. We don't face an error, but nothing changes.
- **`ls`**: Running `ls` displays 'lecture 1' as the top-level directory within the home directory. We don't face an error it lists the directories within the home directory. 
- **`cat`**: Since no arguments are provided, `cat` waits for input. I used `Ctrl+C` to exit the command. Here we face an error in the sense that there are no arguments provided so we can't move foward. 

#### Navigating to Specific Directories
- **`cd` with Path**: Using `cd` followed by the path to 'lecture 1' changes the working directory from 'home' to 'lecture 1'. We face no error here as lecture 1 does exist.
- **`ls` with Path**: Executing `ls` with the path to 'lecture 1' lists 'messages' as the highest-level directory within 'lecture 1'. This also faces no error. 
- **`cat` with Directory Path**: Running `cat` with the path to 'lecture 1' returns an error message indicating that it is a directory. Here we face an error as we cannot cat directories. 

#### Working with Text Files
- **`cd` to Non-Directory**: Attempting to `cd` into 'en-ur.txt' returns an error because it is not a directory. We cannot navigate directory to a txt file, the method to do so would be to enter the directory that txt file exists in. 
- **`ls` with File Path**: Using `ls` with the path to 'en-ur.txt' simply lists the same path, confirming the file exists.
- **`cat` with File Path**: Executing `cat` with the path to 'en-ur.txt' displays its content, which is "Hello World" translated into Urdu, but written in Latin script instead of Arabic.

This concise breakdown provides a clearer understanding of how to use these fundamental Unix commands for directory navigation and file manipulation.
