#common makefile header

DIR_INC = ../../include
DIR_BIN = ../../bin

TARGET	= tts
BIN_TARGET = $(DIR_BIN)/$(TARGET)

CROSS_COMPILE = 
CFLAGS = -g -Wall -I$(DIR_INC)

LDFLAGS = -lmsc -lrt -ldl -lpthread

OBJECTS := $(patsubst %.c,%.o,$(wildcard *.c))

$(BIN_TARGET) : $(OBJECTS)
	$(CROSS_COMPILE)gcc $(CFLAGS) $^ -o $@ $(LDFLAGS)

%.o : %.c
	$(CROSS_COMPILE)gcc -c $(CFLAGS) $< -o $@
clean:
	@rm -f *.o $(BIN_TARGET)

install:
	@mv $(BIN_TARGET) /usr/bin

.PHONY:clean

#common makefile foot
