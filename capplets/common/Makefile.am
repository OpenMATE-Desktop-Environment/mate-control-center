EXTRA_DIST =

INCLUDES = \
	-DGNOMECC_DATA_DIR="\"$(pkgdatadir)\""				\
	-DGNOMELOCALEDIR="\"$(datadir)/locale\""			\
	-DGTK_ENGINE_DIR="\"$(GTK_ENGINE_DIR)\"" 			\
	-DG_LOG_DOMAIN=\"capplet-common\"				\
	-DINSTALL_PREFIX=\"$(prefix)\"					\
	-I$(top_srcdir)							\
	-I$(top_srcdir)/libwindow-settings				\
	-DPIXMAP_DIR=\""$(datadir)/gnome-control-center/pixmaps"\"	\
	$(CAPPLET_CFLAGS)						\
	$(DBUS_CFLAGS)							\
	$(GNOME_DESKTOP_CFLAGS)						\
	$(METACITY_CFLAGS)						\
	$(GSD_DBUS_CFLAGS)						\
	$(GIO_CFLAGS)


noinst_LTLIBRARIES = libcommon.la

libcommon_la_SOURCES = \
	activate-settings-daemon.c	\
	activate-settings-daemon.h	\
	capplet-stock-icons.c		\
	capplet-stock-icons.h		\
	capplet-util.c			\
	capplet-util.h			\
	file-transfer-dialog.c		\
	file-transfer-dialog.h		\
	gconf-property-editor.c		\
	gconf-property-editor.h		\
	gconf-property-editor-marshal.c	\
	gconf-property-editor-marshal.h \
	gnome-theme-apply.c		\
	gnome-theme-apply.h 		\
	gnome-theme-info.c		\
	gnome-theme-info.h		\
	gtkrc-utils.c			\
	gtkrc-utils.h			\
	theme-thumbnail.c		\
	theme-thumbnail.h		\
	wm-common.c			\
	wm-common.h

libcommon_la_LIBADD =							\
	$(top_builddir)/libwindow-settings/libgnome-window-settings.la  \
	$(METACITY_LIBS)						\
	$(DBUS_LIBS)							\
	$(GNOME_DESKTOP_LIBS)						\
	$(GIO_LIBS)

gnome_theme_test_SOURCES = \
	gnome-theme-test.c

gnome_theme_test_LDADD = 						\
	libcommon.la							\
	$(GNOMECC_CAPPLETS_LIBS)

noinst_PROGRAMS = \
	gnome-theme-test

-include $(top_srcdir)/git.mk
