Version 0.02;

-------------------------

This is far from finished and I apologize for its lack of
completeness.  This will be rectified over time.  Hopefully
it is useful nonetheless.

UPDATE: HEADER COMPRESSION IS SIMPLY BROKEN.  It will work
in some cases, but far from all.

This is not a complete implemtation of Draft-04 of HTTP/2.0.  
The expecation is this will evolve in the near future to approach
completeness.  

This does not yet inclue a Makefile.pl.  It will.  Soon.
For now it will need to be installed by hand which is probably 
best for something in this state.  Look at the usage in 
http2client.pl and http2server.pl for examples.

--------------------------

This bundle provides a number of libraries intended to
provide the basic necessitied for an HTTP/2.0 implementation.
The modules currently are as follows.

HTTP2::Draft

Base module that provide a namespace and basic functinality

HTTP2::Draft::Log

Provides a wrapperl for Log::Log4perl;

HTTP2::Draft::Compress
HTTP2::Draft::HeaderIndex

Modules for the implementation of the header compression spec.

HTTP2::Draft::Stream
HTTP2::Draft::Connection
HTTP2::Draft::Frame

Connection, Frame, and stream implementation.  Most of the heavy 
lifting occurs in Connection.  Each Frame has a sub class in
Frame.pm

HTTP2::Draft::Server
HTTP2::Draft::Client

An attempt to wrap the above code in a moduel to make Server and
Client implementaions simple.

IO::Async::HTTP2::Framer
IO::Async::HTTP2::FramerStream

IO::Async moduels for reading and writing HTTP/2.0 frames on the
wire.  

--------------------------

Also included are two scripts that use Server.pm and Client.pm
to implements a client and server:

apps/http2client.pl
apps/http2server.pl

--------------------------

Example:

From the ./apps directory:

perl http2server.pl

Thsi defaults to useing port 8443.

perl http2client.pl http://127.0.0.1:8443

The client has a relatively rich set of command line options.
Use the -h option for details.







