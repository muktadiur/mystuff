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
LIBEXECDIR=	${PREFIX}/libexec/blockor
EXAMPLEDIR=	${PREFIX}/share/examples/blockor

do-install:
	${INSTALL_DATA_DIR} ${LIBEXECDIR}
	${INSTALL_DATA_DIR} ${EXAMPLEDIR}
	${INSTALL_SCRIPT} ${WRKSRC}${BIN_DIR}/blockor ${BIN_DIR}
	${INSTALL_MAN} ${WRKSRC}/openbsd${PREFIX}/man/blockor.8.gz ${PREFIX}/man/blockor.8.gz
	${INSTALL_DATA} ${WRKSRC}/openbsd${PREFIX}/etc/blockor.conf ${PREFIX}/etc/blockor.conf
	${INSTALL_SCRIPT} ${WRKSRC}${LIBEXECDIR}/blockord.sh ${LIBEXECDIR}/blockord.sh
	${INSTALL_DATA} ${WRKSRC}/openbsd${EXAMPLEDIR}/blockor.example.conf \
		${EXAMPLEDIR}/blockor.example.conf

# Enable daemon control
RC_SCRIPTS=	blockord
SUBST_VARS+=	BIN_DIR LIBEXECDIR EXAMPLEDIR

.include       <bsd.port.mk>


