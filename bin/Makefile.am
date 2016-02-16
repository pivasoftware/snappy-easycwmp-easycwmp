bin_PROGRAMS = easycwmpd

easycwmpd_SOURCES =		\
	../src/backup.c		\
	../src/backup.h		\
	../src/config.h		\
	../src/config.c		\
	../src/cwmp.h		\
	../src/cwmp.c		\
	../src/digestauth.h	\
	../src/digestauth.c	\
	../src/external.h	\
	../src/external.c	\
	../src/easycwmp.h	\
	../src/easycwmp.c	\
	../src/http.h		\
	../src/http.c		\
	../src/json.c		\
	../src/json.h		\
	../src/log.c		\
	../src/log.h		\
	../src/md5.h		\
	../src/md5.c		\
	../src/time.h		\
	../src/time.c		\
	../src/ubus.h		\
	../src/ubus.c		\
	../src/xml.h		\
	../src/xml.c

easycwmpd_CFLAGS =		\
	$(AM_CFLAGS)		\
	$(LIBUCI_CFLAGS)	\
	$(LIBUBOX_CFLAGS)	\
	$(LIBUBUS_CFLAGS)	\
	$(MICROXML_CFLAGS)	\
	$(LIBCURL_CFLAGS)

easycwmpd_LDFLAGS =		\
	$(AM_LDFLAGS)		\
	$(LIBUCI_LDFLAGS)	\
	$(LIBUBOX_LDFLAGS)	\
	$(LIBUBUS_LDFLAGS)	\
	$(MICROXML_LDFLAGS)	\
	$(LIBCURL_LDFLAGS)

easycwmpd_LDADD =		\
	$(AM_LIBS)			\
	$(LIBUCI_LIBS)		\
	$(LIBUBOX_LIBS)		\
	$(LIBUBUS_LIBS)		\
	$(MICROXML_LIBS)	\
	$(LIBCURL_LIBS)		\
	$(LIBJSON_LIBS)


BUILDROOT	=	$(DSTROOT)
DSTROOT		=	$(DESTDIR)


#
# Install commands...
#

INSTALL_BIN	=	$(LIBTOOL) $(INSTALL) -m 755 -s
INSTALL_DATA_C	=	$(INSTALL) -m 644
INSTALL_DIR_C	=	$(INSTALL) -d
INSTALL_LIB	=	$(LIBTOOL) $(INSTALL) -m 755
INSTALL_SCRIPT	=	$(INSTALL) -m 755


install-data-hook:
	echo Installing easycwmp data model main script...
	$(INSTALL_DIR_C) $(BUILDROOT)/usr/sbin
	$(INSTALL_SCRIPT) ../ext/openwrt/scripts/easycwmp.sh $(BUILDROOT)/usr/sbin/easycwmp
	echo Installing easycwmp data model function scripts...
	$(INSTALL_DIR_C) $(BUILDROOT)/usr/share/easycwmp/functions
	$(INSTALL_SCRIPT) ../ext/openwrt/scripts/functions/* $(BUILDROOT)/usr/share/easycwmp/functions
	echo Installing easycwmp config...
	$(INSTALL_DIR_C) $(BUILDROOT)/etc/config
	$(INSTALL_DIR_C) $(BUILDROOT)/etc/easycwmp
	$(INSTALL_DATA_C) ../ext/openwrt/config/easycwmp $(BUILDROOT)/etc/config

