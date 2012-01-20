MonoTouch BTouch Binding Sample
================

The new btouch tool for MonoTouch (and bmac for MonoMac) simplifies binding an Objective-C API and does the heavy lifting for you: registering the selectors, taking care of invoking the proper handle for overwritten classes, doing parameter checking and doing some of the common marshaling required for your project.

In this sample we'll go through the use case of binding a static Objective-C library for use in a MonoTouch application.


Using this Sample
======================

This sample consists of three distinct source projects:

-XCode Project in Objective-C
-MonoTouch Binding classes
-MonoTouch Sample Project

To compile the binding classes execute the following commands from the root directory:

- ```cd src/binding/```
- ```make```

The make command will execute the Makefile and create a XMBindingLibrary.dll in the binding directory. This .dll is created using the new ```LinkWithAttribute``` and will automatically embed the native library in your application.

How to Create a Universal Binary
======================

In order to understand how we've build a universal binary, open up the XCode XMBindingLibrarySample project. In this project we have created an additional ```Build Target```. This allows us to create a separate library in the Products folder of the source tree. In our Universal Build Target we have supplemented our build output with a post-build ```Run Script``` which allows us to ```lipo``` or create a "fat" multi-architecture library without affecting any of the individual libraries from standard build output.

![screenshot](http://i.imgur.com/6SIsx.png "Build Target - Run Script")







