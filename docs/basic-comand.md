---
layout: default
title: Basic Commands
nav_order: 2
---
# Basic Commands

{: .no_toc }

<details open markdown="block">
  <summary>
    Table of contents
  </summary>
  {: .text-delta }
- TOC
{:toc}
</details>

---

### Uninstall a Package

To remove a application compleatly use `apt purge` command.

```console
sudo apt purge --auto-remove packagename
```
---

### System Monitor Tools

To monitor your system you can use [Glances](https://nicolargo.github.io/glances/), to install it:

```console
sudo apt install glances
```

To watch the system performance just hit `glances` on your terminal:

```console
glance
```

---

### Copy, Move, Make File, Rename File, Make Directory

To copy use `cp` command:

```console
cp old_file_name <Space> new_file Name
```

To move use `mv` command:

```console
mv old_file_name <Space> new_file Name
```

To make new file use `touch` command:

```console
touch file_name
```

To rename file use `mv` command:

```console
mv old_file_name <Space> new_file Name
```

To make new directory use `mkdir` command:

```console
mkdir directory_name
```

---

### Check IP Address

To check your IP Address use following command:

```console
ip addr
```

---

### Make an User
To make a new user
```console
sudo adduser ftpuser
```
### Steps to Add a User to the `sudo` Group:

1. **Run the following command to add the user to the `sudo` group**:

   ```bash
   sudo usermod -aG sudo username
   ```

   Replace `username` with the actual username of the user you want to add.

   - The `-aG` flag adds the user to the group (`sudo` in this case) without removing them from any other groups they are in.

2. **Verify the User is in the `sudo` Group**:
   After adding the user, you can verify that they are in the `sudo` group by running:

   ```bash
   groups username
   ```

   This will show all groups the user is part of. Look for `sudo` in the list.

3. **Switch to the User Account (Optional)**:
   To test if the user has `sudo` privileges, you can switch to that user:

   ```bash
   su - username
   ```

4. **Test the `sudo` Privileges**:
   Now, try running a command with `sudo`:

   ```bash
   sudo whoami
   ```

   You should see the output `root` if the user has been successfully added to the `sudoers` list.

---
### Change TimeZone
To change the time zone on an Ubuntu server, follow these steps:

1. **Check the current time zone:**
   ```bash
   timedatectl
   ```

2. **List available time zones:**
   ```bash
   timedatectl list-timezones
   ```

   You can scroll through the list or use `grep` to search for a specific time zone:
   ```bash
   timedatectl list-timezones | grep <Region>
   ```

   For example, to search for time zones related to "America":
   ```bash
   timedatectl list-timezones | grep America
   ```

3. **Set the desired time zone:**
   Use the `timedatectl set-timezone` command followed by the chosen time zone.
   ```bash
   sudo timedatectl set-timezone <Your_Time_Zone>
   ```

   Example:
   ```bash
   sudo timedatectl set-timezone America/New_York
   ```

4. **Verify the change:**
   After setting the time zone, verify it using:
   ```bash
   timedatectl
   ```

That's it! Your Ubuntu server will now use the new time zone.

---
###Cron Job Setup

To create a cron job in Ubuntu, follow these steps:

### 1. Open the Crontab
To edit the cron jobs for your user, open the crontab with this command:

```bash
crontab -e
```

If it's your first time, it may ask you to choose an editor. You can select your preferred one (e.g., nano, vim).

### 2. Add a Cron Job
Cron jobs are written in the following format:

```bash
* * * * * /path/to/script_or_command
```

The five asterisks (`* * * * *`) represent the schedule for running the job:

- **First**: Minute (0 - 59)
- **Second**: Hour (0 - 23)
- **Third**: Day of the month (1 - 31)
- **Fourth**: Month (1 - 12)
- **Fifth**: Day of the week (0 - 7) (0 or 7 is Sunday)

For example, if you want to run a script every day at 3:30 AM, you would add:

```bash
30 3 * * * /path/to/your/script.sh
```

### 3. Save and Exit
After adding the job, save the file (in nano, it's `CTRL+O` to write out and `CTRL+X` to exit).

### 4. Verify the Cron Job
You can list your cron jobs with this command:

```bash
crontab -l
```

### Example
If you want to run a backup script (`backup.sh`) every day at 2 AM, your cron entry would look like this:

```bash
0 2 * * * /home/user/backup.sh
```

This would run `backup.sh` daily at 2:00 AM.
