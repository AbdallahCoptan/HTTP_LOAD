# HTTP_LOAD: Multiprocessing http test client #

http_load runs multiple http fetches in parallel, to test the
throughput of a web server.  However unlike most such test clients,
it runs in a single process, so it doesn't bog down the client
machine.  It can be configured to do https fetches as well.

See the manual entry for more details.

Files in this distribution:

    README		this
    Makefile		guess
    http_load.c		source file
    http_load.1		manual entry
    timers.c		timers package
    timers.h		headers for timers package
    make_test_files	simple script to create a set of test files

To build: If you're on a SysV-like machine (which includes old Linux systems
but not new Linux systems), edit the Makefile and uncomment the SYSV_LIBS
line.  If you're doing SSL, uncomment those lines too.  Otherwise, just do
a make.

## Get Starting ##

Clone the project in a new folder by the following commands: 

		$ git clone https://github.com/AbdallahCoptan/HTTP_LOAD.git
		$ cd HTTP_LOAD
