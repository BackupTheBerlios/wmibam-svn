CC=g++
CFLAGS=-g -Wall -O2 -pedantic

PREFIX=/usr/local
BINPATH=$(PREFIX)/bin
MANPATH=$(PREFIX)/share/man/man1

INSTALL=install -m 755
INSTALLMAN=install -m 644
INSTALLDIR=install -d
RM=rm -f

X11=/usr/X11R6/lib
INCLUDE=-L$(X11) -lX11 -lXext -lXpm

all: wmibam

wmibam: main.o dockapp.o
	$(CC) $(CFLAGS) $(INCLUDE) -o wmibam main.o dockapp.o

install: wmibam install-man
	$(INSTALLDIR) $(BINPATH)
	$(INSTALL) wmibam $(BINPATH)

install-man:
	$(INSTALLDIR) $(MANPATH)
	$(INSTALLMAN) wmibam.1 $(MANPATH)

uninstall: uninstall-man
	-$(RM) $(BINPATH)/wmibam

uninstall-man:
	-$(RM) $(MANPATH)/wmibam.1

clean:
	$(RM) main.o dockapp.o wmibam
