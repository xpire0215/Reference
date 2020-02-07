# set include path

### First

Find the include path

>> gcc -v

```	
Configured with: --prefix=/Applications/Xcode.app/Contents/Developer/usr 
				 --with-gxx-include-dir=/Applications/Xcode.app/Contents/
				 Developer/Platforms/MacOSX.platform/Developer/SDKs/
				 MacOSX10.14.sdk/usr/include/c++/4.2.1
	Apple LLVM version 10.0.0 (clang-1000.11.45.2)
	Target: x86_64-apple-darwin18.0.0
	Thread model: posix
	InstalledDir: /Applications/Xcode.app/Contents/Developer/Toolchains/
				  XcodeDefault.xctoolchain/usr/bin
```

### Second

We get the include path

```
/Applications/Xcode.app/Contents/Developer/usr --with-gxx-include-dir=/
Applications/Xcode.app/Contents/Developer/Platforms/MacOSX.platform/Developer/
SDKs/MacOSX10.14.sdk/usr/include/
```

Add the directory of the headers into the include path.
