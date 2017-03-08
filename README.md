# HTTP_LOAD: Multiprocessing http test client #

http_load runs multiple http fetches in parallel, to test the
throughput of a web server.  However unlike most such test clients,
it runs in a single process, so it doesn't bog down the client
machine.  It can be configured to do https fetches as well.

See the manual entry for more details.

Files in this distribution:

    README    		this
    Makefile		guess
    http_load.c		source file
    http_load.1		manual entry
    timers.c		timers package
    timers.h		headers for timers package
    make_test_files   	simple script to create a set of test files

To build: If you're on a SysV-like machine (which includes old Linux systems
but not new Linux systems), edit the Makefile and uncomment the SYSV_LIBS
line.  If you're doing SSL, uncomment those lines too.  Otherwise, just do
a make.

## Getting Started ##

Clone the project in a new folder by the following commands: 

		$ git clone https://github.com/AbdallahCoptan/HTTP_LOAD.git
		$ cd HTTP_LOAD

### Building & Installing http_load ###

You just need to invoke a make command to install:

		$ cd HTTP_LOAD
		$ make
		$ sudo make install

To test if the http_load is installed successfully, by asking for the help by:

		$ ./http_load

Here is the output, which is the usage of the tool:

		usage:  ./http_load [-checksum] [-throttle] [-proxy host:port] [-verbose] [-timeout secs] [-sip sip_file]
			    -parallel N | -rate N [-jitter]
			    -fetches N | -seconds N
			    url_file
		One start specifier, either -parallel or -rate, is required.
		One end specifier, either -fetches or -seconds, is required.


## Using http_load Utility ##

To use the HTTP_LOAD utility, you need first to creat a file to contains the URLS or the servers you want to test so as following:

		$ cd HTTP_LOAD
		$ nano urls

And inside the file write each url in one line: (if you have apache server locally)

		http://127.0.0.1/
		http://10.10.1.200:80/  ## if remote Http server 
		http://google.com/
		...

**NOW** if you want to run the HTTP_LOAD test by the following command as an instance:

		$ ./http_load -rate 5 -seconds 10 urls

Here it is the output:

		49 fetches, 1 max parallel, 563990 bytes, in 10 seconds
		11510 mean bytes/connection
		4.9 fetches/sec, 56399 bytes/sec
		msecs/connect: 0.0879388 mean, 0.118 max, 0.065 min
		msecs/first-response: 0.204061 mean, 0.724 max, 0.161 min
		HTTP response codes:
		  code 200 -- 49

###Read More About HTTP Load Tools###

See also: test the [HTTP PING](http://www.acme.com/software/http_ping/) , Test the [HTTP GET](http://www.acme.com/software/http_get/) and have a look for a page of other [HTTP Load Test Tools](http://www.softwareqatest.com/qatweb1.html#LOAD)

### Reference ###
Actually, the work of the HTTP_LOAD tool is credited to the http_load [page](http://www.acme.com/software/http_load/), but this unfortunately is not on github and that is why i upload it here and provide some help !!!

For any more questions and comments please send [abdallah.cisco@gmail.com]()
