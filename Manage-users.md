## Links 

* Add a new Linux user   
http://doc.ubuntu-fr.org/adduser

* Add a user to a group   
http://www.cyberciti.biz/faq/howto-linux-add-user-to-group/

* Configure sudoers   
https://help.ubuntu.com/community/Sudoers

## Commands

* Create a user rue89 and add it to the group sudo   
<pre>useradd -G sudo rue89</pre>

* Add an existing user (graymond) to an existing group (payroll)   
<pre>sudo usermod -a -G payroll graymond</pre>
