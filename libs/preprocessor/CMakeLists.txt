cmake_minimum_required(VERSION 3.5)
project(boost_preprocessor)

find_package(BCM)
include(BCMDeploy)
include(BCMSetupVersion)


bcm_setup_version(VERSION 1.64.0)

add_library(boost_preprocessor INTERFACE
)
set_property(TARGET boost_preprocessor PROPERTY EXPORT_NAME preprocessor)





bcm_deploy(TARGETS boost_preprocessor INCLUDE include NAMESPACE boost::)

if(BOOST_CMAKE_BUILD_TESTS)
    add_subdirectory(test)
endif()
