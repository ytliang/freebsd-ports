# Created by: thinker@branda.to
# $FreeBSD$

PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
PORTREVISION=	0

MAINTAINER=	lev@FreeBSD.org
COMMENT=	Python bindings for version control system

.if defined(WITH_SUBVERSION_VER) && ${WITH_SUBVERSION_VER} == 18
MASTERDIR=	${.CURDIR}/../../devel/subversion18
.else
MASTERDIR=	${.CURDIR}/../../devel/subversion
.endif
PKGDIR=		${.CURDIR}

USES+=		python
USE_PYTHON=	flavors py3kplist

SVN_BUILD_BINDINGS=	yes
SVN_BUILD_ADDONS=	yes

.include "${MASTERDIR}/Makefile.common"

CATEGORIES+=	python

CONFIGURE_ARGS+=	--without-gnome-keyring \
			--without-kwallet \
			--with-apxs=no

ALL_TARGET=	swig-py-lib swig-py
INSTALL_TARGET=	install-swig-py

.include <bsd.port.post.mk>
