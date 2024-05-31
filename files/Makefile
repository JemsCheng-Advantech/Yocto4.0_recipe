PWD = $(shell pwd)
SRC = hellogtk.c
LOCAL_TARGET = hellogtk

#CC=aarch64-linux-gnu-gcc
#CC=gcc

CFLAGS += $(shell pkg-config --cflags gtk+-3.0)
LDFLAGS += $(shell pkg-config --libs gtk+-3.0)



all: $(LOCAL_TARGET)

$(LOCAL_TARGET):
	$(CC) $(SRC) $(LDFLAGS) $(CFLAGS) -o $@


clean:

