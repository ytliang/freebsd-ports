# $FreeBSD$

PORTNAME=	grantleetheme
DISTVERSION=	${KDE_APPLICATIONS_VERSION}
CATEGORIES=	deskutils kde kde-applications

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KDE PIM grantleetheme

LICENSE=	LGPL21

USES=		cmake:outsource compiler:c++11-lib gettext grantlee:5 kde:5 \
		pkgconfig tar:xz
USE_KDE=	attica auth codecs config configwidgets coreaddons ecm i18n \
		iconthemes newstuff service widgetsaddons xmlgui
USE_QT5=	core dbus gui network testlib widgets xml \
		buildtools_build qmake_build
USE_LDCONFIG=	yes

DESCR=		${.CURDIR:H:H}/deskutils/kdepim/pkg-descr

.include <bsd.port.mk>
