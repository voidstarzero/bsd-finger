all: fingerd

include ../MCONFIG
include ../MRULES

fingerd: fingerd.o
	$(CC) $(LDFLAGS) $^ $(LIBS) -o $@

fingerd.o: pathnames.h ../version.h

install: fingerd
	install -s -m$(DAEMONMODE) fingerd $(INSTALLROOT)$(SBINDIR)/in.fingerd
	install -m$(MANMODE) fingerd.8 $(INSTALLROOT)$(MANDIR)/man8/in.fingerd.8
	ln -sf in.fingerd.8 $(INSTALLROOT)$(MANDIR)/man8/fingerd.8
	install -m$(SDMODE) finger.socket $(INSTALLROOT)$(SDDIR)/finger.socket
	install -m$(SDMODE) finger@.service $(INSTALLROOT)$(SDDIR)/finger@.service

clean:
	rm -f *.o fingerd

