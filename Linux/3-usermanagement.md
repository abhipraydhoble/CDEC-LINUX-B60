# Types of Users in Linux


## 1. $${\color{red} \textbf {Root User}}$$

- The root user is the superuser in Linux with unrestricted access to the entire system.
- They can perform any administrative task, including creating and deleting users, modifying files, and configuring the system.
- user id is 0

**Common Commands for Root User:**
```bash
# Switch to root user
sudo -i
````

**Execute a command as root**
````
sudo <command>
````

## 2. $${\color{blue} \textbf {System Users}}$$
- These are service accounts created by the system to manage and run specific processes or services.
- Do not have login shells by default.
- Limited privileges, ensuring security for system services.
- user id ranges from 1 - 999

  
## 3. $${\color{green} \textbf {Local User}}$$
- These are standard users created for daily tasks and operations.
- Each user has their own home directory (e.g., /home/username) and specific permissions.
- user id 1000 - 65535

  
#### Add a new user

````
adduser tony
````
or 

note: using useradd command home dir is not created
````
useradd <username>
````
use
````
useradd-m username
````
#### Set or change a user password
````
passwd <username>
````
#### Delete User
````
userdel -r username
````
#### List All Users
````
cat /etc/passwd
```` 
#### Important Files for Users

## /etc/passwd
- Stores user account information
````steve:x:1001:1001:Steve User:/home/steve:/bin/bash````

#### Fields in `/etc/passwd`  

1. **Username** – The name of the user account.  
2. **Password Placeholder** – Typically `x`, indicating the password is stored in `/etc/shadow`.  
3. **User ID (UID)** – A unique identifier assigned to the user.  
4. **Group ID (GID)** – The primary group associated with the user.  
5. **User Info (Comment Field)** – Additional information, such as the full name of the user.  
6. **Home Directory** – The default directory for the user.  
7. **Login Shell** – The shell assigned to the user (e.g., `/bin/bash`).  


## /etc/shadow
1. Username
2. Encrypted Password
3. Last time password change
4. Min days between password change
5. Max days between password change
6. Warning days
7. Inactive days
8. Account Expiry
9. Future Use
- Stores encrypted password hashes and metadata for password policies.

# change pass policy

| Command                         | Description                                                   |
|----------------------------------|---------------------------------------------------------------|
| `chage -l username`              | List current password aging info for the user.                |
| `chage -M 30 username`           | Set maximum number of days between password changes to 30.    |
| `chage -m 7 username`            | Set minimum number of days between password changes to 7.     |
| `chage -W 5 username`            | Set number of days of warning before password expires (5).    |
| `chage -I 10 username`           | Set account inactive after 10 days of password expiration.    |
| `chage -E 2025-07-1 username`    | Set account expiration date.                                  |





# $${\color{magenta} \textbf {Group Management}}$$

**Create a Group**
````
groupadd avengers
````

**Important Files for Groups**

### **Fields in `/etc/group`**  

1. **Group Name** – The name of the group (e.g., `avengers`).  
2. **Password Placeholder** – Usually `x`, meaning the actual password (if any) is stored in `/etc/gshadow`.  
3. **Group ID (GID)** – A unique numerical ID for the group.  
4. **Group Members** – A comma-separated list of users in the group.  

### **Fields in `/etc/gshadow`** 


1. **Group Name** – The name of the group (e.g., avengers).
2. **Encrypted Password** – If a group has a password, it is stored here. (! or * means no password).
3. **Group Administrators** – Users who can manage the group.
4. **Group Members** – Regular users in the group.



**Add a User to a Group**
````
usermod -aG groupname username
example:
usermod -aG avengers natasha
````
````
gpasswd -a username groupname
example:
gpasswd -a steve avengers
````
**Remove a User from a Group**
````
gpasswd -d steve avengers
````

**Add Multiple Users to a Group**
- note: this will remove previous users
````
gpasswd -M steve,thor,bruce avengers
````
**Remove a User from a Group**
````
gpasswd -d bruce avengers
````

**Assign an Admin to a Group**
````
gpasswd -A steve avengers
````
**Remove Admin from a Group**
````
gpasswd -A '' avengers
````

**Delete a Group**
````
groupdel -f avengers
````
