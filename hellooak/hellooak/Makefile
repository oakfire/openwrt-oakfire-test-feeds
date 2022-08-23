# build helloworld executable when user executes "make"
hellooak: hellooak.o
	$(CC) $(LDFLAGS) hellooak.o -o hellooak
hellooak.o: hellooak.c
	$(CC) $(CFLAGS) -c hellooak.c
# remove object files and executable when user executes "make clean"
clean:
	rm *.o hellooak
