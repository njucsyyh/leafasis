# Introduction #

opencv2.1+QT+Eclipse

http://tech.groups.yahoo.com/group/OpenCV/message/71043
# Details #


Installation Procedure OpenCV 2.1 - Eclipse CDT 6 - MinGW with gcc 4.5 - MSYS
with GNU Make 3.81 - cmake-2.8.1
Step Procedure & Program & Version
0 see OpenCV Installation Guide
"..\Installazioni\OpenCV-Library\ImportantGuide\InstallGuide - OpenCV Wiki.pdf |
OpenCV-2.1-Readme.txt"
http://opencv.willowgarage.com/wiki/InstallGuide
- Install 7Zip for unxzip archive:
"Installazioni\Eclipse\c++\7z913.exe"
For all the process of unzip archive/file use 7Zip
1 Installare Eclipse CDT 6.0 (Eclipse C++ plugin) after the installation of
eclipse.
Installation of Eclipse
install the Java JDK "Installazioni\JavaJDK6\jdk-6u20-windows-i586.exe":
java version "1.6.0\_20"
Java(TM) SE Runtime Environment (build 1.6.0\_20-b02)

And after unarchive the
\Installazioni\Eclipse\javaeclipse-jee-galileo-SR2-win32.zip under
"C:\eclipse-jee-galileo-SR2-win32"
To install the Eclipse CDT 6.0 plug in:
Launch eclipse and use the update functionality of Eclipse to download the
latest CDT plugin:
Help->Install New software (select the link available software site and copy the
url of Galileo "http://download.eclipse.org/releases/galileo"in the field "work
with"of the previous window "Available Software". Then start the search and
select to install CDT )
Install Cmake Eclipse Editor
see http://www.cthing.com/CMakeEd.asp
see "Installazioni\Eclipse\c++\C++ Development using eclipse IDE Starters
guide.pdf"
2 IMPORTANT
Install MinGW MinGW-5.1.6.exe + Update gcc\_4.5:
execute the installer of "Installazioni\Eclipse\c++MinGW-5.1.6.exe" select the
root directory of installation of MinGW "C:\MinGW" Select download and install
the MinGW base tools and the g++ compiler. Do not install the MinGW Make feature
as the MSYS version of make from step 3 is a more complete implementation of
make
Unzip the updated library for gcc & dbg (The MinGW setup program currently does
not install the gdb debugger so follow the instruction)
"Installazioni\Eclipse\c++\gcc\_4.5\_Update\UnArchive" under the directory where
was installed "C:\MinGW"
see instruction
"Installazioni\Eclipse\c++\gcc\_4.5\_Update\gcc-4.5.0-1-mingw32.RELEASE\_NOTES.txt"
3 IMPORTANT (Install the shell of unix-like for windows with make program)
Install MSYS "Installazioni\Eclipse\c++\MSYS-1.0.11.exe" that include GNU Make
3.81. select the root directory of installation of MSYS "C:\msys\1.0"
update the version of MSYS to MSYS\_1.0.14 Unzip the updated library
"Installazioni\Eclipse\c++\MSYS\_1.0.14\_Update" under the directory where was
installed MSYS "C:\msys\1.0".
Execute the post installation procedure:
"C:\msys\1.0\postinstall\pi.bat" where you have to indicate the directory where
was installed "C:\MinGW"
IMPORTANT Add on the PATH variable environment of windows the following
directories for MinGW and MSYS:
PATH
......;C:\MinGW\bin;C:\msys\1.0\bin;C:\Programmi\CMake 2.8\bin
4 Install Cmake 2.8.1 "Installazioni\OpenCV-Library\cmake-2.8.1-win32-x86.exe"
5 Unzip the "\Installazioni\OpenCV-Library\OpenCV-2.1.0-win.zip" archive under
the directory "C:\OpenCV2.1.0"
Run Cmake 2.8.1
--IMPORTANT See step 7 before to proceed
--Insert the root source directory of OpenCV 2.1 "C:\OpenCV2.1.0"
--Insert the build output directory of OpenCV 2.1
"C:\OpenCV2.1.0-work\OpenCV\_MinGW\release" It is the directory where at the end
of bulding with eclipse (step 6..8) we have the build release version for
windows of OpenCV 2.1
Click on Configure button
Select:
eclipse CDT4 Unix Makefiles (PROCEDURA UTILIZZATA in tal caso non installare
come consigliato make di MinGW in modo da usare quello di MSYS)
After the click on Configure button on the output:
set CMAKE\_BUILD\_TYPE to Release
Select the other preferenze
see
"..\Installazioni\OpenCV-Library\ImportantGuide\OpenCV\_2\_0\_Installation.pdf":
The option chosen: BUILD\_EXAMPLES, BUILD\_PACKAGES, BUILD\_TEST,
INSTALL\_C\_EXAMPLES, OPENCV\_BUILD\_3RDPARTY\_LIBS,
(OPENCV\_WHOLE\_PROGRAM\_OPTIMIZATION it is not available).
Click another time on Configure button and then on Generate.
6
see
"..\Installazioni\OpenCV-Library\ImportantGuide\CMAKE\_Eclipse\_CDT\_Generator-impo\
rte\_in\_Eclipse .pdf"
Cmake 2.8.1 creates a set of .project/.cproject files that can be imported in
Eclipse as an "Existing Eclipse project".
Follow the instruction included in "Using Eclipse CDT4 Generator" -> "Import
the created project file into Eclipse"
http://www.cmake.org/Wiki/Eclipse_CDT4_Generator
To import the project in eclipse create a new workspace
(C:\workspaces\workspaceOpenCV2\_1\_0\.metadata) and :
Import the created project file into Eclipse
1. Import project using Menu File->Import
2. Select General->Existing projects into workspace:
3. Browse where your build tree is and select the root build tree directory.
Keep "Copy projects into
workspace" unchecked.
4. You get a fully functional eclipse project
Definitive Build RELEASE Installation (dll) of OpenCV 2.1.0 is under:
C:\OpenCV2.1.0-work\OpenCV\_MinGW\release

