project(SerialChannel)

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

find_package(Boost REQUIRED container thread)

target_link_libraries(${PROJECT_NAME} 
	PRIVATE 
	Boost::boost 
	Boost::container 
	Boost::thread
)
	