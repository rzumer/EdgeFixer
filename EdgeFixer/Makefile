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
install:
	mkdir -p $(DESTDIR)$(PREFIX)/lib
	cp $(LIBNAME).a $(DESTDIR)$(PREFIX)/lib
	cp $(LIBNAME).so $(DESTDIR)$(PREFIX)/lib

.PHONY: uninstall
uninstall:
	rm -f $(DESTDIR)$(PREFIX)/lib/$(LIBNAME).a $(DESTDIR)$(PREFIX)/lib/$(LIBNAME).so
