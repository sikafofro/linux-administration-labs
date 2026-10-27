# Linux Exercise 01: Filesystem Navigation

## Objective
Practise essential Linux filesystem navigation and file-management commands using Ubuntu on Windows Subsystem for Linux (WSL).

## Environment
- Operating system: Ubuntu on WSL
- Working directory: `/home/sikafofro/linux-practice`

## Commands Practised

| Command | Purpose |
|---|---|
| `pwd` | Display the current working directory |
| `ls` | List files and directories |
| `ls -la` | Display detailed listings, including hidden files |
| `mkdir -p` | Create a directory |
| `cd` | Change the current directory |
| `touch` | Create an empty file |
| `echo` | Write text to a file |
| `cat` | Display file contents |
| `cp` | Copy a file |
| `mv` | Rename or move a file |
| `find` | Search for files by name |

## Practical Tasks Completed

1. Checked the current directory using `pwd`.
2. Listed visible and hidden files.
3. Created the `linux-practice` directory.
4. Created `notes.txt` and wrote text into it.
5. Verified file contents using `cat`.
6. Created a copy using `cp`.
7. Renamed the copy to `backup.txt` using `mv`.
8. Located `notes.txt` using `find`.
9. Verified that the backup retained the original text.

## Command Walkthrough

The following examples demonstrate the core commands used during this exercise.

### 1. Inspect the working directory

```bash
pwd
ls -la
```

- `pwd` prints the current working directory.
- `ls -la` lists visible and hidden entries with detailed file information.

### 2. Create a directory and a file

```bash
mkdir -p ~/linux-practice
cd ~/linux-practice
touch notes.txt
echo "Linux filesystem practice" > notes.txt
```

The `mkdir -p` command creates the directory if needed. The `touch` command creates an empty file, and `echo` with `>` writes text to the file, replacing existing contents.

### 3. Read and copy the file

```bash
cat notes.txt
cp notes.txt notes-copy.txt
```

`cat` displays the file contents, while `cp` creates a separate copy.

### 4. Rename the copy

```bash
mv notes-copy.txt backup.txt
```

The `mv` command renames the copied file to `backup.txt`.

### 5. Locate and verify the files

```bash
find ~/linux-practice -name "notes.txt"
cat notes.txt
cat backup.txt
```

The `find` command searches for the specified filename. Reading both files allows their contents to be compared.

**Verification note:** These commands are reproducible examples of the documented workflow. Record the actual terminal output separately if you want to include execution evidence.

## Key Learnings

- Linux directory and file names must match exactly.
- `~` represents the user's home directory.
- `.` represents the current directory, while `..` represents its parent.
- `ls -la` reveals hidden files and detailed file metadata.
- `cp` creates a copy, whereas `mv` can rename or move a file.
- The `>` redirection operator replaces a file's existing contents.
- Verifying command output helps identify and resolve errors.

## Result
Successfully completed the filesystem navigation and basic file-management exercises in Ubuntu on WSL.

## Next Steps
Practise Linux file permissions, ownership, and user management in the next lab.
