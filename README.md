AVID SCROLLER & Simple Scroll Hook
----------------------------------
<br>

Scrolling Configuration Editor and Modifications<br>
Open Source and cross compatable : Windows/OSX/GNU-Linux

- CLI (written in C)
- GUI (written in Python)
<br>
Written by : Kevin Swain
<br>
This software is free to redistribute in part or whole as your own as
It is now a part of public domain. Learn!
<br>
Written for 2019 competition with programmerhumor.com
Simple Scroll Hook is a proof of Concept on the fly scroll speed changer
Which shows how rediculous thecontest entry program is.
<br>


LICENCE
-------

This is free and unencumbered software released into the public domain.

Anyone is free to copy, modify, publish, use, compile, sell, or
distribute this software, either in source code form or as a compiled
binary, for any purpose, commercial or non-commercial, and by any
means.

In jurisdictions that recognize copyright laws, the author or authors
of this software dedicate any and all copyright interest in the
software to the public domain. We make this dedication for the benefit
of the public at large and to the detriment of our heirs and
successors. We intend this dedication to be an overt act of
relinquishment in perpetuity of all present and future rights to this
software under copyright law.

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND,
EXPRESS OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR
OTHER LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE,
ARISING FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR
OTHER DEALINGS IN THE SOFTWARE.

For more information, please refer to <http://unlicense.org>
<br>



What is Avid Scroller?
----------------------

A set of tools along with a GUI that allow you to customize
everything about your mouse scrolling speeds. Avid Scroller
is essentially controlled with an input configuration file.
The Frontend makes customizing this configuration file 
extremely easy, though with enough practice one can write
a configuration file without it or use the CLI.

It was written with multiple platforms in mind, and can run
on Windows, GNU/Linux, and OSX provided it is built specifically
for said OS.

Python was chosen as the frontend language as it is multi
platform as well.
<br>



Overview of Functionality
-------------------------

Set Scroll speed (or disable) based on:
  - OS used
  - User logged in
  - Application used, individually
  - Time of day (to and from), daily
  - Set configuration for future date

If you learn the configuration files and how they are written
(Check the commented sections), you can set these behaviors
to specific dates of the week. eg. Fast scroll friday. Slow
scroll Sunday.


Avid scroller really takes scrolling to the next level. An
example configuration file can be found in the build folder
at settings.conf.
<br>



Requirements
------------

- CMAKE - Newest version, no lower than 2.6.3
- Python 2.7. Python 3 is not supported
- Builds are 32bit for comparability.
<br>


Building
--------

Download Avid Scroller from the GIT repository found here, and these commands:

> git clone https://github.com/kbs-os/AvidScroller/edit/master <br>
> cmake <br>
> make <br>
> [sudo] make install <br>

Note: you may need to be super user for last command. Debian derived 
Distributions add 'sudo' before make install.
<br>


Quickstart
----------

Launch the frontend and select 'File', 'New'. Here you will
generate a configuration template. Your OS will be detected
 and automatically chosen. You can override this
by clicking the 'override' box. This way your configuration
will also work on other operating systems. If this box is not
checked, your configuration will only work on the OS you 
are currently using.

Configuration files are saved in UTF-8 character encoding by
default. You are able to change this to various others including:
- todo
- todo
-
- ...
-

Avid Scroller will find all of your applications. from there
the rest is straight forward. The configuration file must be
saved by using File > Save or it will not be written after
exiting.
<br>


CLI
---
If you are running a headless distribution, you can still use Avid Roller.
Create a barebones template using the flags below, then edit them in an
Console text editor like vim or nano.

Avid Scroller can generate configurations using the -c flag with
Other relevant flags:

./aRoller -c (ARGS)

ARGS:<nl>
- -c // new config
- -os [win/osx/linux] // OS on host computer
- -O [0/1] // Override OS check
- -e [character encoding] // default utf-8
- -u [account name] // Apply only while logged in specific account
- -b [app bin] // *nix /usr/bin, win "C:\Program Files"
- -a [apps, separated by commas]
- -D [1/0] // Disable scroll
- -S [-20/+20] // Scroll Speed. 0 default
- -A [1/0] // Autostart on boot
- -o [filename.conf] // output config 
- -C [Config] // load config , no other args
- -h // This help menu

Eg. Load config which already exists:

> ./aScroller -C settings.conf<br>
> [OK] Configuration file loaded successfully

Running aScroller with the -h or without arguments will 
display the proper way to load it.

It is not possible to tweak the configuration more by command line,
However the generated output config will be heavily commented to
Guide you through the process. Or the front end can load your CLI
Generated config to farther customize.
<br>

Heirerarchy of Configuration
----------------------------

Any configurations set for a future date will overwrite that
of daily configurations. So please keep that in mind.

<BR>
  EOF 12.08.2019



