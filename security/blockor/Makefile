# $OpenBSD$

COMMENT =     Protect BSD Unix computer servers from brute-force attacks

V =           0.1.2
DISTNAME =    blockor-${V}
CATEGORIES =  security
REVISION =    0

HOMEPAGE =    https://github.com/muktadiur/blockor
MAINTAINER =  Muktadiur Rahman <muktadiur@gmail.com>

# MIT
PERMIT_PACKAGE = Yes

GH_ACCOUNT =   muktadiur
GH_PROJECT =   blockor
GH_COMMIT =    c6ccc0d767e965efca5d9107eee4a6bc22a6a555

# Dependencies
RUN_DEPENDS=	shells/sh


# Installation instructions
NO_BUILD=	Yes
NO_TEST=	Yes


do-install:
	make install

.include       <bsd.port.mk>


