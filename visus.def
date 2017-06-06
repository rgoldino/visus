BootStrap: docker
From: visus/mod_visus

%runscript
	echo "Starting visus server"
	echo "Connect to `hostname`:8080"
	service apache2 start

%post
	umask 022
	cd /etc/apache2
	mv envvars envvars.orig
	sed 's#/var#/tmp/visus#g' envvars.orig > envvars
	mv ports.conf ports.conf.orig
	sed 's/80/8080/' ports.conf.orig > ports.conf
	cd sites-enabled
	mv 000-default.conf 000-default.conf.orig
	sed 's/80/8080/' 000-default.conf.orig > 000-default.conf
