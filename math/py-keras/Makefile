# $FreeBSD$

PORTNAME=	keras
DISTVERSION=	2.1.5
CATEGORIES=	math
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	neel@neelc.org
COMMENT=	Deep learning library for Python

LICENSE=	MIT
LICENSE_FILE=	${WRKSRC}/LICENSE

RUN_DEPENDS=	${PYNUMPY} \
		${PYTHON_PKGNAMEPREFIX}scipy>=0.14:science/py-scipy@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}six>=1.9.0:devel/py-six@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}theano>=0.8.0:math/py-theano@${FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}yaml>0:devel/py-yaml@${FLAVOR}

USES=		python
USE_GITHUB=	yes
GH_ACCOUNT=	fchollet
USE_PYTHON=	autoplist distutils
NO_ARCH=	yes

.include <bsd.port.mk>
