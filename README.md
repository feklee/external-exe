Introduction
============

External.exe allows using an external editor from any Windows application. It
was originally developed by Ben Collerson, starting from discussions around
[Vim tip 805][1].

With version 0.3 and with permission from Ben, External.exe has been updated
from GPLv2 to GPLv3 and hosting has moved.


Example Use Case
================

 1. In a web browser's text entry box you hit a keyboard shortcut, such as
    *Windows-V.*

 2. The current contents of the text entry box open in a text editor, for
    example Notepad.

 3. You edit the text and save your changes.

 4. After exiting Notepad, the edited text is automatically copied back into
    the browser's text area.

The key combination as well as the text editor may be freely configured.


Installation and Configuration
==============================

After downloading and unpacking the software, ensure that the files
`external.exe` and `external.ini` are in a directory together.

Open `external.ini` in a text editor and set the options `Editor` and
`!EditorBinding` as explained in the comments in the file.

The program can be started by manually running the `external.exe` command. But
once you get a configuration you like you may want to place a shortcut in your
`Start/Programs/Startup` folder so it will be automatically executed.

Tip: When configuring `external.exe` it can be useful to use the Restart
(*Shift-Ctrl-Alt-R*) and Exit (*Shift-Ctrl-Alt-X*) bindings to reconfigure your
program.


Usage
=====

To use the program, once it is configured and running, move the cursor to the
text area of an application and type your `!EditorBinding` keystroke
(*Windows-V,* for example)


Vim
===

Provided with the program is a [Vim][2] script `external.vim`. This file can be
installed by putting it in your Vim plugin folder. With an appropriately
configured `Editor` option in `external.ini` Vim will be able to recognize the
filetype of the text you are editing by using the application window title as a
clue.

`external.vim` has so far only been tested on a small number of applications
and filetypes, but it should be relatively easy to add new filetypes by
modifying the `External()` function in the script.


Compilation from source code
============================

 1. Install [AutoIt][3] v3 or compatible.

 2. Compile `external.au3` to `external.exe`:

        Aut2exe.exe /in external.au3 /out external.exe /icon logo.ico /x86 /gui

 3. And/Or compile a version for 64 bits:

        Aut2exe_x64.exe /in external.au3 /out external_x64.exe /icon logo.ico ^
            /x64 /gui


License
=======

Author: Ben Collerson &lt;benc at bur dot st&gt;  
Contributor: [Felix E. Klee](mailto:felix.klee@inka.de)  
Last Modified: 06 Oct 2015  
Version: 0.3.1  
Logo: Based on <http://en.wikipedia.org/wiki/File:External.svg> (public domain)

Copyright (C) 2005–2015 Ben Collerson &lt;benc at bur dot st&gt;,
[Felix E. Klee](mailto:felix.klee@inka.de)

This file is part of External.exe.

External.exe is free software: you can redistribute it and/or modify it under
the terms of the GNU General Public License as published by the Free Software
Foundation, either version 3 of the License, or (at your option) any later
version.

This program is distributed in the hope that it will be useful, but WITHOUT ANY
WARRANTY; without even the implied warranty of MERCHANTABILITY or FITNESS FOR A
PARTICULAR PURPOSE. See the GNU General Public License for more details.

You should have received a copy of the GNU General Public License along with
this program. If not, see <http://www.gnu.org/licenses/>.


[1]: http://vim.wikia.com/wiki/VimTip805
[2]: http://vim.sourceforge.net/
[3]: https://en.wikipedia.org/wiki/AutoIt
