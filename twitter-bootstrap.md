http://getbootstrap.com/css/#grid

A twitter bootstrap playground 
http://bootsnipp.com/

#### Containers 

* container is a wrapper for fixed width site 
* container is a wrapper for fluid width site

### Modal 

There is a fix to twbs3 modal 
http://jschr.github.io/bootstrap-modal/bs3.html
that extend core twbs3 modal
It 
- allow to set a spinner 
- disable background scrolling

### Afix :    
an element of the page (generally a menu bar) get fixed, when we scroll  

* Good demo : http://www.bootply.com/okZQLf2gat
The css is quite simple 

```` css
.affix {
  position: fixed;
  -webkit-transform: translate3d(0, 0, 0);
       -o-transform: translate3d(0, 0, 0);
          transform: translate3d(0, 0, 0);
}
````

There don't seem to have an official ui.boostrap.affix project 
But several personn has launched theres directives

http://jsfiddle.net/MatthewLothian/kBpxb/7/


### Angular directives 

There is at least 2 projects that has made this job : 
* https://github.com/angular-ui/bootstrap the bigger one 
* http://mgcrea.github.io/angular-strap a also popular project that can complete some of the unported directives
