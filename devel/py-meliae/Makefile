# $FreeBSD$

PORTNAME=	meliae
PORTVERSION=	0.4.0
PORTREVISION=	2
CATEGORIES=	devel python
MASTER_SITES=	http://launchpadlibrarian.net/74803944/ \
		LOCAL/sbz
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	sbz@FreeBSD.org
COMMENT=	Python Memory Usage Analyzer

LICENSE=	GPLv3

USES=		python:2.7
USE_PYTHON=	distutils autoplist cython

regression-test: extract
	(cd ${WRKSRC}; ${MAKE} check)

.include <bsd.port.mk>
