# Practice in the Terminal

## The Command Line
A command line, or terminal, is a text based interface to the system. You are able to enter commands by typing them on the keyboard and feedback will be given to you similarly as text.

The command line typically presents you with a prompt. As you type, it will be displayed after the prompt. Most of the time you will be issuing commands

Opening a terminal is fairly easy. I can't tell you exactly how to do it as every system is different but here are a few places to start looking.

If you're on a Mac then you'll find the program Terminal under Applications -> Utilities. An easy way to get to it is the key combination 'command + space' which will bring up Spotlight, then start typing Terminal and it will soon show up. If on Linux then you will probably find it in Applications -> System or Applications -> Utilities. Alternatively you may be able to 'right-click' on the desktop and there may be an option 'Open in terminal'. If you are on Windows and intend to remotely log into another machine then you will need an SSH client. A rather good one is Putty (free).

# Basic Navigation
Many tasks rely on being able to get to, or reference the correct location in the system. As such, this stuff really forms the foundation of being able to work effectively in Linux.

pwd Print Working Directory - ie. Where are we currently. ls List the contents of a directory. cd Change Directories - ie. move to another directory. Relative path A file or directory location relative to where we currently are in the file system. Absolute path A file or directory location in relation to the root of the file system.

# More About Files
A file extension is normally a set of 2 - 4 characters after a full stop at the end of a file, which denotes what type of file it is. The following are common extensions:

file.exe - an executable file, or program. file.txt - a plain text file. file.png, file.gif, file.jpg - an image.

file obtain information about what type of file a file or directory is. ls -a List the contents of a directory, including hidden files.
# Manual Pages
The manual pages are a set of pages that explain every command available on your system including what they do, the specifics of how you run them and what command line arguments they accept.

man Look up the manual page for a particular command. man -k Do a keyword search for all manual pages containing the given search term. / Within a manual page, perform a search for 'term' n After performing a search within a manual page, select the next found item.
# File Manipulation
mkdir Make Directory - ie. Create a directory. rmdir Remove Directory - ie. Delete a directory. touch Create a blank file. cp Copy - ie. Copy a file or directory. mv Move - ie. Move a file or directory (can also be used to rename). rm Remove - ie. Delete a file.
# Cheat Sheet
It contains most of the important commands and their use

[Cheat Sheet](https://ryanstutorials.net/linuxtutorial/cheatsheet.php)
