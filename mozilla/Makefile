URL=http://ftp.mozilla.org/pub/mozilla.org/firefox/releases/latest/linux-x86_64/fr/firefox-35.0.1.tar.bz2

all: firefox-latest.tar.bz2
	sudo $(MAKE) install

firefox-latest.tar.bz2:
	wget -O $@ $(URL)

install: install-firefox

install-firefox: firefox-latest.tar.bz2
	tar xvfC $< /opt/
	chgrp -R users /opt/firefox
	chmod -R g+w /opt/firefox
	ln -s /opt/firefox/firefox /usr/bin/firefox.real
	install -o root -g root firefox.desktop /usr/share/applications/
	update-desktop-database
