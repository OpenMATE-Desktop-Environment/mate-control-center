# This is used in GNOMECC_CAPPLETS_CFLAGS
cappletname = keyboard

bin_PROGRAMS = gnome-keyboard-properties

gnome_keyboard_properties_SOURCES = \
	gnome-keyboard-properties.c \
	gnome-keyboard-properties-a11y.c \
	gnome-keyboard-properties-a11y.h \
	gnome-keyboard-properties-xkb.c \
	gnome-keyboard-properties-xkbmc.c \
	gnome-keyboard-properties-xkblt.c \
	gnome-keyboard-properties-xkbltadd.c \
	gnome-keyboard-properties-xkbot.c \
	gnome-keyboard-properties-xkbpv.c \
	gnome-keyboard-properties-xkb.h

gnome_keyboard_properties_LDADD = $(GNOMECC_CAPPLETS_LIBS) $(LIBGNOMEKBDUI_LIBS) $(LIBGNOMEKBD_LIBS)

@INTLTOOL_DESKTOP_RULE@

uidir   = $(pkgdatadir)/ui
dist_ui_DATA = gnome-keyboard-properties-a11y-notifications.ui \
               gnome-keyboard-properties-dialog.ui \
               gnome-keyboard-properties-layout-chooser.ui \
               gnome-keyboard-properties-model-chooser.ui \
               gnome-keyboard-properties-options-dialog.ui

desktopdir = $(datadir)/applications
Desktop_in_files = keyboard.desktop.in
desktop_DATA = $(Desktop_in_files:.desktop.in=.desktop)

INCLUDES = \
	$(GNOMECC_CAPPLETS_CFLAGS) \
	$(LIBGNOMEKBDUI_CFLAGS) \
	$(LIBGNOMEKBD_CFLAGS) \
	-DGNOMELOCALEDIR="\"$(datadir)/locale\"" \
	-DGNOMECC_DATA_DIR="\"$(pkgdatadir)\"" \
	-DGNOMECC_UI_DIR="\"$(uidir)\""
CLEANFILES = $(GNOMECC_CAPPLETS_CLEANFILES) $(Desktop_in_files) $(desktop_DATA)
EXTRA_DIST = $(ui_DATA)

-include $(top_srcdir)/git.mk
