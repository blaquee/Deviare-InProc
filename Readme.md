﻿Deviare In-Proc is a code interception engine for Microsoft Windows® developed by
[Nektra Advanced Computing](http://www.nektra.com).

This library is at the core of our [Deviare v2.0](http://www.nektra.com/products/deviare-api-hook-windows/)
and [SpyStudio Application Monitor](http://www.nektra.com/products/spystudio-api-monitor/) technologies.
Deviare is an alternative to Microsoft Detours® but with a dual license distribution.

The library is coded in C++ and provides all the facilities required to
instrumenting binary libraries during runtime. It includes support for both 32
and 64 bit applications and it implements the interception verifying different
situations that can crash the process. If you need to intercept any Win32
functions or any other code, this library makes it easier than ever.

Unlike the rest of the libraries, Deviare In-Proc provides a safe mecanism to
implement multi-threaded application API hooking. When an application is
running, more than one thread can be executing the code being intercepted.
Deviare In-Proc provides safe hooking even in this scenario.


----------------------
# MINIMUM REQUIREMENTS

To use Deviare In-Proc you must have the following:

- IBM PC or compatible.
- Microsoft Windows 2000 or later.
- Visual Studio 2008 or later (with latest available Service Pack recommended).


----------------------
# INSTALLATION & USAGE

Uncompress the downloaded .zip file in an empty folder.

If the package contains the source code, you can open the `NktHookLib.sln` with
Visual Studio to rebuild the libraries.

The *LIBS* subfolder contains precompiled libraries of the product.

To use the library in your project, add the reference to the `NktHookLib.h` file
located in the *INCLUDE* forder and ensure to link with the correct library.
The provided HookTest sample contains `#pragma` sentences you can use to tell
the linker to add the libraries depending on the platform.  


------------------------
# .NET FRAMEWORK SUPPORT

The **new** experimental feature of Deviare In-Proc is **the ability to hook
.NET methods** and redirect them to your own. Feel free to examine the provided
C# samples to see .net method hooking in action.


-----------------
# C RUN-TIME LESS

Although the library functionallity remains the same, the code was modified to
make it independant from Visual Studio's CRT libraries.

Deviare In-Proc base library only depends on *NTDLL.DLL*, no *kernel32.dll* nor
another library is used.

It also does a dynamic discovery of needed apis in order to eliminate
*NTDLL.DLL* static binding when used in an application or dll. This allows
developers to use the library, for e.g., in custom dll's that will be injected
in non-initialized processes that ware launched in a suspended state.

The C ApiHook sample provided with this package was also modified in order to
demostrate how to build an executable with minimal imported api's. Because
Visual Studio's compiler & linker inserts undesired Microsoft's specific code
and data, the sample contains some hacks and modified compiler switches to
circumvent this behavior.


-------------
# BUG REPORTS

If you experience something you think might be a bug in Deviare In-Proc, please
report it in GitHub repository or write us in <http://www.nektra.com/contact/>.

Describe what you did, what happened, what kind of computer you have, which
operating system you're using, and anything else you think might be relevant.


-----------------------
# LICENSING INFORMATION

This library has a dual license, a commercial one suitable for closed source
projects and a GPL license that can be used in open source software.

Depending on your needs, you must choose one of them and follow its policies.
A detail of the policies and agreements for each license type are available in
the *LICENSE.COMMERCIAL* and *LICENSE.GPL* files.

For further information please refer to <http://www.nektra.com/licensing/> or
contact Nektra here <http://www.nektra.com/contact/>.

This library uses a portion of UDis86 project <http://udis86.sourceforge.net/>,
authored, copyrighted and maintained by Vivek Thampi. UDis86 is licensed under
the terms of BSD License. For any questions referring to UDis86 contact the
author at vivek[at]sig9[dot]com.
