add_subdirectory(SearchFile)
add_subdirectory(BingRequest)
add_subdirectory(BlackJack)
add_subdirectory(Oauth1Client)
add_subdirectory(Oauth2Client)

if(WIN32)
  add_subdirectory(CasaLens)
endif()

set(SAMPLE_TARGETS SearchFile BingRequest blackjackclient blackjackserver oauth1client oauth2client)
if(WIN32)
  list(APPEND SAMPLE_TARGETS casalens)
endif()

add_custom_target(samples
  DEPENDS ${SAMPLE_TARGETS}
  )