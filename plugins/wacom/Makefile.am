plugin_name = wacom

plugin_LTLIBRARIES = libgsdwacom.la

libgsdwacom_la_SOURCES =	\
	gsd-wacom-plugin.h	\
	gsd-wacom-plugin.c	\
	gsd-wacom-manager.h	\
	gsd-wacom-manager.c	\
	gsd-wacom-device.c	\
	gsd-wacom-device.h

libgsdwacom_la_CPPFLAGS = \
	-I$(top_srcdir)/gnome-settings-daemon		\
	-I$(top_srcdir)/plugins/common/			\
	-I$(top_srcdir)/data/				\
	-DGNOME_SETTINGS_LOCALEDIR=\""$(datadir)/locale"\" \
	-DLIBEXECDIR=\""$(libexecdir)"\" 		\
	$(AM_CPPFLAGS)

libgsdwacom_la_CFLAGS = \
	$(PLUGIN_CFLAGS)		\
	$(SETTINGS_PLUGIN_CFLAGS)	\
	$(WACOM_CFLAGS)			\
	$(AM_CFLAGS)

libgsdwacom_la_LDFLAGS =		\
	$(GSD_PLUGIN_LDFLAGS)

libgsdwacom_la_LIBADD  =						\
	$(top_builddir)/plugins/common/libcommon.la			\
	$(SETTINGS_PLUGIN_LIBS)						\
	$(WACOM_LIBS)

noinst_PROGRAMS = test-wacom list-wacom

test_wacom_SOURCES =		\
	test-wacom.c		\
	gsd-wacom-manager.c	\
	gsd-wacom-manager.h	\
	gsd-wacom-device.c	\
	gsd-wacom-device.h

test_wacom_CPPFLAGS = \
	-I$(top_srcdir)/data/					\
	-I$(top_srcdir)/gnome-settings-daemon			\
	-I$(top_srcdir)/plugins/common				\
	-DBINDIR=\"$(bindir)\"					\
	-DPIXMAPDIR=\""$(pkgdatadir)"\"				\
	-DGTKBUILDERDIR=\""$(pkgdatadir)"\"			\
	-DGNOME_SETTINGS_LOCALEDIR=\""$(datadir)/locale"\"	\
	$(AM_CPPFLAGS)

test_wacom_CFLAGS =			\
	$(SETTINGS_PLUGIN_CFLAGS)	\
	$(WACOM_CFLAGS)			\
	$(AM_CFLAGS)

test_wacom_LDADD = \
	$(top_builddir)/gnome-settings-daemon/libgsd-profile.la		\
	$(top_builddir)/plugins/common/libcommon.la			\
	$(SETTINGS_DAEMON_LIBS)			\
	$(SETTINGS_PLUGIN_LIBS)			\
	$(WACOM_LIBS)				\
	-lm

list_wacom_SOURCES =		\
	list-wacom.c		\
	gsd-wacom-device.c	\
	gsd-wacom-device.h

list_wacom_CPPFLAGS = \
	-I$(top_srcdir)/data/					\
	-I$(top_srcdir)/gnome-settings-daemon			\
	-I$(top_srcdir)/plugins/common				\
	-DBINDIR=\"$(bindir)\"					\
	-DPIXMAPDIR=\""$(pkgdatadir)"\"				\
	-DGTKBUILDERDIR=\""$(pkgdatadir)"\"			\
	-DGNOME_SETTINGS_LOCALEDIR=\""$(datadir)/locale"\"	\
	$(AM_CPPFLAGS)

list_wacom_CFLAGS =			\
	$(SETTINGS_PLUGIN_CFLAGS)	\
	$(WACOM_CFLAGS)			\
	$(AM_CFLAGS)

list_wacom_LDADD = \
	$(top_builddir)/gnome-settings-daemon/libgsd-profile.la		\
	$(top_builddir)/plugins/common/libcommon.la			\
	$(SETTINGS_DAEMON_LIBS)			\
	$(SETTINGS_PLUGIN_LIBS)			\
	$(WACOM_LIBS)				\
	-lm

plugin_in_files = wacom.gnome-settings-plugin.in

plugin_DATA = $(plugin_in_files:.gnome-settings-plugin.in=.gnome-settings-plugin)

EXTRA_DIST = $(plugin_in_files)
CLEANFILES = $(plugin_DATA)
DISTCLEANFILES = $(plugin_DATA)

@GSD_INTLTOOL_PLUGIN_RULE@
