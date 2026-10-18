if (NOT WINDOWS_STORE AND NOT WINDOWS_PHONE)
  add_executable(casalens
    casalens.cpp
    datafetcher.cpp
    stdafx.cpp
    )
  target_link_libraries(casalens cpprest)
endif()
