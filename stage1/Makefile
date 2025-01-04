CC=gcc
CFLAGS=-I.

#adding - to rm, to fallback to next target
clean:
	-rm *.o
test: test.o
	$(CC) -o test test.o
