CC=gcc
CFLAGS=-c -std=c99 -Wall -fPIC
SOURCES=edgefixer.c vsplugin.c
OBJECTS=$(SOURCES:.c=.o)
LIBNAME=edgefixer
PREFIX=/usr/local
SHELL=/bin/bash
.SHELLFLAGS="-O extglob -c"

all:
	$(CC) $(CFLAGS) $(SOURCES)
	ar cru $(LIBNAME).a $(OBJECTS)
	$(CC) -shared -o $(LIBNAME).so $(OBJECTS)

.PHONY: clean
clean:
	rm -f $(OBJECTS) $(LIBNAME){.a,.so}

.PHONY: install
install: all
	mkdir -p $(DESTDIR)$(PREFIX)/bin
	cp $< $(DESTDIR)$(PREFIX)/bin $(LIBNAME){.a,.so}

.PHONY: uninstall
uninstall:
	rm -f $(DESTDIR)$(PREFIX)/bin/$(LIBNAME){.a,.so}
