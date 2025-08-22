CFLAGS ?= -Wall -Wextra -std=c99

ifeq ($(OS),Windows_NT)
	LDFLAGS = -lgdi32
else
	UNAME_S := $(shell uname -s)
	ifeq ($(UNAME_S),Darwin)
		LDFLAGS = -framework Cocoa
	else
		LDFLAGS = -lSDL3 -DUSE_SDL -I/usr/include/SDL3
	endif
endif

main: main.c ../../fenster.h
	$(CC) main.c -I../.. -o $@ $(CFLAGS) $(LDFLAGS)
