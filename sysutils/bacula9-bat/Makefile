# Created by: Dan Langille <dan@langille.org>
# $FreeBSD$

PORTNAME=	bacula
PKGNAMESUFFIX=	9-bat

COMMENT=	Network backup solution (GUI)

DEPRECATED=		Qt4 has been EOL since december 2015
EXPIRATION_DATE=	2019-03-15

LIB_DEPENDS+=	libqwt.so:x11-toolkits/qwt5 \
		libbac.so:sysutils/bacula9-client

USES=		pkgconfig qt:4
USE_QT=		qmake_build uic_build moc_build rcc_build
WITH_BAT=	yes

PLIST=		${.CURDIR}/pkg-plist
MAKE_ENV+=	MAKEOBJDIRPREFIX=/

MASTERDIR=	${.CURDIR}/../../sysutils/bacula9-server

CONFIGURE_ARGS+=	--enable-bat \
			--with-qwt=${LOCALBASE}/lib \
			--disable-build-dird \
			--disable-build-stored \
			--enable-client-only

OPTIONS_DEFINE=	#
OPTIONS_DEFAULT=#

.include "${MASTERDIR}/Makefile"
