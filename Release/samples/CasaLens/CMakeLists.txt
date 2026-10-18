if (NOT WINDOWS_STORE AND NOT WINDOWS_PHONE)
  add_executable(casalens
    casalens.cpp
    datafetcher.cpp
    stdafx.cpp
    )
  target_link_libraries(casalens cpprest)

  add_custom_command(TARGET casalens POST_BUILD
    COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/css" "$<TARGET_FILE_DIR:casalens>/css"
    COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/image" "$<TARGET_FILE_DIR:casalens>/image"
    COMMAND ${CMAKE_COMMAND} -E copy_directory "${CMAKE_CURRENT_SOURCE_DIR}/js" "$<TARGET_FILE_DIR:casalens>/js"
    COMMAND ${CMAKE_COMMAND} -E copy_if_different "${CMAKE_CURRENT_SOURCE_DIR}/AppCode.html" "$<TARGET_FILE_DIR:casalens>/AppCode.html")
endif()
