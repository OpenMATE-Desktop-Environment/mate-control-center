# This is used in GNOMECC_CAPPLETS_CFLAGS
cappletname = display

uidir = $(pkgdatadir)/ui
dist_ui_DATA = display-capplet.ui

bin_PROGRAMS = gnome-display-properties

sbin_PROGRAMS = gnome-display-properties-install-systemwide

gnome_display_properties_SOURCES =	\
	xrandr-capplet.c		\
	scrollarea.c			\
	foo-marshal.c			\
	scrollarea.h			\
	foo-marshal.h

gnome_display_properties_LDFLAGS = -export-dynamic
gnome_display_properties_LDADD = \
	$(top_builddir)/capplets/common/libcommon.la \
	$(DISPLAY_CAPPLET_LIBS)

gnome_display_properties_install_systemwide_SOURCES =	\
	gnome-display-properties-install-systemwide.c

gnome_display_properties_install_systemwide_LDADD =	\
	$(GLIB_LIBS)

polkit_policydir = $(datadir)/polkit-1/actions
dist_polkit_policy_DATA =					\
	org.gnome.randr.policy

# You will need a recent intltool or the patch from this bug
# http://bugzilla.gnome.org/show_bug.cgi?id=462312
@INTLTOOL_POLICY_RULE@

@INTLTOOL_DESKTOP_RULE@

icons16dir = $(datadir)/icons/hicolor/16x16/apps
dist_icons16_DATA = icons/16x16/preferences-desktop-display.png
icons22dir = $(datadir)/icons/hicolor/22x22/apps
dist_icons22_DATA = icons/22x22/preferences-desktop-display.png
icons24dir = $(datadir)/icons/hicolor/24x24/apps
dist_icons24_DATA = icons/24x24/preferences-desktop-display.png
icons32dir = $(datadir)/icons/hicolor/32x32/apps
dist_icons32_DATA = icons/32x32/preferences-desktop-display.png
iconssvgdir = $(datadir)/icons/hicolor/scalable/apps
dist_iconssvg_DATA = icons/scalable/preferences-desktop-display.svg

desktopdir = $(datadir)/applications
Desktop_in_files = display-properties.desktop.in
desktop_DATA = $(Desktop_in_files:.desktop.in=.desktop)

INCLUDES   = $(DISPLAY_CAPPLET_CFLAGS) \
             $(GNOMECC_CAPPLETS_CFLAGS) \
	     -DSBINDIR="\"$(sbindir)\"" \
	     -DUIDIR="\"$(uidir)\"" \
	     -DGNOMELOCALEDIR="\"$(datadir)/locale\"" \
	     -DGNOMECC_DATA_DIR="\"$(pkgdatadir)\""

CLEANFILES = $(GNOMECC_CAPPLETS_CLEANFILES) $(Desktop_in_files) $(desktop_DATA)

gtk_update_icon_cache = gtk-update-icon-cache -f -t $(datadir)/icons/hicolor
install-data-hook: update-icon-cache
uninstall-hook: update-icon-cache
update-icon-cache:
	@-if test -z "$(DESTDIR)"; then \
		echo "Updating Gtk icon cache."; \
		$(gtk_update_icon_cache); \
	else \
		echo "*** Icon cache not updated.  After (un)install, run this:"; \
		echo "***   $(gtk_update_icon_cache)"; \
	fi

EXTRA_DIST = org.gnome.randr.policy.in
DISTCLEANFILES = org.gnome.randr.policy

-include $(top_srcdir)/git.mk
