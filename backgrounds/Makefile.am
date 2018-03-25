backgrounddir = $(datadir)/backgrounds/gnome

background_DATA =\
	adwaita-pi-day.jpg \
	adwaita-pi-lock.jpg \
	adwaita-pi-morning.jpg \
	adwaita-pi-night.jpg \
	adwaita-pi-timed.xml \
	Aqua.jpg \
	Stripes.jpg \
	Stripes34.jpg \
	Terraform-blue.jpg \
	Terraform-orange.jpg \
	Spaceflare.jpg \
	Spaceflare-nova.jpg \
	Spaceflare-supernova.jpg \
	UnderLit.jpg \
	Wood-classic.jpg

metadata_in_files = gnome-backgrounds-classic.xml.in
metadatadir = $(datadir)/gnome-background-properties
metadata_DATA = $(metadata_in_files:.xml.in=.xml)
@INTLTOOL_XML_RULE@

noinst_DATA = gnome-backgrounds-classic.xml.in
CLEANFILES = gnome-backgrounds-classic.xml gnome-backgrounds-classic.xml.in adwaita-pi-timed.xml

EXTRA_DIST = $(background_DATA) gnome-backgrounds-classic.xml.in.in adwaita-pi.xml.in.in adwaita-pi-timed.xml.in

edit = sed -e 's|@BACKGROUNDDIR[@]|$(backgrounddir)|g'

adwaita-pi-timed.xml: adwaita-pi-timed.xml.in Makefile
	$(AM_V_GEN) sed -e 's^\@datadir\@^$(datadir)^g' < $(srcdir)/adwaita-pi-timed.xml.in > adwaita-pi-timed.xml.tmp \
	&& mv adwaita-pi-timed.xml.tmp adwaita-pi-timed.xml

gnome-backgrounds-classic.xml.in: gnome-backgrounds-classic.xml.in.in Makefile
	$(edit) $< >$@

MAINTAINERCLEANFILES = \
	Makefile.in

-include $(top_srcdir)/git.mk
