Installation
======

This will compile and install the files in your /usr/lib and /usr/include directories.

	make
	make install

Make a test with :

	make test
	// Will compile and run two test executables
	//	./hex 2014 1024 512 256 128 64 16 0
	//	./dec 7DE 400 200 100 80 40 10 0

Clean output files with :

	make clean

Usage
======

Include the following librairy :

	<libhex.h>

Use the flag <code>-lhex</code> ~~and <code>-lm</code>~~ to link with the libhex librairy ~~and math librairy~~.

Fonctions
------

###char* dechex ( unsigned dec, char *hex, int len, int fill )


Convert a Decimal unsigned int in an Hexadecimal string.
First argument is the decimal to convert.
The second one is the output buffer, if NULL passed it will use malloc to allocate sufficient memory, so don't forget to free() if you're programming in C/C++.
The next argument is buffer's length can be any value if NULL is passed because length wil be calculated.
And the last argument is to make string start at first address and filled with zero at end.

###void init_hexdec ( void )

Intitialize the hexadecimal to decimal conversion array.

###unsigned hexdec ( const unsigned char *hex, const int s_hex )

Convert an Hexadecimal string to a Decimal int.

Check for <code>errno == EINVAL</code>, if string contains invalid hexadecimal character.

Note : Call the function init_hexdec() once before you convert hexadecimal to decimal.

###char hexascii ( const unsigned char *hex )

Convert two characters length string to character according the ASCII Table.

Note : Call the function init_hexdec() once before you convert decimal to hexadecimal.

TODO
======

- Make fonctions for encoding/decoding ASCII strings.

