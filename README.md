# How to link a library to an executable in CMake

1. Create a library using `add_library` command.
2. Add library interface headers directory using `target_include_directories(${LIBRARY_NAME} INTERFACE ${LIBRARY_INTERFACE_HEADERS_DIR})`.
3. Link an executable to the library using `target_link_libraries(${EXECUTABLE_NAME} ${LIBRARY_NAME})`.
4. Library's interface headers directory is automatically added to executable's include directories, now you can include library's headers by simply using `#include <library.h>`.
5. Now if you move library somewhere else, change where interface headers are, etc, - it will be automatically picked up by CMake.
