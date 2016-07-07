CC=gcc
CFLAGS=-c -std=c99 -Wall -fPIC
SOURCES=edgefixer.c vsplugin.c
OBJECTS=$(SOURCES:.c=.o)
LIBNAME=edgefixer

all:
	$(CC) $(CFLAGS) $(SOURCES)
	ar cru $(LIBNAME).a $(OBJECTS)
	$(CC) -shared -o $(LIBNAME).so $(OBJECTS)

clean:
	-rm -f $(OBJECTS) $(LIBNAME).a $(LIBNAME).so
