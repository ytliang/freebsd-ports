# Created by: Steve Wills <swills@FreeBSD.org>
# $FreeBSD$

PORTNAME=	google-cloud-sdk
PORTVERSION=	196.0.0
CATEGORIES=	net
MASTER_SITES=	https://dl.google.com/dl/cloudsdk/channels/rapid/downloads/
DISTNAME=	google-cloud-sdk-${PORTVERSION}-linux-x86_64

MAINTAINER=	swills@FreeBSD.org
COMMENT=	Google Cloud SDK for Google Cloud Platform

USES=		python:2.7
NO_BUILD=	yes
WRKSRC=		${WRKDIR}/google-cloud-sdk

RUN_DEPENDS=	python:lang/python \
		${PYTHON_PKGNAMEPREFIX}sqlite3>0:databases/py-sqlite3

post-extract:
	@${RM} -r \
		${WRKSRC}/install.bat \
		${WRKSRC}/platform/gsutil/third_party/crcmod/docs/source/make.bat \
		${WRKSRC}/platform/gsutil/third_party/rsa/doc/make.bat \
		${WRKSRC}/rpm \
		${WRKSRC}/deb \
		${WRKSRC}/lib/third_party/grpc/_cython/cygrpc.so

do-install:
	${RM} -r ${WRKSRC}/help ${WRKSRC}/.install/.download
	( cd ${WRKSRC} ; ${COPYTREE_SHARE} . ${STAGEDIR}${PREFIX}/google-cloud-sdk )
.for x in bq gcloud git-credential-gcloud.sh gsutil
	${CHMOD} +x ${STAGEDIR}${PREFIX}/google-cloud-sdk/bin/${x}
	${RLN} ${STAGEDIR}${PREFIX}/google-cloud-sdk/bin/${x} \
		${STAGEDIR}${PREFIX}/bin/${x}
.endfor

.include <bsd.port.mk>
