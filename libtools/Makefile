### get external defined data

### constant symbols

ARCH ?=
CROSS_COMPILE ?=
CC := $(CROSS_COMPILE)gcc
AR := $(CROSS_COMPILE)ar

CFLAGS := -O2 -Wall -Wextra -std=c99 -Iinc -I.

OBJDIR = obj
INCLUDES = $(wildcard inc/*.h)

### linking options

### general build targets

all: libtinymt32.a libparson.a libbase64.a liblinenoise.a linenoise_example

clean:
	rm -f libtinymt32.a
	rm -f libparson.a
	rm -f libbase64.a
	rm -f liblinenoise.a
	rm -f linenoise_example
	rm -f $(OBJDIR)/*.o

### library module target

$(OBJDIR):
	mkdir -p $(OBJDIR)

$(OBJDIR)/%.o: src/%.c $(INCLUDES) | $(OBJDIR)
	$(CC) -c $(CFLAGS) $< -o $@

### static library

libtinymt32.a:  $(OBJDIR)/tinymt32.o
	$(AR) rcs $@ $^

libparson.a:  $(OBJDIR)/parson.o
	$(AR) rcs $@ $^

libbase64.a:  $(OBJDIR)/base64.o
	$(AR) rcs $@ $^
	
liblinenoise.a:  $(OBJDIR)/linenoise.o
	$(AR) rcs $@ $^

### test programs

linenoise_example: $(OBJDIR)/linenoise.o $(OBJDIR)/linenoise_example.o
	$(CC) -o $@ $^
	
### EOF
