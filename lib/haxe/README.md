Thrift Haxe Software Library

License
=======

Licensed to the Apache Software Foundation (ASF) under one
or more contributor license agreements. See the NOTICE file
distributed with this work for additional information
regarding copyright ownership. The ASF licenses this file
to you under the Apache License, Version 2.0 (the
"License"); you may not use this file except in compliance
with the License. You may obtain a copy of the License at

  http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing,
software distributed under the License is distributed on an
"AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
KIND, either express or implied. See the License for the
specific language governing permissions and limitations
under the License.

Using Thrift with Haxe
========================

Haxe setup
---------------

Thrift requires Haxe 3.1.3. Installers for Windows and OSX
platforms are available at `http://haxe.org/download`. 

Depending on the desired targets, you may have to install the appropriate HaxeLibs 
after installing Haxe itself. For example, if you plan to target C#, Java and C++,
enter the following commands after installing Haxe:

    haxelib install hxcpp
    haxelib install hxjava
    haxelib install hxcs

For other targets, please consult the Haxe documentation whether or not any additional
target libraries need to be installed and how to achieve this.


Haxe on Linux 
---------------

For Linux platforms it is recommended not to download the 
binaries manually, instead use the Haxe installation shell 
script which can be found at `http://www.openfl.org/download`.

If you run into the error message 

    Uncaught exception - load.c(237) : Failed to load library : /usr/lib/neko/regexp.ndll  
	(libpcre.so.3: cannot open shared object file: No such file or directory)

this can be solved depending on your OSes bitness by either

    sudo ln -sf /usr/lib/libpcre.so.1 /usr/lib/libpcre.so.3
    sudo ldconfig
	
or

    sudo ln -sf /usr/lib64/libpcre.so.1 /usr/lib64/libpcre.so.3
    sudo ldconfig

Thrift Haxe bindings
-------------------
	
Thrift Haxe bindings can be set up via the `haxelib` tool  
either from the official ASF repo, or via the github mirror.

- To set up any **stable version**, choose the appropriate branch (e.g. `0.9.3`):

    - `haxelib git thrift https://git.apache.org/thrift.git 0.9.3 lib/haxe`
    - `haxelib git thrift https://github.com/apache/thrift.git 0.9.3 lib/haxe`

- To set up the current **development version**, use the `master` branch:
  
    - `haxelib git thrift https://git.apache.org/thrift.git master lib/haxe`	
    - `haxelib git thrift https://github.com/apache/thrift.git master lib/haxe`

As usual, the installed library can be updated using `haxelib upgrade` 
or `haxelib update thrift`.

In order to work with Thrift, you will need to install the Thrift compiler 
or build from source, depending on your operating system. Appropriate 
downloads and more information can be found at http://thrift.apache.org
	
To get started, visit the /tutorial/haxe and /test/haxe dirs for examples. 
If you are using HIDE or the FlashDevelop IDE, you'll find appropriate 
project files in these folders.


Current status
========================
- tested with Haxe C++ target
- transports: Socket, HTTP (client only), Stream
- protocols: Binary, JSON, Multiplex, Compact
- tutorial client and server available
- cross-test client and server available 


Further developments
========================
- improve to work with C#, Java and JavaScript Haxe/OpenFL targets
- improve to work with more (ideally all) Haxe/OpenFL targets
- add HTTP server, update tutorial and tests accordingly


Known restrictions
========================

Although designed with maximum portability in mind, for technical reasons some platforms
may only support parts of the library, or not be compatible at all.

Javascript:
- tutorial fails to build because of unsupported Sys.args

