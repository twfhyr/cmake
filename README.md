# cmake
solve the problem when cannot find boost libraries
when I use the cmake tool at the windows 7 platform,I meet the problem that cann't find the boost which i have already installed.
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

[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:551 ] _boost_TEST_VERSIONS = 1.59.0;1.59;1.58.0;1.58;1.57.0;1.57;1.56.0;1.56;1.55.0;1.55;1.54.0;1.54;1.53.0;1.53;1.52.0;1.52;1.51.0;1.51;1.50.0;1.50;1.49.0;1.49;1.48.0;1.48;1.47.0;1.47;1.46.1;1.46.0;1.46;1.45.0;1.45;1.44.0;1.44;1.43.0;1.43;1.42.0;1.42;1.41.0;1.41;1.40.0;1.40;1.39.0;1.39;1.38.0;1.38;1.37.0;1.37;1.36.1;1.36.0;1.36;1.35.1;1.35.0;1.35;1.34.1;1.34.0;1.34;1.33.1;1.33.0;1.33
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:553 ] Boost_USE_MULTITHREADED = TRUE
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:555 ] Boost_USE_STATIC_LIBS = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:557 ] Boost_USE_STATIC_RUNTIME = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:559 ] Boost_ADDITIONAL_VERSIONS = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:561 ] Boost_NO_SYSTEM_PATHS = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:613 ] Declared as CMake or Environmental Variables:
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:615 ]   BOOST_ROOT = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:617 ]   BOOST_INCLUDEDIR = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:619 ]   BOOST_LIBRARYDIR = 
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:621 ] _boost_TEST_VERSIONS = 1.59.0;1.59;1.58.0;1.58;1.57.0;1.57;1.56.0;1.56;1.55.0;1.55;1.54.0;1.54;1.53.0;1.53;1.52.0;1.52;1.51.0;1.51;1.50.0;1.50;1.49.0;1.49;1.48.0;1.48;1.47.0;1.47;1.46.1;1.46.0;1.46;1.45.0;1.45;1.44.0;1.44;1.43.0;1.43;1.42.0;1.42;1.41.0;1.41;1.40.0;1.40;1.39.0;1.39;1.38.0;1.38;1.37.0;1.37;1.36.1;1.36.0;1.36;1.35.1;1.35.0;1.35;1.34.1;1.34.0;1.34;1.33.1;1.33.0;1.33
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:690 ] Include debugging info:
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:692 ]   _boost_INCLUDE_SEARCH_DIRS = D:/boost_1_59_0/include;D:/boost_1_59_0;PATHS;C:/boost/include;C:/boost;/sw/local/include
[ C:/Program Files (x86)/CMake/share/cmake-3.4/Modules/FindBoost.cmake:694 ]   _boost_PATH_SUFFIXES = boost-1_59_0;boost_1_59_0;boost/boost-1_59_0;boost/boost_1_59_0;boost-1_59;boost_1_59;boost/boost-1_59;boost/boost_1_59;boost-1_58_0;boost_1_58_0;boost/boost-1_58_0;boost/boost_1_58_0;boost-1_58;boost_1_58;boost/boost-1_58;boost/boost_1_58;boost-1_57_0;boost_1_57_0;boost/boost-1_57_0;boost/boost_1_57_0;boost-1_57;boost_1_57;boost/boost-1_57;boost/boost_1_57;boost-1_56_0;boost_1_56_0;boost/boost-1_56_0;boost/boost_1_56_0;boost-1_56;boost_1_56;boost/boost-1_56;boost/boost_1_56;boost-1_55_0;boost_1_55_0;boost/boost-1_55_0;boost/boost_1_55_0;boost-1_55;boost_1_55;boost/boost-1_55;boost/boost_1_55;boost-1_54_0;boost_1_54_0;boost/boost-1_54_0;boost/boost_1_54_0;boost-1_54;boost_1_54;boost/boost-1_54;boost/boost_1_54;boost-1_53_0;boost_1_53_0;boost/boost-1_53_0;boost/boost_1_53_0;boost-1_53;boost_1_53;boost/boost-1_53;boost/boost_1_53;boost-1_52_0;boost_1_52_0;boost/boost-1_52_0;boost/boost_1_52_0;boost-1_52;boost_1_52;boost/boost-1_52;boost/boost_1_52;boost-1_51_0;boost_1_51_0;boost/boost-1_51_0;boost/boost_1_51_0;boost-1_51;boost_1_51;boost/boost-1_51;boost/boost_1_51;boost-1_50_0;boost_1_50_0;boost/boost-1_50_0;boost/boost_1_50_0;boost-1_50;boost_1_50;boost/boost-1_50;boost/boost_1_50;boost-1_49_0;boost_1_49_0;boost/boost-1_49_0;boost/boost_1_49_0;boost-1_49;boost_1_49;boost/boost-1_49;boost/boost_1_49;boost-1_48_0;boost_1_48_0;boost/boost-1_48_0;boost/boost_1_48_0;boost-1_48;boost_1_48;boost/boost-1_48;boost/boost_1_48;boost-1_47_0;boost_1_47_0;boost/boost-1_47_0;boost/boost_1_47_0;boost-1_47;boost_1_47;boost/boost-1_47;boost/boost_1_47;boost-1_46_1;boost_1_46_1;boost/boost-1_46_1;boost/boost_1_46_1;boost-1_46_0;boost_1_46_0;boost/boost-1_46_0;boost/boost_1_46_0;boost-1_46;boost_1_46;boost/boost-1_46;boost/boost_1_46;boost-1_45_0;boost_1_45_0;boost/boost-1_45_0;boost/boost_1_45_0;boost-1_45;boost_1_45;boost/boost-1_45;boost/boost_1_45;boost-1_44_0;boost_1_44_0;boost/boost-1_44_0;boost/boost_1_44_0;boost-1_44;boost_1_44;boost/boost-1_44;boost/boost_1_44;boost-1_43_0;boost_1_43_0;boost/boost-1_43_0;boost/boost_1_43_0;boost-1_43;boost_1_43;boost/boost-1_43;boost/boost_1_43;boost-1_42_0;boost_1_42_0;boost/boost-1_42_0;boost/boost_1_42_0;boost-1_42;boost_1_42;boost/boost-1_42;boost/boost_1_42;boost-1_41_0;boost_1_41_0;boost/boost-1_41_0;boost/boost_1_41_0;boost-1_41;boost_1_41;boost/boost-1_41;boost/boost_1_41;boost-1_40_0;boost_1_40_0;boost/boost-1_40_0;boost/boost_1_40_0;boost-1_40;boost_1_40;boost/boost-1_40;boost/boost_1_40;boost-1_39_0;boost_1_39_0;boost/boost-1_39_0;boost/boost_1_39_0;boost-1_39;boost_1_39;boost/boost-1_39;boost/boost_1_39;boost-1_38_0;boost_1_38_0;boost/boost-1_38_0;boost/boost_1_38_0;boost-1_38;boost_1_38;boost/boost-1_38;boost/boost_1_38;boost-1_37_0;boost_1_37_0;boost/boost-1_37_0;boost/boost_1_37_0;boost-1_37;boost_1_37;boost/boost-1_37;boost/boost_1_37;boost-1_36_1;boost_1_36_1;boost/boost-1_36_1;boost/boost_1_36_1;boost-1_36_0;boost_1_36_0;boost/boost-1_36_0;boost/boost_1_36_0;boost-1_36;boost_1_36;boost/boost-1_36;boost/boost_1_36;boost-1_35_1;boost_1_35_1;boost/boost-1_35_1;boost/boost_1_35_1;boost-1_35_0;boost_1_35_0;boost/boost-1_35_0;boost/boost_1_35_0;boost-1_35;boost_1_35;boost/boost-1_35;boost/boost_1_35;boost-1_34_1;boost_1_34_1;boost/boost-1_34_1;boost/boost_1_34_1;boost-1_34_0;boost_1_34_0;boost/boost-1_34_0;boost/boost_1_34_0;boost-1_34;boost_1_34;boost/boost-1_34;boost/boost_1_34;boost-1_33_1;boost_1_33_1;boost/boost-1_33_1;boost/boost_1_33_1;boost-1_33_0;boost_1_33_0;boost/boost-1_33_0;boost/boost_1_33_0;boost-1_33;boost_1_33;boost/boost-1_33;boost/boost_1_33
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
