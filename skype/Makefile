URL=http://www.skype.com/go/getskype-linux-deb

all: skype-install.deb
	sudo $(MAKE) install

skype-install.deb:
	wget -O $@ $(URL)

install: skype-install.deb
	dpkg --add-architecture i386
	apt-get update
	dpkg -i $< || true
	apt-get -f install
	apt-get install libpulse0:i386
