TARGET = xv11test
LIBS = 
CC = gcc
CFLAGS = -Wall

.PHONY: default all clean

default: $(TARGET)
all: default

OBJECTS = $(patsubst %.c, %.o, $(wildcard *.c))
HEADERS = $(wildcard *.h)

%.o: %.c $(HEADERS)
	$(CC) $(CFLAGS) --std=c99 -c $< -o $@

.PRECIOUS: $(TARGET) $(OBJECTS)

$(TARGET): $(OBJECTS)
	$(CC) $(OBJECTS) --std=c99 -Wall $(LIBS) -o $@ -lm

clean:
	-rm -f *.o
	-rm -f $(TARGET)
