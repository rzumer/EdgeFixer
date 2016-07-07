all:
	gcc -c -std=c99 -Wall -fpic edgefixer.c vsplugin.c
	ar cru edgefixer.a edgefixer.o vsplugin.o
	gcc -shared -o edgefixer.so edgefixer.o vsplugin.o
