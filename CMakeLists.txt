project(SerialChannel)

include(CMakePrintHelpers)

add_library(${PROJECT_NAME}
	STATIC 
	src/SerialChannel_win.cpp
	src/winapi_error.hpp
	SerialChannel.hpp
)

target_include_directories(${PROJECT_NAME}
	PUBLIC
	${CMAKE_CURRENT_SOURCE_DIR}
)
cmake_print_variables(CMAKE_MODULE_PATH)

find_package(Boost 1.78.0 REQUIRED COMPONENTS container thread)

# cmake_print_variables(Boost_INCLUDE_DIRS Boost_LIBRARY_DIRS Boost_LIBRARIES Boost_VERSION)
# cmake_print_properties(TARGETS Boost::container PROPERTIES LOCATION INCLUDE_DIRECTORIES)
# cmake_print_variables(Boost_container_FOUND)
# cmake_print_variables(Boost_INCLUDE_DIR)
target_include_directories(${PROJECT_NAME} PRIVATE D:/Projects/locsim/Win32/include/boost-1_78 )  # Necessary to specify, where the include-files are
target_link_libraries(${PROJECT_NAME} 
	PRIVATE 
	Boost::boost 
	Boost::container 
	Boost::thread
)	
# cmake_print_properties(TARGETS SerialChannel PROPERTIES INCLUDE_DIRECTORIES)