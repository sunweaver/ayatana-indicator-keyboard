pkglibexec_PROGRAMS = ayatana-indicator-keyboard-service

AM_CFLAGS = -w -DGNOME_DESKTOP_USE_UNSTABLE_API
AM_LDFLAGS = -lm
AM_VALAFLAGS = --enable-experimental-non-null   \
               --metadatadir $(top_srcdir)/deps \
               --vapidir $(top_srcdir)/deps

ayatana_indicator_keyboard_service_SOURCES = main.vala            \
                                             source.vala          \
                                             common.vala          \
                                             ibus-menu.vala       \
                                             ibus-panel.vala      \
                                             indicator-menu.vala  \
                                             keyboard-plugin.vala \
                                             window-stack.vala    \
                                             unity-session.vala   \
                                             unity-greeter.vala
ayatana_indicator_keyboard_service_VALAFLAGS = $(AM_VALAFLAGS)            \
                                               --pkg gee-1.0              \
                                               --pkg posix                \
                                               --pkg pangocairo           \
                                               --pkg gtk+-3.0             \
                                               --pkg GDesktopEnums-3.0    \
                                               --pkg GnomeDesktop-3.0     \
                                               --pkg Xkl-1.0              \
                                               --pkg Gkbd-3.0             \
                                               --pkg ibus-1.0             \
                                               --pkg Fcitx-1.0            \
                                               --pkg AccountsService-1.0  \
                                               --pkg liblightdm-gobject-1
ayatana_indicator_keyboard_service_CFLAGS = $(AM_CFLAGS)              \
                                            $(GEE_CFLAGS)             \
                                            $(PANGOCAIRO_CFLAGS)      \
                                            $(GTK_CFLAGS)             \
                                            $(GNOME_DESKTOP_CFLAGS)   \
                                            $(LIBXKLAVIER_CFLAGS)     \
                                            $(LIBGNOMEKBD_CFLAGS)     \
                                            $(IBUS_CFLAGS)            \
                                            $(FCITX_GCLIENT_CFLAGS)   \
                                            $(ACCOUNTSSERVICE_CFLAGS) \
                                            $(LIGHTDM_CFLAGS)         \
                                            $(COVERAGE_CFLAGS)
ayatana_indicator_keyboard_service_LDFLAGS = $(AM_LDFLAGS)           \
                                             $(GEE_LIBS)             \
                                             $(PANGOCAIRO_LIBS)      \
                                             $(GTK_LIBS)             \
                                             $(GNOME_DESKTOP_LIBS)   \
                                             $(LIBXKLAVIER_LIBS)     \
                                             $(LIBGNOMEKBD_LIBS)     \
                                             $(IBUS_LIBS)            \
                                             $(FCITX_GCLIENT_LIBS)   \
                                             $(ACCOUNTSSERVICE_LIBS) \
                                             $(LIGHTDM_LIBS)         \
                                             $(COVERAGE_LDFLAGS)
