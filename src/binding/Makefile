BTOUCH=/Developer/MonoTouch/usr/bin/btouch

all: XMBindingLibrary.dll

XMBindingLibrary.dll: Makefile AssemblyInfo.cs XMBindingLibrarySample.cs libXMBindingLibrarySampleUniversal.a
	$(BTOUCH)  XMBindingLibrarySample.cs AssemblyInfo.cs --out=$@ --link-with=libXMBindingLibrarySampleUniversal.a,libXMBindingLibrarySampleUniversal.a -x=extras.cs

clean:
	-rm -f *.a *.dll
