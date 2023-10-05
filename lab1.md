<img width="515" alt="Screen Shot 2023-10-04 at 5 17 09 PM" src="https://github.com/affaan-m/cse15l-lab-reports/assets/124439313/55a1a1f7-9315-4d36-95f8-0ea1262dad88">
### Refactored Assignment on Unix Commands

#### Introduction to Basic Unix Commands: `cd`, `ls`, `cat`
- **`cd`**: Executing `cd` without any arguments doesn't change the directory because I am already in the home directory.
- **`ls`**: Running `ls` displays 'lecture 1' as the top-level directory within the home directory.
- **`cat`**: Since no arguments are provided, `cat` waits for input. I used `Ctrl+C` to exit the command.

#### Navigating to Specific Directories
- **`cd` with Path**: Using `cd` followed by the path to 'lecture 1' changes the working directory from 'home' to 'lecture 1'.
- **`ls` with Path**: Executing `ls` with the path to 'lecture 1' lists 'messages' as the highest-level directory within 'lecture 1'.
- **`cat` with Directory Path**: Running `cat` with the path to 'lecture 1' returns an error message indicating that it is a directory.

#### Working with Text Files
- **`cd` to Non-Directory**: Attempting to `cd` into 'en-ur.txt' returns an error because it is not a directory.
- **`ls` with File Path**: Using `ls` with the path to 'en-ur.txt' simply lists the same path, confirming the file exists.
- **`cat` with File Path**: Executing `cat` with the path to 'en-ur.txt' displays its content, which is "Hello World" translated into Urdu, but written in Latin script instead of Arabic.

This concise breakdown provides a clearer understanding of how to use these fundamental Unix commands for directory navigation and file manipulation.
