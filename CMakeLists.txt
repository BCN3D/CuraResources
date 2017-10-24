project(CuraResources NONE)

cmake_minimum_required(VERSION 2.8.12)

include(GNUInstallDirs)

if(CMAKE_BUILD_TYPE MATCHES Release)
	set(INSTALL_PATH share/cura)
else()
	set(INSTALL_PATH "")
endif()

if(IS_ABSOLUTE ${INSTALL_PATH})
	set(INSTALL_PATH ${INSTALL_PATH})
else()
    set(INSTALL_PATH ${CMAKE_INSTALL_PREFIX}/${INSTALL_PATH})
endif()

install(DIRECTORY definitions DESTINATION ${INSTALL_PATH}/resources)
install(DIRECTORY extruders DESTINATION ${INSTALL_PATH}/resources)
install(DIRECTORY materials DESTINATION ${INSTALL_PATH}/resources)
install(DIRECTORY meshes DESTINATION ${INSTALL_PATH}/resources)
install(DIRECTORY quality DESTINATION ${INSTALL_PATH}/resources)
install(DIRECTORY variants DESTINATION ${INSTALL_PATH}/resources)