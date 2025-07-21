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
