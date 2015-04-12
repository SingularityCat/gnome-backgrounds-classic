backgrounddir = $(datadir)/backgrounds/gnome

background_DATA =\
	adwaita-day.jpg \
	adwaita-lock.jpg \
	adwaita-morning.jpg \
	adwaita-night.jpg \
	adwaita-timed.xml \
	Aqua.jpg \
	Blinds.jpg \
	BlueMarbleWest.jpg \
	Chmiri.jpg \
	FootFall.png \
	Mirror.jpg \
	Road.jpg \
	Sandstone.jpg \
	Spaceflare.jpg \
	Stripes.jpg \
	Stripes34.jpg \
	Sunset.png \
	Terraform-green.jpg \
	Spaceflare.jpg \
	Stripes.jpg \
	Stripes34.jpg \
	Sunset.jpg \
	FreshFlower.jpg \
	Garden.jpg \
	GreenMeadow.jpg \
	Spaceflare.jpg \
	Spaceflare-nova.jpg \
  Stamps.jpg \
	Stripes.jpg \
	Stripes34.jpg \
	SundownDunes.jpg \
	Terraform-blue.jpg \
	Terraform-green.jpg \
	Terraform-orange.jpg \
	TwoWings.jpg \
	UnderLit.jpg \
	Tulip.jpg \
	Wood.jpg \
	Waves.jpg \
	YellowFlower.jpg \
	ZvonecKonec.jpg

metadata_in_files = gnome-backgrounds.xml.in adwaita.xml.in
metadatadir = $(datadir)/gnome-background-properties
metadata_DATA = $(metadata_in_files:.xml.in=.xml)
@INTLTOOL_XML_RULE@

noinst_DATA = gnome-backgrounds.xml.in adwaita.xml.in
CLEANFILES = gnome-backgrounds.xml gnome-backgrounds.xml.in adwaita.xml adwaita.xml.in adwaita-timed.xml

EXTRA_DIST = $(background_DATA) gnome-backgrounds.xml.in.in adwaita.xml.in.in adwaita-timed.xml.in

edit = sed -e 's|@BACKGROUNDDIR[@]|$(backgrounddir)|g'

adwaita.xml.in: adwaita.xml.in.in Makefile
	$(AM_V_GEN) sed -e 's^\@datadir\@^$(datadir)^g' < $(srcdir)/adwaita.xml.in.in > adwaita.xml.in.tmp \
	&& mv adwaita.xml.in.tmp adwaita.xml.in

adwaita-timed.xml: adwaita-timed.xml.in Makefile
	$(AM_V_GEN) sed -e 's^\@datadir\@^$(datadir)^g' < $(srcdir)/adwaita-timed.xml.in > adwaita-timed.xml.tmp \
	&& mv adwaita-timed.xml.tmp adwaita-timed.xml

gnome-backgrounds.xml.in: gnome-backgrounds.xml.in.in Makefile
	$(edit) $< >$@

MAINTAINERCLEANFILES = \
	Makefile.in

-include $(top_srcdir)/git.mk
