cmake_minimum_required(VERSION 3.2 FATAL_ERROR)

if(NOT CMAKE_BUILD_TYPE)
	set(CMAKE_BUILD_TYPE release)
endif()

set (CMAKE_CXX_FLAGS, "-02")
set (CMAKE_CXX_FLAGS_DEBUG, "-02")
set (CMAKE_CXX_FLAGS_RELEASE, "-02")

project(Scacchi_cpp)

include_directories (Scacchi)
include_directories (ReplayScacchi)

add_library (	Alfiere
	Scacchi/Alfiere.h
	Scacchi/Alfiere.cpp	
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp

)

add_library (	Casella
	Scacchi/Casella.h
	Scacchi/Casella.cpp


)

add_library (	Cavallo
	Scacchi/Cavallo.h
	Scacchi/Cavallo.cpp	
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp

)

add_library (	ChessBoard
	Scacchi/ChessBoard.h
	Scacchi/ChessBoard.cpp	
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp
	
	Scacchi/Cavallo.h
	Scacchi/Cavallo.cpp
	Scacchi/Alfiere.h
	Scacchi/Alfiere.cpp	

)

add_library (	Exception
	Scacchi/Exception.h
	Scacchi/Exception.cpp
)

add_library (Mossa
	Scacchi/Mossa.h
	Scacchi/Mossa.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp
)

add_library (	Pedone
	Scacchi/Pedone.h
	Scacchi/Pedone.cpp
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp	

)

add_library (	Pezzo
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp	

)

add_library (	Player
	Scacchi/Player.h
	Scacchi/Player.cpp
	
)

add_library (	Re
	Scacchi/Re.h
	Scacchi/Re.cpp
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp	

)

add_library (	Regina
	Scacchi/Regina.h
	Scacchi/Regina.cpp	
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp

)

add_library (	Torre
	Scacchi/Torre.h
	Scacchi/Torre.cpp	
	Scacchi/Pezzo.h
	Scacchi/Pezzo.cpp
	Scacchi/Casella.h
	Scacchi/Casella.cpp

)



add_executable(scacchiera
	Scacchi/scacchiera.cpp 
)

target_link_libraries(scacchiera
Alfiere
Casella
Cavallo
ChessBoard
Exception
Mossa
Pedone
Pezzo
Player
Re
Regina
Torre
)


add_library (	exception
	ReplayScacchi/Exception.h
	ReplayScacchi/Exception.cpp	
)

add_library (	Replay
	ReplayScacchi/Replay.h
	ReplayScacchi/Replay.cpp	
)


add_executable(replay
	ReplayScacchi/Scacchi_Replay.cpp 
)


target_link_libraries(replay
exception
Replay
)





