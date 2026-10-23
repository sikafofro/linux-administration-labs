# Linux Exercise 02: File Permissions

## Objective
Practise inspecting and changing Linux file permissions, identifying the current user, and examining file metadata and default permission masks.

## Environment
- Operating system: Ubuntu on Windows Subsystem for Linux (WSL)
- Working directory: `/home/sikafofro/linux-practice`
- Practice file: `permissions.txt`

## Commands Practised

| Command | Purpose |
|---|---|
| `ls -l` | Inspect file permissions and ownership |
| `chmod 600 permissions.txt` | Give the owner read/write access only |
| `chmod 644 permissions.txt` | Give the owner read/write access and group/others read access |
| `cat permissions.txt` | Display file contents |
| `stat permissions.txt` | Inspect file metadata, ownership, size, and permissions |
| `whoami` | Identify the current user |
| `umask` | Display the numeric default permission mask |
| `umask -S` | Display the symbolic permission mask |

## Practical Results

- Created `permissions.txt` containing `Learning Linux permissions`.
- Verified the initial permissions using `ls -l`.
- Changed permissions to `600` and verified the result.
- Restored permissions to `644` and verified the result.
- Used `cat` to confirm that the file contents remained readable.
- Used `stat` to verify mode `0644`, ownership, and file size.
- Used `whoami` to confirm the current user was `sikafofro`.
- Ran `umask` and observed `0022`.
- Ran `umask -S` and observed `u=rwx,g=rx,o=rx`.

## Key Learnings

- Linux permissions control read, write, and execute access.
- Numeric permission values are read = 4, write = 2, and execute = 1.
- `600` grants the owner read/write access and removes permissions for group and others.
- `644` grants the owner read/write access and group/others read access.
- `umask` determines which permissions are removed from the default mode requested by an application.
- Least-privilege permissions help reduce unnecessary access to files.

## Result
Successfully practised Linux file permission changes, metadata inspection, user identification, and umask inspection in Ubuntu on WSL.

## Next Steps
Practise Linux file ownership, groups, and user management.
