.PHONY: all clean mac unmac

all: ask2-signals

CC = gcc
CFLAGS = -g -Wall -O2

ask2-signals: ask2-signals.o proc-common.o tree.o
	$(CC) $(CFLAGS) $^ -o $@

%.o: %.c
	$(CC) $(CFLAGS) -c $<

.PHONY:
	clean

clean:
	rm -f *.o ask2-signals{,.o} proc-common.o

mac:
	patch proc-common.c ../mac-port/proc-common-mac.patch
	patch tree.c ../mac-port/tree-mac.patch

unmac:
	patch -R proc-common.c ../mac-port/proc-common-mac.patch
	patch -R tree.c ../mac-port/tree-mac.patch
