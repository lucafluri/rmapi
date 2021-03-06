# rmapi

ReMarkable Cloud Go API

# What is this?

An attempt to access the ReMarkable Cloud API programmatically.
So far, we expose interactions through a shell. However, you can
also run the shell commands non-interactively as a way to create scripts
that work with your reMarkable data.

![Console Capture](docs/console.gif)

# Install it

Install and build the project:

`go get -u github.com/juruen/rmapi`

# API support

- [x] list files and directories
- [x] move around directories
- [x] download a specific file
- [x] download a directory and all its files and subdiretores recursively
- [x] create a directory
- [ ] delete a file or a directory
- [ ] rename a file or a directory
- [ ] upload a specific file
- [ ] upload a directory and all its files and subdirectories recursively

# Commands

Start the shell by running `rmapi`

## List current directory

Use `ls` to list the contents of the current directory. Entries are listed with `[d]` if they
are directories, and `[f]` if they are files.

## Change current directory

Use `cd` to change the current directory to any other directory in the hiearchy.

## Download a file

Use `get path_to_file` to download a file from the cloud to your local computer.

## Recursively download directories and files

Use `mget path_to_dir` to recursively download all the files in that directory.

E.g: download all the files

```
mget .
```

## Create a directoy

Use `mkdir path_to_new_dir` to create a new directory

# Run command non-interactively

Add the commands you want to execute to the arguments of the binary.

E.g: simple script to download all files from the cloud to your local machine

```bash
$ rmapi mget .
```
