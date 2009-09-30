# Makefile

# Some values might need customization.

LUAINC = -I/usr/include/lua5.1
LUALIB = -llua5.1
LD = gcc -Wall -Werror -g -O2 -DNDEBUG -fPIC -fno-common -shared

CFLAGS = `libnet-config --cflags --defines` `dnet-config --cflags`
LDLIBS = `libnet-config --libs` `dnet-config --libs` $(LUALIB) -lrt -lm

net.so: net.c
	$(LD) $(LUAINC) $(CFLAGS) -o $@ $<  $(LDLIBS)

test: net.so
	sudo ./net-test

