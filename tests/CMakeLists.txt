# libttip tests
ADD_EXECUTABLE(createdestroy_test createdestroy.c)
TARGET_LINK_LIBRARIES(createdestroy_test ${TTIP_LIBRARIES})
ADD_TEST(createdestroy createdestroy_test)

ADD_EXECUTABLE(pngio_test pngio.c)
TARGET_LINK_LIBRARIES(pngio_test ${TTIP_LIBRARIES})
ADD_TEST(pngio pngio_test)

ADD_EXECUTABLE(errors_test errors.c)
TARGET_LINK_LIBRARIES(errors_test ${TTIP_LIBRARIES})
ADD_TEST(errors errors_test)

# tiletool internals tests
INCLUDE_DIRECTORIES(../utils/tiletool)

ADD_EXECUTABLE(parsing_test parsing.c ../utils/tiletool/parsing.c)
ADD_TEST(parsing parsing_test)

ADD_EXECUTABLE(bounds_test bounds.c ../utils/tiletool/bounds.c ../utils/tiletool/parsing.c)
ADD_TEST(bounds bounds_test)

ADD_EXECUTABLE(paths_test paths.c ../utils/tiletool/paths.c)
ADD_TEST(paths paths_test)

ADD_EXECUTABLE(process_test process.c ../utils/tiletool/process.c)
ADD_TEST(process process_test)
