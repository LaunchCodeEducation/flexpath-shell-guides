# Windows Command Line

## Introduction

Every modern desktop operating system includes a "shell" or "command line"
application.  This application allows you to navigate the file system and
run tools and utilities in the context of a certain folder.

In Windows, the modern shell application is called **Powershell**.  While
powershell is a powerful tool with several advanced features, it is only
necessary to know a few basic commands for the purposes of this course.

## Launching Powershell

To launch powershell, press the `Windows` key and type `powershell`.  You
should see an application called "Windows Powershell" appear in the search
results.  Click on this application to launch it.

## Working Directory

When you launch powershell, you will be placed in a certain folder.  This
folder is called the "working directory".  The prompt that is displayed in
the powershell window will show you the current working directory.  You can
also view the working directory using the first command that we will learn.
To run a command in powershell, click the window, and type the command.  You
will see the command display next to the prompt as you type it.  When you
are finished typing the command, press `Enter` to run the command.

Let's try running the following command by typing it into the powershell:

```powershell
pwd
```

This command stands for "print working directory".  Once you have typed this
command and pressed `Enter`, you should see the full path to the current
working directory displayed in the powershell window.

The working directory is important because it is the folder that will be
used as the default location for any files that you create or modify, and
it is the folder that will be operated on when you run commands that affect
the file system.  (For example, later you will use the `npm` command to install
packages, and the packages will be installed in the current working directory.)

## Listing Files

To see a list of files in the current working directory, you can use the
following command:

```powershell
ls
```

This command stands for "list".  When you run this command, you will see a
list of files and folders in the current working directory displayed in the
powershell window.

## Changing Directories

To change the current working directory to the root of your hard drive, you
can use the following command:

```powershell
cd /
```
After running this command, you can use the `pwd` command to verify that you
are now in the root directory.  You should see something like `C:\` displayed
in the powershell window.

The slash '/' character in this command refers to the root of the hard drive.

Now that we are in the root directory, let's use the `ls` command to see a
list of files and folders in the root directory.

```powershell
ls
```

You should see a list of files and folders displayed in the powershell window.
The list of files and folders in the root directory will be different on every
computer, but you should see a list of folders like `Users`, `Program Files`,
and `Windows`.


To change the current working directory to the `Users` folder, you can use the
following command:

```powershell
cd /Users/
```

This command changes the current working directory to the `Users` folder.

This time, we specified the full path to the `Users` folder, starting from the
root of the hard drive (`/`) followed by the name of the folder under the root
directory that we want to change to (`Users`).

Now that we are in the `Users` folder, let's use the `ls` command to see a list
of files and folders in the `Users` folder.

```powershell
ls
```

Let's try changint to your documents folder:

```powershell
cd /Users/<your-username>/Documents
```

Replace `<your-username>` with your actual username.  You can use the `ls`
command to see a list of files and folders in the `Documents` folder.

This time, our path started from the root of the hard drive (`/`), followed by
the name of the `Users` folder, followed by another slash (`/`), followed by
the name of your user folder, followed by another slash (`/`), followed by the
name of the `Documents` folder.

Your current working directory is now the `Documents` folder, which is a
folder that is located inside of your user folder, which is located inside of
the `Users` folder, which is located in the root of the hard drive.


### Relative Paths

So far, we have been using **absolute paths** to change directories.  An
absolute path is a path that starts from the root of the hard drive, followed
by the names of folders that you want to navigate to.


You can also use **relative paths** to change directories.  A relative path is
a path that does not start with a slash (`/`).  When you use a relative path,
instead of needing to specify the full path from the root of the hard drive,
you can specify a path that is relative to the current working directory.

First, navigate back to the root of the hard drive:

```powershell
cd /
```

Now, let's navigate back to the `Users` folder using a relative path.  To do
this, we can use the following command:

```powershell
cd Users
```

This command changes the current working directory to the `Users` folder, that
is located within the current working directory.  We can write two more `cd`
commands to navigate to the `Documents` folder:

```powershell
cd <your-username>
cd Documents
```

(Again, replace `<your-username>` with your actual username.)

Each time, we used a relative path to navigate to a folder that is located
within the current working directory.

### Navigating Up

You can also use relative paths to navigate up to the parent directory of the
current working directory.  To do this, you can use the following command:

```powershell
cd ..
```

This command changes the current working directory to the parent directory of
the current working directory.  If you're following along, you should now be
in your user folder (`c:\users\<your-username>`).  You can run pwd to verify
this.

You can chain multiple `..` together to navigate up multiple levels.  For
example, to navigate up two more leves from your user folder to the root of
the hard drive, you can use the following command:

```powershell
cd ../..
```

### Going Home

You can also use a special path called `~` to navigate to your user folder
from anywhere on the hard drive.  To do this, you can use the following
command:

```powershell
cd ~
```

This command changes the current working directory to your user folder.  You
can verify this by running the `pwd` command.

## Creating Directories

To create a new directory in the current working directory, you can use the
following command:

```powershell
mkdir my-new-folder
```

This command creates a new folder called `my-new-folder` in the current
working directory.  You can use the `ls` command to verify that the new
folder was created.

## Removing Directories

To remove a directory in the current working directory, you can use the
following command:

```powershell
rmdir my-new-folder
```

This command removes the folder called `my-new-folder` from the current
working directory.  You can use the `ls` command to verify that the folder
was removed.

## Creating Empty Files

To create a new empty file in the current working directory, you can use the
following command:

```powershell
touch my-new-file.txt
```

This command creates a new empty file called `my-new-file.txt` in the current
working directory.  You can use the `ls` command to verify that the new file
was created.

## Removing Files

To remove a file in the current working directory, you can use the following
command:

```powershell
rm my-new-file.txt
```

This command removes the file called `my-new-file.txt` from the current
working directory.  You can use the `ls` command to verify that the file was
removed.

## Copying Files

First, let's create a new file to copy:

```powershell
touch file1.txt
```

Now, let's copy the file:

```powershell
cp file1.txt file2.txt
```

This command copies the file called `file1.txt` to a new file called
`file2.txt`.  You can use the `ls` command to verify that the new copy of the
file was created.

## Moving Files

First, let's create a new file to move:

```powershell
touch file1.txt
```

Now, let's move the file:

```powershell
mv file1.txt file2.txt
```

This command moves the file called `file1.txt` to a new location and renames
it to `file2.txt`.  You can use the `ls` command to verify that the file was
moved.

## Conclusion

These are the basic commands that you will need to know to navigate the file
system and work with files and folders in the Windows command line.  Throughout
the course, you will use these commands to navigate to the correct folder and
run commands to install packages and run your code.

## Quick Reference

- `pwd` - Print working directory
- `ls` - List files and folders in the current working directory
- `cd <path>` - Change the current working directory to the specified path
- `mkdir <name>` - Create a new directory with the specified name
- `rmdir <name>` - Remove the directory with the specified name
- `touch <name>` - Create a new empty file with the specified name
- `rm <name>` - Remove the file with the specified name
- `cp <source> <destination>` - Copy the file from the source to the destination
- `mv <source> <destination>` - Move the file from the source to the destination
```

