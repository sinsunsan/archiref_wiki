http://www.howtogeek.com/howto/ubuntu/add-a-user-on-ubuntu-server/

Create a slucas user with its home directory 
```
useradd -m slucas 
```

Edit sudoers to add this user right to sudo 
https://help.ubuntu.com/community/Sudoers

// Create the admin group (refered in the default sudoers file
groupadd admin

// Add slucas to the admin group
usermod -a -G admin slucas