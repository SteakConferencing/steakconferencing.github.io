all : upload verify

build: clean _site

upload : _site
	rsync --progress -avz --exclude '.git' --exclude 'Makefile' --exclude '*.yml' --delete $</ g00se@g00se.indus.uberspace.de:/home/g00se/www/steakconferencing.de/

local : _site
	chromium-browser --incognito $$(pwd)/$</index.html

_site : clean
	jekyll build

clean :
	rm -rf _site