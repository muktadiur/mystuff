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
RUN_DEPENDS=	shells/sh


# Installation instructions
NO_BUILD=	Yes
NO_TEST=	Yes


# Define paths
PREFIX=		/usr/local
BIN_DIR=	${PREFIX}/bin
LIBEXECDIR=	${PREFIX}/libexec
ETCDIR=		${PREFIX}/share/examples/blockor
DATADIR=	${PREFIX}/share/blockor

# Installation commands
do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/${PREFIX}/bin/blockor ${PREFIX}/bin
	${INSTALL_MAN} ${WRKSRC}/openbsd/${PREFIX}/man/blockor.8 ${PREFIX}/man/man8/
	${INSTALL_DATA_DIR} ${ETCDIR}
	${INSTALL_DATA_DIR} ${DATADIR}
	${INSTALL_DATA} ${WRKSRC}/openbsd/${PREFIX}/examples/blockor/blockor.conf.sample \
		${ETCDIR}/blockor.conf.sample
	${INSTALL_DATA} ${WRKSRC}/openbsd/${PREFIX}/etc/blockor.conf \
		${ETCDIR}/blockor.conf
	${INSTALL_SCRIPT} ${WRKSRC}/${PREFIX}/libexec/blockor/blockord.sh \
		${LIBEXECDIR}/blockor/blockord.sh

# Enable daemon control
RC_SCRIPTS=	blockord
SUBST_VARS+=	BIN_DIR LIBEXECDIR ETCDIR DATADIR

# do-install:
# 	make install

.include       <bsd.port.mk>


