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
