MonoTouch BTouch Binding Sample
================

This example shows how we can utilize an existing Objective-C library and expose it for use in a MonoTouch project. For instance, you may have existing code written in Objective-C that you may want to bind to C# to consume in your MonoTouch project. This sample provides a basic template/overview of the steps involved, including:

- Creating a "fat" or multi-architecture library that can be target both the iOS simulator and device.
- Defining an API definition file in the form of a C# interface against the Objective-C API.
- Building a ```*.dll``` that contains both the binding and and the embedded native library.


Understanding this Sample
======================

This sample consists of three distinct source projects:

- XCode Project in Objective-C
- MonoTouch Binding classes
- MonoTouch Sample Project

To compile the binding classes execute the following commands from the root directory:

- ```cd src/binding/```
- ```make```

The make command will execute the Makefile and create a XMBindingLibrary.dll in the binding directory. This .dll is created using the new ```LinkWithAttribute``` and will automatically embed the native library in your application.

How to Create a Universal Binary
======================

In order to understand how we've build a universal binary, open up the XCode XMBindingLibrarySample project. In this project we have created an additional ```Build Target```. This allows us to create a separate library in the Products folder of the source tree. In our Universal Build Target we have supplemented our build output with a post-build ```Run Script``` which allows us to ```lipo``` or create a "fat" multi-architecture library without affecting any of the individual libraries from standard build output.

![screenshot](http://i.imgur.com/6SIsx.png "Build Target - Run Script")







