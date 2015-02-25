### Make file 

make file are with tabs only 

The name of the file should be "Makefile"
````
help:
	@echo "Please use \`make <target>' where <target> is one of:"
	@echo "  build       install all stuff :)"
	@echo "  dist       clear cache, reload database schema and load fixtures (only for dev environment)"

install:
	npm install
	bower install --allow-root
````

by typing 
``make``
we see the help 

by typing 
``make install``

The list of shelle command is triggered