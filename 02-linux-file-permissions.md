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

## Command Walkthrough

### 1. Inspect the file

```bash
cd ~/linux-practice
ls -l permissions.txt
whoami
stat permissions.txt
```

These commands identify the current user and inspect the file's permissions, ownership, and metadata.

### 2. Restrict access to the owner

```bash
chmod 600 permissions.txt
ls -l permissions.txt
stat -c '%a %A %n' permissions.txt
```

Expected permission mode: `600` (`-rw-------`).

The owner can read and write the file. Group and other users have no permissions through the file's Unix permission bits.

### 3. Restore read access for group and others

```bash
chmod 644 permissions.txt
ls -l permissions.txt
stat -c '%a %A %n' permissions.txt
```

Expected permission mode: `644` (`-rw-r--r--`).

The owner can read and write the file, while group and other users can read it.

### 4. Inspect the file contents

```bash
cat permissions.txt
```

Expected content:

```text
Learning Linux permissions
```

### 5. Inspect the default permission mask

```bash
umask
umask -S
```

In this exercise, the observed numeric mask was `0022`, and the symbolic output was `u=rwx,g=rx,o=rx`.

The `umask` affects the permissions assigned to newly created files and directories. It removes permissions from the mode requested by the creating application; it does not change permissions on existing files.

## Security Considerations

- Apply the principle of least privilege when choosing file permissions.
- Use `600` for files containing information that should be accessible only to the owner, where appropriate.
- Use `644` only when group and other users are permitted to read the file.
- File permissions are one layer of access control; ownership, directory permissions, ACLs, and other security controls can also affect access.

## Verification Note

The permission modes and `umask` values above reflect the results recorded during this exercise. The command walkthrough provides a repeatable way to inspect and verify them.

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
