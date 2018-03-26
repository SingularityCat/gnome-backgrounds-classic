VERSION := $(shell grep -F "  version:"  ../meson.build | cut -d " " -f 4 | tr -d "'" | tr -d ",")

.PHONY: all
all: dist arch/PKGBUILD

.PHONY: dist
dist: gnome-backgrounds-classic.tar.gz

.PHONY: clean
clean:
	rm -f gnome-backgrounds-classic.tar.gz arch/PKGBUILD arch/gnome-backgrounds-classic-*.tar.gz

gnome-backgrounds-classic.tar.gz: ../meson.build
	(cd ..; git archive --format=tar.gz --output=./dist/gnome-backgrounds-classic.tar.gz  --prefix=gnome-backgrounds-classic-${VERSION}/ HEAD)

arch/PKGBUILD: arch/PKGBUILD.in
	sed -e 's/@VERSION@/${VERSION}/g'  < arch/PKGBUILD.in > arch/PKGBUILD
	(cd arch; ln -s ../gnome-backgrounds-classic.tar.gz ./gnome-backgrounds-classic-${VERSION}.tar.gz)
	(cd arch; updpkgsums)
