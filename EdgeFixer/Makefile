CC=gcc
CFLAGS=-c -std=c99 -Wall -fPIC
SOURCES=edgefixer.c vsplugin.c
OBJECTS=$(SOURCES:.c=.o)
LIBNAME=edgefixer
PREFIX=/usr/local

all:
	$(CC) $(CFLAGS) $(SOURCES)
	ar cru $(LIBNAME).a $(OBJECTS)
	$(CC) -shared -o $(LIBNAME).so $(OBJECTS)

.PHONY: clean
clean:
	rm -f $(OBJECTS) $(LIBNAME).a $(LIBNAME).so

.PHONY: install
install: all
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp $(LIBNAME).a $(DESTDIR)$(PREFIX)/bin
	cp $(LIBNAME).so $(DESTDIR)$(PREFIX)/bin

.PHONY: uninstall
uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/$(LIBNAME).a $(DESTDIR)$(PREFIX)/bin/$(LIBNAME).so
