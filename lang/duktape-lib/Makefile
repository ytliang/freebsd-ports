# $FreeBSD$

PORTNAME=	duktape
DISTVERSION=	2.2.0
CATEGORIES=	lang devel
MASTER_SITES=	http://duktape.org/
PKGNAMESUFFIX=	-lib

MAINTAINER=	alfix86@gmail.com
COMMENT=	Embeddable Javascript engine (shared lib)

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

USES=		tar:xz
USE_LDCONFIG=	yes

MAKEFILE=	Makefile.sharedlibrary

do-install:
	${INSTALL_DATA} ${WRKSRC}/src/duktape.h ${STAGEDIR}${PREFIX}/include
	${INSTALL_DATA} ${WRKSRC}/src/duk_config.h ${STAGEDIR}${PREFIX}/include
.for l in libduktape.so libduktaped.so
	${INSTALL_LIB} ${WRKSRC}/${l}.202.20200 ${STAGEDIR}${PREFIX}/lib
	${RLN} ${STAGEDIR}${PREFIX}/lib/${l}.202.20200 ${STAGEDIR}${PREFIX}/lib/${l}
	${RLN} ${STAGEDIR}${PREFIX}/lib/${l}.202.20200 ${STAGEDIR}${PREFIX}/lib/${l}.202
.endfor

.include <bsd.port.mk>
