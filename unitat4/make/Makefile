CC=gcc
CFLAGS=-Wall -g

calcula: calc.o calcula.c
	$(CC) $(CFLAGS) calc.o calcula.c -o calcula

calc.o: calc.c calc.h
	$(CC) $(CFLAGS) -c calc.c -o calc.o

.PHONY: clean
clean:
	rm -rf *.o
	rm calcula

.PHONY: dist
dist: calcula
	rm -rf ../dist;
	mkdir -p ../dist/usr/bin/calc
	cp calcula ../dist/usr/bin/calc

.PHONY: targz
targz:
	mkdir -p source
	cp *.c Makefile source
	tar -cvf calcula.tar source
	gzip calcula.tar
	rm -rf calcula.tar
	rm -rf source

install: dist
	cp -r ../dist/* /
