objects = foo.o bar.o
libs = libfoo.so

app: $(libs)
	gcc main.c -o app -lfoo -L$(PWD)/src -Wl,-rpath-link=$(PWD)/src
		
foo.o: 
	gcc -c -fPIC foo.c
	
bar.o:
	gcc -c -fPIC bar.c

libfoo.so: $(objects)
	gcc -shared foo.o -o libfoo.so

.PHONY: clean
clean: 
	@rm app $(objects) $(libs)
