project(functionaltests)


# ======================================

add_executable(basic_tests BasicTests.cpp)
target_link_libraries(basic_tests
    restc-cpp ${DEFAULT_LIBRARIES})

add_test(BASIC_TESTS basic_tests)


# ======================================

add_executable(readme_tests ReadmeTests.cpp)
target_link_libraries(readme_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
)

add_test(README_TESTS readme_tests)

# ======================================

add_executable(auth_tests AuthTest.cpp)
target_link_libraries(auth_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(auth_tests externalLest)
add_test(AUTH_TESTS auth_tests)


# ======================================

add_executable(upload_tests UploadTests.cpp)
target_link_libraries(upload_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(upload_tests externalLest)
add_test(UPLOAD_TESTS upload_tests)


# # ======================================

add_executable(inserter_serializer_tests InsertSerializerTest.cpp)
target_link_libraries(inserter_serializer_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(inserter_serializer_tests externalLest)
add_test(INSERTER_SERIALIZER_TESTS inserter_serializer_tests)


# # ======================================

add_executable(ccache_tests ConnectionCacheTests.cpp)
target_link_libraries(ccache_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(ccache_tests externalLest)
add_test(CCACHE_FUNCTIONAL_TESTS ccache_tests)

# # ======================================

add_executable(redirect_tests RedirectTests.cpp)
target_link_libraries(redirect_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(redirect_tests externalLest)
add_test(REDIRECT_FUNCTIONAL_TESTS redirect_tests)


# # ======================================

add_executable(crud_tests CRUD_test.cpp)
target_link_libraries(crud_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(crud_tests externalLest)
add_test(CRUD_FUNCTIONAL_TESTS crud_tests)


# ======================================

add_executable(many_connections_tests ManyConnectionsTest.cpp)
target_link_libraries(many_connections_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(many_connections_tests externalLest)
add_test(MANY_CONNECTIONS_FUNCTIONAL_TESTS many_connections_tests)


# ======================================

if (RESTC_CPP_WITH_TLS)
    add_executable(https_tests HttpsTest.cpp)
    target_link_libraries(https_tests
        restc-cpp
        ${DEFAULT_LIBRARIES}
        ${UNITTEST_LIB}
    )
    add_dependencies(https_tests externalLest)
    add_test(HTTPS_FUNCTIONAL_TESTS https_tests)
endif()


# ======================================

add_executable(own_ioservice_tests OwnIoserviceTests.cpp)
target_link_libraries(own_ioservice_tests
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(own_ioservice_tests externalLest)
add_test(OWN_IOSERVICE_TESTS own_ioservice_tests)



# ======================================

add_executable(connection_pool_instances_test ConnectionPoolInstancesTest.cpp)
target_link_libraries(connection_pool_instances_test
    restc-cpp
    ${DEFAULT_LIBRARIES}
    ${UNITTEST_LIB}
)
add_dependencies(connection_pool_instances_test externalLest)
add_test(CONNECTION_POOL_INSTANCES_TEST connection_pool_instances_test)


