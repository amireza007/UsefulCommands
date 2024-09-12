- If you encountered an `unknown target "install"` while running the build and make files with `ninja`, add n `install` commnand in your `CmakeLists.txt`. E.g.:
     ```
     install(TARGETS ${PROJECT_NAME} LIBRARY DESTINATION ${CMAKE_CURRENT_BINARY_DIR})
     ```