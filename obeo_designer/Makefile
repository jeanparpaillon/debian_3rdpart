URL=http://www.obeo.fr/download/release/designer/7.0/community/latest/packages/ObeoDesigner-Community-7.0-linux.gtk.x86_64.zip

all: ObeoDesigner-Community-latest.zip
	sudo $(MAKE) install

ObeoDesigner-Community-latest.zip:
	wget -O $@ $(URL)

install: install-archive install-desktop

install-archive: ObeoDesigner-Community-latest.zip
	rm -rf /opt/ObeoDesigner-Community
	unzip -d /opt $<
	chgrp -R users /opt/ObeoDesigner-Community
	chmod -R g+w /opt/ObeoDesigner-Community

install-desktop: /usr/share/applications/obeodesigner-community.desktop

/usr/share/applications/obeodesigner-community.desktop: obeodesigner-community.desktop
	install -o root -g root $< /usr/share/applications/
	update-desktop-database
