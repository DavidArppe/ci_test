cmake_minimum_required(VERSION 3.7)
project(CI)

enable_testing()

add_library (MathLib
	src/Vector.h
	src/Vector.cpp
	)

add_executable(MathTest
	src/main.cpp
	)
	
target_link_libraries(MathTest MathLib)

install(TARGETS MathLib MathTest
	RUNTIME DESTINATION "bin/"
	LIBRARY DESTINATION "lib/"
	ARCHIVE DESTINATION "lib/static/"
	)

add_test(MathTestRun MathTest)