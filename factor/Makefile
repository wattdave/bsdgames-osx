#	@(#)Makefile	8.1 (Berkeley) 5/31/93
# $FreeBSD: src/games/factor/Makefile,v 1.2.6.2 2002/10/23 14:59:14 fanf Exp $
# $DragonFly: src/games/factor/Makefile,v 1.4 2006/10/08 16:22:35 pavalos Exp $

PROG=	factor
SRCS=	factor.c pr_tbl.c
CFLAGS+=-I${.CURDIR}/../primes

.if exists(${.CURDIR}/../../crypto) && !defined(NO_OPENSSL)
CFLAGS+=-DHAVE_OPENSSL
LDADD+=	-lcrypto
DPADD+=	${LIBCRYPTO}
.endif

MAN=	factor.6
MLINKS+=factor.6 primes.6
.PATH:	${.CURDIR}/../primes

beforeinstall:
.if !exists(${BINDIR})
	mkdir -p ${BINDIR}
.endif
.if !exists(${MANDIR}6)
	mkdir -p ${MANDIR}6
.endif

.include <bsd.prog.mk>
