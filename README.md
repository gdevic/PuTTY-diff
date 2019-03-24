# PuTTY-diff
PuTTY modifications for GitForce project

Compile PuTTY:
On Windows, need to have Perl. Use Strawberry Perl from here: http://strawberryperl.com/ and download a Portable edition
Run "portableshell.bat" to get the Perl PATH set up (or you can set it up manually, see README.TXT)

Check the latest version of PuTTY from home here: https://www.chiark.greenend.org.uk/~sgtatham/putty/latest.html
Clone git repo:  https://git.tartarus.org/simon/putty.git

Make Windows PuTTY build: perl mkfiles.pl
Apply a patch to PuTTY sources: git apply --reject --whitespace=fix ...\PuTTY-diff\putty.diff
At this point, Windows\version.h contains GitForce-specific defines but also the BINARY_VERSION (base Putty version) - which may need to be incremented.

Open the solution file in Visual Studio 2015: windows\VS2012\putty.sln
Select Release build and rebuild all.
