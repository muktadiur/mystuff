# $OpenBSD$

COMMENT =     Protect BSD Unix computer servers from brute-force attacks

V =           0.1.2
DISTNAME =    blockor-${V}
CATEGORIES =  security
REVISION =    0

HOMEPAGE =    https://github.com/muktadiur/blockor
MAINTAINER =  Muktadiur Rahman <muktadiur@gmail.com>

# BSD3CLAUSE
PERMIT_PACKAGE = Yes

GH_ACCOUNT =   muktadiur
GH_PROJECT =   blockor
GH_COMMIT =    c6ccc0d767e965efca5d9107eee4a6bc22a6a555

# Dependencies
#RUN_DEPENDS=	shells/sh


# Installation instructions
NO_BUILD=	Yes
NO_TEST=	Yes

BLIBEXECDIR=	${PREFIX}/libexec/blockor
BEXAMPLEDIR=	${PREFIX}/share/examples/blockor

do-install:
	${INSTALL_DATA_DIR} ${BLIBEXECDIR}
	${INSTALL_DATA_DIR} ${BEXAMPLEDIR}
	${INSTALL_DATA_DIR} ${PREFIX}/etc
	${INSTALL_MAN} ${WRKSRC}/openbsd/usr/local/man/man8/blockor.8.gz ${PREFIX}/man/man8/blockor.8.gz
	${INSTALL_DATA} ${WRKSRC}/openbsd/usr/local/etc/blockor.conf ${PREFIX}/etc/blockor.conf
	${INSTALL_DATA} ${WRKSRC}/openbsd/usr/local/share/examples/blockor/blockor.sample.conf \
		${PREFIX}/share/examples/blockor/blockor.sample.conf
	${INSTALL_SCRIPT} ${WRKSRC}/usr/local/bin/blockor ${PREFIX}/bin/
	${INSTALL_SCRIPT} ${WRKSRC}/usr/local/libexec/blockor/blockord.sh ${PREFIX}/libexec/blockor/blockord.sh

# Enable daemon control
RC_SCRIPTS=	blockord
SUBST_VARS+=	BLIBEXECDIR BEXAMPLEDIR
.include       <bsd.port.mk>


