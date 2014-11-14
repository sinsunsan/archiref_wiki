### 
* Scala documentation 
http://www.scala-lang.org/

* Play framework
https://www.playframework.com/

### App structure
```
app                      → Application sources
 └ assets                → Compiled asset sources
    └ stylesheets        → Typically LESS CSS sources
    └ javascripts        → Typically CoffeeScript sources
 └ controllers           → Application controllers
 └ models                → Application business layer
 └ views                 → Templates
build.sbt                → Application build script
conf                     → Configurations files and other non-compiled resources (on classpath)
 └ application.conf      → Main configuration file
 └ routes                → Routes definition
public                   → Public assets
 └ stylesheets           → CSS files
 └ javascripts           → Javascript files
 └ images                → Image files
project                  → sbt configuration files
 └ build.properties      → Marker for sbt project
 └ plugins.sbt           → sbt plugins including the declaration for Play itself
lib                      → Unmanaged libraries dependencies
logs                     → Standard logs folder
 └ application.log       → Default log file
target                   → Generated stuff
 └ scala-2.10.0            
    └ cache              
    └ classes            → Compiled class files
    └ classes_managed    → Managed class files (templates, ...)
    └ resource_managed   → Managed resources (less, ...)
    └ src_managed        → Generated sources (templates, ...)
test                     → source folder for unit or functional tests
```
### Run the app 

sbt Equivalent of grunt

~run / compile when it's ok


http://fr.slideshare.net/brikis98/nodejs-vs-play-framework

### Play templating 

Function definition of the template
2 arguments are available
```scala
@(planId: Int, weekNumber: Int)
```

We load a global datas defined in the app configuration     
**mysite.backend** is the name space
**_** Mean all data files under the name space
```scala
@import mysite.backend.TemplateConfiguration._
```


Data definition 
```scala

@*** Definition of the package **@
package mysite.backend

@*** Definition of the object **@
object TemplateConfiguration {

  @*** Definition of a Map **@

  val translationString: Map[String, String] = Map("blue" -> "bleu",
                                          "red" -> "rouge",
                                          "green" -> "vert")
  @*** Definition of a List **@

  val alimentList: List[String] = List("apple", "steak", "fish")

}
```
