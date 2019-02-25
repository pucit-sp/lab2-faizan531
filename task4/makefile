
all:myapp
CC=gcc
LIBS=myfunctions
LIBPATH=.
INCLUDEPATH=.
INSTALLDIR=/usr/bin
OBJS= ./prog1/prog1.o prog2.o prog3.o prog4.o
myapp: driver.o header.h libmyfunctions.a
	$(CC) -o myapp --static driver.o -lmyfunctions -L. -I.
diver.o: driver.c
	$(CC) -c driver.c
libmyfunctions.a: $(OBJS)
	ar -rs libmyfunctions.a $(OBJS)
prog1.o: prog1.c
	$(CC) -c -fPIC prog1.c
prog2.o: prog2.c
	$(CC) -c -fPIC prog2.c
prog3.o:prog3.c
	$(CC) -c -fPIC prog3.c
prog4.o: prog4.c
	$(CC) -c -fPIC prog4.c
include: ./prog1/makefile

clean:
	-@rm -f *.o
install: myapp
	@cp myapp $(INSTALLDIR)
	@chmod a+x $(INSTALLDIR)/myapp
	@chmod og-w $(INSTALLDIR)/myapp
	@echo "myexe has been Installed Successfully in $(INSTALLDIR)";
uninstall:
	@rm -f $(INSTALLDIR)/myapp
	@echo "myapp has been uninstalled from $(INSTALLDIR)";
