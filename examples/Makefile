#
# Copyright (c) 2020 Lucas Müller
#
# Permission is hereby granted, free of charge, to any person obtaining a copy
# of this software and associated documentation files (the "Software"), to deal
# in the Software without restriction, including without limitation the rights
# to use, copy, modify, merge, publish, distribute, sublicense, and/or sell
# copies of the Software, and to permit persons to whom the Software is
# furnished to do so, subject to the following conditions:
#
# The above copyright notice and this permission notice shall be included in all
# copies or substantial portions of the Software.
#
# THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS OR
# IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF MERCHANTABILITY,
# FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT. IN NO EVENT SHALL THE
# AUTHORS OR COPYRIGHT HOLDERS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
# LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING FROM,
# OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER DEALINGS IN THE
# SOFTWARE.
#

TOP	:= ..
CC	?= gcc

LIBDIR	:= $(TOP)/lib

LIBJSCON_CFLAGS		:= -I$(TOP)/include/
LIBJSCON_LDFLAGS	:= "-Wl,-rpath,$(LIBDIR)" -L$(LIBDIR) -ljscon

LIBS_CFLAGS	:= $(LIBJSCON_CFLAGS)
LIBS_LDFLAGS	:= $(LIBJSCON_LDFLAGS)

CFLAGS	:= -Wall -Werror -Wextra -pedantic -g

.PHONY : clean purge

all : run-append run-scanf

run-append : append.c $(LIBDIR) Makefile
	$(CC) $(CFLAGS) $(LIBS_CFLAGS) \
	      append.c -o $@ $(LIBS_LDFLAGS)

run-scanf : scanf.c $(LIBDIR) Makefile
	$(CC) $(CFLAGS) $(LIBS_CFLAGS) \
	      scanf.c -o $@ $(LIBS_LDFLAGS)

$(LIBDIR) :
	$(MAKE) -C $(TOP)

clean :
	rm -rf run-append run-scanf *.txt
