TESTNUM=	sys

ASMSRCS= mknod.S chmod.S stat.S

SRCS+= ${ASMSRCS}
CLEANFILES+= ${ASMSRCS} test.c

CFLAGS+=-I/usr/src/lib/libc/amd64

.include <../Makefile.inc>
.include <bsd.lib.mk>

test.c:
	sh ${.CURDIR}/../makesyscalls-fake.sh /usr/src/sys/kern/syscalls.master > ${.TARGET}

${ASMSRCS}:
	printf '#include "SYS.h"\nRSYSCALL(${.PREFIX})\n' >> ${.TARGET}
