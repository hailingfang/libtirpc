# LIBTIRPC 0.1 FROM SUN'S TIRPCSRC 2.3 29 Aug 1994
## this repo is from others and conserved for python nis module
This package contains SunLib's implementation of transport-independent
RPC (TI-RPC) documentation.  This library forms a piece of the base of Open Network
Computing (ONC), and is derived directly from the Solaris 2.3 source.

TI-RPC is an enhanced version of TS-RPC that requires the UNIX System V
Transport Layer Interface (TLI) or an equivalent X/Open Transport Interface
(XTI).  TI-RPC is on-the-wire compatible with the TS-RPC, which is supported
by almost 70 vendors on all major operating systems.  TS-RPC source code
(RPCSRC 4.0) remains available from several internet sites.

This release was a native source release, compatible for
building on Solaris 2.3. It had been ported from FreeBSD 5.2.1 to GNU/Linux 
in 2004.

Applications linked with this release's librpc must link with the United
States domestic version of libcrypt in order to resolve the cbc_crypt() and
ecb_crypt() functions.  These routines are used with Secure RPC however all
RPC programs that link with this release's librpc will need to link with the
domestic libcrypt.  

WHAT'S NEW IN THIS RELEASE: TIRPCSRC 2.3 FROM SUN

The previous release was TIRPCSRC 2.0.

1.      This release is based on Solaris 2.3.  The previous release was
	based on Solaris 2.0.  This release contains a siginificant number of
	bug fixes and other enhancements over TIRPCSRC 2.0.

2.      The RPC library is thread safe for all client-side interfaces
	(clnt_create, clnt_call, etc.).  The server-side interfaces
	(svc_create, svc_run, etc.) are not thread safe in this release. The
	server-side interfaces will be made thread safe in the next release of
	TIRPCSRC.  Please see the manual pages for details about which
	interfaces are thread safe.

3.      As part of the work to make the RPC library thread-safe, rpcgen has
	been enhanced to generate thread-safe RPC stubs (the -M option).  Note
	that this modifies the call-signature for the stub functions; the
	procedure calling the RPC stub must now pass to the stub a pointer to
	an allocated structure where results will be placed by the stub.  See
	the rpcgen manual page and the rpcgen Programming Guide for details.


## Note

Can build without gssapi with option `--disable-gssapi`
