[solr + jetty + drupal]

## Tutorials

http://19thstreetdesign.com/blog/2009.02.04/installing-apache-solr-drupal-6
http://drupal.org/node/1935934
https://www.digitalocean.com/community/articles/how-to-install-apache-tomcat-on-ubuntu-12-04


How to installing tomcat and Solr on Debian or Ubuntu

## Tomcat

### Step One—Install Tomcat
In some tuto it say to install tomcat7, In other 6, we will stay on 6 for now

Install Tomcat6 package

<pre></code>
sudo apt-get install tomcat6
</code/></pre>

By default it runs on port 8080. If you need to change the port 
<pre></code>
edit /etc/tomcat6/server.xml
</code/></pre>

To change the default port here is a tuto
http://www.mkyong.com/tomcat/how-to-change-tomcat-default-port/


Start the server

<pre>```/etc/init.d/tomcat6 start```</pre>


### Step Two—Install Java

We installed the entire Apache Tomcat server on our virtual server in the previous step. Before we can use it, however, we do need to have Java installed on the VPS as well. If you currently do not have java, you can download it quite easily with apt-get.  
 
```
sudo apt-get install default-jdk
```
Once you have Tomcat and Java installed on the virtual private server, all that remains is to start them.


### Step Three—Configure .bashrc

In order to start Tomcat, we need to add it as an environment variable in the /.bashrc file.
```sudo nano ~/.bashrc```

You can add this information to the end of the file:
```
export JAVA_HOME=/usr/lib/jvm/default-java
export CATALINA_HOME=~/path/to/tomcat
```
In my case with default tomcat installation on ubuntu 
```
#https://www.digitalocean.com/community/articles/how-to-install-apache-tomcat-on-ubuntu-12-04
export JAVA_HOME=/usr/lib/jvm/default-java
export CATALINA_HOME=/usr/share/tomcat6
```

It can have
this error 
```
Using CATALINA_BASE:   /usr/share/tomcat6
Using CATALINA_HOME:   /usr/share/tomcat6
Using CATALINA_TMPDIR: /usr/share/tomcat6/temp
Using JRE_HOME:        /usr/lib/jvm/default-java
Using CLASSPATH:       /usr/share/tomcat6/bin/bootstrap.jar
touch: cannot touch `/usr/share/tomcat6/logs/catalina.out': No such file or directory
/usr/share/tomcat6/bin/catalina.sh: 375: /usr/share/tomcat6/bin/catalina.sh: cannot create /usr/share/tomcat6/logs/catalina.out: Directory nonexistent
```
That can be fixed by creating the directory 
```
 mkdir /usr/share/tomcat6/logs 
```

Save and exit out of .bashrc. You can make the changes effective by restarting the bashrc file.
```
. ~/.bashrc
```

### Authorize connexion with the new 8081 port  and IPTABLES
http://www.alsacreations.com/tuto/lire/622-Securite-firewall-iptables.html


Not as easy ! 
What does it mean localhost in a remote server, to be changed by server ip. 
Further more in other tuto found, need to install java, configure some variable in bashr
https://www.digitalocean.com/community/articles/how-to-install-apache-tomcat-on-ubuntu-12-04

In this tuto 
#https://www.digitalocean.com/community/articles/how-to-install-apache-tomcat-on-ubuntu-12-04
export JAVA_HOME=/usr/lib/jvm/default-java
export CATALINA_HOME=/usr/share/tomcat6


and go to http://localhost:8080 
You should see the defaut Tomcat page   


***


## Solr

Download apache Solr http://apache.crihan.fr/dist/lucene/solr/ (version 3.6.x)

<pre></code>
wget http://apache.crihan.fr/dist/lucene/solr/3.6.1/apache-solr-3.6.1.tgz
</code/></pre>

Untar
<pre></code>
tar xvzf apache-solr-3.6.1.tgz
</code/></pre>

Create the $SOLR_HOME directory
<pre><code>
mkdir /opt/solr
mkdir /opt/<PROJECT_NAME>
mkdir /opt/<PROJECT_NAME>/solr
</code></pre>

From the apache-solr directory copy the war file
<pre><code>
sudo cp /path/to/apache-solr-3.6.1/dist/apache-solr-3.6.1.war /opt/solr/<PROJECT_NAME/solr/solr.war
</code></pre>

Note that the war file must be renamed

Copy the solr home from the example folder for Solr download
<pre><code>
sudo cp -r /path/to/apache-solr-3.6.1/example/solr/ /opt/solr/<PROJECT_NAME>
</code></pre>

Create the data directory
<pre><code>
sudo mkdir /opt/solr/<PROJECT_NAME>/solr/data
</code></pre>
Change the permission for the tomcat6 user
<pre><code>
sudo chown tomcat6: -R /opt/solr/<PROJECT_NAME>/solr/data
</code></pre>

Create your context :
<pre><code>
edit /etc/tomcat6/Catalina/localhost/<PROJECT_NAME>.xml
</code></pre>

and add:

```
<code xml>
    code class="xml">
    <?xml version="1.0" encoding="utf-8"?>
    <Context docBase="/opt/solr/<PROJECT_NAME>/solr.war" debug="0" crossContext="true">
    <Environment name="solr/home" type="java.lang.String" value="/opt/solr/<PROJECT_NAME>/solr" override="true"/>
    </Context>
</code>
 ```
<pre>
restart tomcat
</pre>
<pre>
/etc/init.d/tomcat6 restart
</pre>

You are done. You should have the admin of Solr here
localhost:8080/<project_name>/admin