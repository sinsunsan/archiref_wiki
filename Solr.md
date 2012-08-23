How to installing tomcat and Solr on Debian or Ubuntu

## Tomcat

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

<pre><code>
/etc/init.d/tomcat6 start
</code></pre>

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