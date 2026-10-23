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