Optional
see also "..\Installazioni\OpenCV-Library\ImportantGuide\" to the option of
compile in debug mode
Follow the instruction included in "Changing Build Configuration to Release"
http://wiki.wxwidgets.org/Eclipse,_CDT_&_MingW_&_MSYS_Setup_Guide#Changing_the_B\
uild\_Configuration
7 see solution For compiling error:
make[2](2.md): **[bin/libhighgui210.dll] Error 1
> make[1](1.md):** [src/highgui/CMakeFiles/highgui.dir/all] Error 2
Substitute - before to compile OpenCV 2.1 on the source directory
"C:\OpenCV2.1.0\3rdparty\lib" the original dll libvideoInput.a shipped with
OpenCV 2.1 with the one saved in
"Installazioni\OpenCV-Library\ImportantGuide\LibrerieCorrette" - then substitute
the file src/highgui/CMakeLists.txt with the one saved in
"Installazioni\OpenCV-Library\ImportantGuide\LibrerieCorrette\OpenCV2.1.0src\_h\
ighgui\_CMakeLists.txt" renamed in CMakeLists.txt. - then substitute the file
OpenCV2.1.0/CMakeLists.txt with the one saved in
"Installazioni\OpenCV-Library\ImportantGuide\LibrerieCorrette\OpenCV2.1.0\_CMakeL\
ists.txt" renamed in CMakeLists.txt.

See Documentation
http://code.google.com/p/pyopencv/wiki/Installation_OpenCV
http://code.google.com/p/pyopencv/
http://openmp.org/wp/
Tracker: Bugs under Open Computer Vision Library
libvideoInput and gcc 4.4.x - ID: 2939647
http://sourceforge.net/tracker/index.php?func=detail&aid=2939647&group_id=22870&\
atid=376677

On Windows: enabling the VideoInput library:
The libvideoInput.a library file that comes with OpenCV was built using the old
SJLJ exception handling method. Hence, you can only link against it by using a
compiler that uses SJLJ. To link against it using a compiler that uses the
DWARF-2 exception handling method, replace the libvideoInput.a file in OpenCV
with this file. In addition, search in file src/highgui/CMakeLists.txt for the
following text: "videoInput strmiids". It should be at somewhere near line 199.
Then, insert " ole32 oleaut32 uuid" right after the text, i.e. "videoInput
strmiids ole32 oleaut32 uuid". The developers have forgotten to insert these
Windows libraries.

If you want to enable OpenMP when building OpenCV 2.0:
Before running cmake, edit file CMakeLists.txt, search for "-D\_GLIBCXX\_PARALLEL"
and remove it. Basically, when this option is set, experimental "parallel mode"
STL containers are used, which are incompatible with the standard "normal mode"
STL containers used by Boost.Python and other libraries. Of course, if you could
recompile every single library that is connected to OpenCV with option
"-D\_GLIBCXX\_PARALLEL" set, then it would be another matter.
8 Definitive Build RELEASE Installation of OpenCV 2.1.0 is under:
C:\OpenCV2.1.0-work\OpenCV\_MinGW\release
Add your content here.  Format your content with:
  * Text in **bold** or _italic_
  * Headings, paragraphs, and lists
  * Automatic links to other wiki pages