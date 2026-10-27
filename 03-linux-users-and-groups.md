# Linux Exercise 03: Users and Groups

## Objective
Practise identifying Linux users and groups, inspecting account records, creating a group, and managing file group ownership and permissions.

## Environment
- Operating system: Ubuntu on Windows Subsystem for Linux (WSL)
- User: `sikafofro`
- Working directory: `/home/sikafofro/linux-practice`

## Commands Practised

| Command | Purpose |
|---|---|
| `whoami` | Display the current username |
| `id` | Display the UID, primary GID, and supplementary groups |
| `groups` | List the groups associated with the current user |
| `getent group` | Look up group records |
| `getent passwd` | Look up user account records |
| `sudo groupadd cloudlearn` | Create a Linux group with administrative privileges |
| `touch` | Create a practice file |
| `sudo chgrp cloudlearn cloud-team.txt` | Assign the file to the `cloudlearn` group |
| `chmod 664 cloud-team.txt` | Grant read/write access to owner and group, and read access to others |
| `ls -l` | Inspect file permissions and ownership |
| `stat` | Inspect file metadata and numeric ownership IDs |

## Verified Results

- Current username: `sikafofro`
- UID: `1000`
- Primary group: `sikafofro`
- Primary GID: `1000`
- `cloudlearn` group created successfully with GID `1501`
- File: `cloud-team.txt`
- File owner: `sikafofro`
- File group: `cloudlearn`
- Final permissions: `0664` (`rw-rw-r--`)

## Command Walkthrough

### 1. Identify the current user and groups

```bash
whoami
id
groups
```

These commands identify the current user, their numeric user and group IDs, and their group memberships.

### 2. Inspect user and group records

```bash
getent passwd sikafofro
getent group cloudlearn
```

`getent` retrieves account and group records from the system's configured identity sources. These commands help verify that the relevant user and group records exist.

### 3. Create and verify the group

```bash
sudo groupadd cloudlearn
getent group cloudlearn
```

The `groupadd` command creates a new group. If the group already exists, check its record rather than attempting to create it again.

The group created during this exercise had GID `1501`.

### 4. Assign group ownership to a file

```bash
touch cloud-team.txt
sudo chgrp cloudlearn cloud-team.txt
ls -l cloud-team.txt
```

The `chgrp` command changes the file's group ownership. The file owner remains `sikafofro`, while its group is changed to `cloudlearn`.

### 5. Set and verify file permissions

```bash
chmod 664 cloud-team.txt
stat -c '%U %G %a %A %n' cloud-team.txt
```

The verified result was:

- Owner: `sikafofro`
- Group: `cloudlearn`
- Permission mode: `0664`
- Symbolic permissions: `-rw-rw-r--`

The owner and group have read/write permission, while other users have read permission.

## Security Considerations

- Use administrative privileges only when necessary.
- Grant group membership according to the user's responsibilities.
- Apply least privilege when setting ownership and permissions.
- Remember that group ownership and permission bits work together to determine access.
- Verify changes with `id`, `getent`, `ls -l`, and `stat`.

## Verification Note

The results above reflect the values recorded during the exercise. The commands provide a repeatable method to inspect account records, group ownership, and file permissions.

**Environment note:** These exercises were performed in Ubuntu on WSL. The same core Linux concepts apply to many Linux servers, including cloud-based environments.

## Key Learnings

- Linux uses UIDs and GIDs to identify users and groups.
- The `sudo` group typically grants permission to execute authorised administrative commands.
- Group ownership can be changed using `chgrp`.
- The `chmod` command controls read, write, and execute permissions.
- Permission mode `664` allows the owner and group to read and write, while others can only read.
- Changing a file's group ownership does not automatically grant write access; permissions must allow it.
- `ls -l` and `stat` help verify changes rather than relying on assumptions.

## Result
Successfully created a test group, assigned it to a practice file, and verified the resulting ownership and permissions in Ubuntu on WSL.

## Next Steps
Practise Linux processes and system monitoring commands.
