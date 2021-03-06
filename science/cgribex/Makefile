# Created by: Sunpoet Po-Chuan Hsieh <sunpoet@FreeBSD.org>
# $FreeBSD$

PORTNAME=	cgribex
PORTVERSION=	1.7.5
CATEGORIES=	science
MASTER_SITES=	https://code.zmaw.de/attachments/download/12689/ \
		LOCAL/sunpoet

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Lightweight GRIBEX in C with portable Fortran interface

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

OPTIONS_DEFINE=	GRIB_API JASPER SZIP
OPTIONS_DEFAULT=JASPER SZIP

CPPFLAGS+=	-DgFortran
GNU_CONFIGURE=	yes
INSTALL_TARGET=	install-strip
USE_LDCONFIG=	yes
USES=		libtool

GRIB_API_CONFIGURE_OFF=	--without-grib_api
GRIB_API_CONFIGURE_ON=	--with-grib_api=${LOCALBASE}
GRIB_API_LIB_DEPENDS=	libgrib_api.so:science/grib_api
JASPER_CONFIGURE_OFF=	--without-jasper
JASPER_CONFIGURE_ON=	--with-jasper=${LOCALBASE}
JASPER_LIB_DEPENDS=	libjasper.so:graphics/jasper
SZLIB_CONFIGURE_OFF=	--without-szlib
SZIP_CONFIGURE_ON=	--with-szlib=${LOCALBASE}
SZIP_LIB_DEPENDS=	libsz.so:science/szip

post-configure:
	@${REINPLACE_CMD} -e 's|-Ino/include||; s|-Lno/lib||' ${WRKSRC}/Makefile ${WRKSRC}/*/Makefile

post-install:
	${STRIP_CMD} ${STAGEDIR}${PREFIX}/lib/libcgribex.so.0.0.0

.include <bsd.port.mk>
