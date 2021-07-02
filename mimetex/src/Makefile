# build mimetex executable when user executes "make"
mimetex: mimetex.o
	$(CC) $(LDFLAGS) -DAA mimetex.c gifsave.c -lm -o mimetex

mimetex.o: mimetex.c
	$(CC) $(CFLAGS) -c mimetex.c

# remove object files and executable when user executes "make clean"
clean:
	rm *.o mimetex