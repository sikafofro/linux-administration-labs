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
