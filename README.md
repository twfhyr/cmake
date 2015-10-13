# cmake
solve the problem when cannot find boost libraries<title>
<p>
when I use the cmake tool at the windows 7 platform,I meet the problem that cann't find the boost which i have already installed.
</p>
First I modified the environment,set the name"BOOST_ROOT",the value is the location of my boost version.But it didn't work.
Then I added the line shown as followed in the project file CMakeList.txt.
set(BOOST_ROOT D:/boost_1_59_0)
set(BOOST_LIBRARYDIR ${BOOST_ROOT}/stage/lib)"
This time I met new trouble
********************trouble*****************************
Unable to find the requested Boost libraries.

  Boost version: 1.59.0

  Boost include path: D:/boost_1_59_0

  Could not find the following Boost libraries:

          boost_system
          boost_program_options
          boost_filesystem
          boost_thread

  No Boost libraries were found.  You may need to set BOOST_LIBRARYDIR to the
  directory containing Boost libraries or BOOST_ROOT to the location of
  Boost.
Call Stack (most recent call first):
  CMakeLists.txt:99 (find_package)


Boost INCLUDE DIR IS: D:/boost_1_59_0
Boost LIBRARY DIR IS: 
****************************************************************
then I added 
set (BOOST_DEBUG ON)
at the CMakeList.txt to debug the cmake

The result was

*****************************************************************************************************************************

[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:714 ] location of version.hpp: D:/boost_1_59_0/boost/version.hpp
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:738 ] version.hpp reveals boost 1.59.0
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:824 ] guessed _boost_COMPILER = -vc120
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:834 ] _boost_MULTITHREADED = -mt
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:877 ] _boost_RELEASE_ABI_TAG = -
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:879 ] _boost_DEBUG_ABI_TAG = -gd
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:933 ] _boost_LIBRARY_SEARCH_DIRS_RELEASE = D:/boost_1_59_0/lib;D:/boost_1_59_0/stage/lib;D:/boost_1_59_0/lib;D:/boost_1_59_0/../lib;D:/boost_1_59_0/stage/lib;PATHS;C:/boost/lib;C:/boost;/sw/local/lib_boost_LIBRARY_SEARCH_DIRS_DEBUG   = D:/boost_1_59_0/lib;D:/boost_1_59_0/stage/lib;D:/boost_1_59_0/lib;D:/boost_1_59_0/../lib;D:/boost_1_59_0/stage/lib;PATHS;C:/boost/lib;C:/boost;/sw/local/lib
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1045 ] Searching for SYSTEM_LIBRARY_RELEASE: boost_system-vc120-mt-1_59;boost_system-vc120-mt;boost_system-mt-1_59;boost_system-mt;boost_system
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1087 ] Searching for SYSTEM_LIBRARY_DEBUG: boost_system-vc120-mt-gd-1_59;boost_system-vc120-mt-gd;boost_system-mt-gd-1_59;boost_system-mt-gd;boost_system-mt;boost_system
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1045 ] Searching for PROGRAM_OPTIONS_LIBRARY_RELEASE: boost_program_options-vc120-mt-1_59;boost_program_options-vc120-mt;boost_program_options-mt-1_59;boost_program_options-mt;boost_program_options
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1087 ] Searching for PROGRAM_OPTIONS_LIBRARY_DEBUG: boost_program_options-vc120-mt-gd-1_59;boost_program_options-vc120-mt-gd;boost_program_options-mt-gd-1_59;boost_program_options-mt-gd;boost_program_options-mt;boost_program_options
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1045 ] Searching for FILESYSTEM_LIBRARY_RELEASE: boost_filesystem-vc120-mt-1_59;boost_filesystem-vc120-mt;boost_filesystem-mt-1_59;boost_filesystem-mt;boost_filesystem
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1087 ] Searching for FILESYSTEM_LIBRARY_DEBUG: boost_filesystem-vc120-mt-gd-1_59;boost_filesystem-vc120-mt-gd;boost_filesystem-mt-gd-1_59;boost_filesystem-mt-gd;boost_filesystem-mt;boost_filesystem
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1045 ] Searching for THREAD_LIBRARY_RELEASE: boost_thread-vc120-mt-1_59;boost_thread-vc120-mt;boost_thread-mt-1_59;boost_thread-mt;boost_thread
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1087 ] Searching for THREAD_LIBRARY_DEBUG: boost_thread-vc120-mt-gd-1_59;boost_thread-vc120-mt-gd;boost_thread-mt-gd-1_59;boost_thread-mt-gd;boost_thread-mt;boost_thread
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1153 ] Boost_FOUND = 1
CMake Error at C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:1247 (message):
  Unable to find the requested Boost libraries.

  Boost version: 1.59.0

  Boost include path: D:/boost_1_59_0

  Could not find the following Boost libraries:

          boost_system
          boost_program_options
          boost_filesystem
          boost_thread

  No Boost libraries were found.  You may need to set BOOST_LIBRARYDIR to the
  directory containing Boost libraries or BOOST_ROOT to the location of
  Boost.
Call Stack (most recent call first):
  CMakeLists.txt:98 (find_package)
*****************************************************************************************************************************
I checked the value in my D:/boost_1_59_0/stage/lib against the debug result and found that the name was not matched.For example,it was serching for 
"boost_system-vc120-mt-gd-1_59",
but in my folder it showed as 
"libboost_system-vc120-mt-gd-1_59".
Then I check the findboost.cmake, and modify the  783 line 
set(Boost_LIB_PREFIX )
as set(Boost_LIB_PREFIX "lib"). Then it worked
I hope this experience can help someone
