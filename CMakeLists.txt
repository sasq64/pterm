cmake_minimum_required(VERSION 3.12)
project(pterm)

find_package(wxWidgets REQUIRED)
find_package(SDL2 REQUIRED)

SET(SOURCES dtnetsubs.c pterm_sdl.c FrameCanvas.cpp MTFile.cpp PtermApp.cpp 
        PtermConnDialog.cpp PtermConnFailDialog.cpp PtermConnection.cpp 
        PtermProfile.cpp PtermPrefDialog.cpp PtermPrintout.cpp PtermTrace.cpp Z80.cpp)
set(DD60_SOURCES dd60.c knob.c iir.c)

include(${wxWidgets_USE_FILE})

add_executable(pterm ${SOURCES})
target_include_directories(pterm PUBLIC /opt/homebrew/include)
target_link_libraries(pterm PUBLIC ${wxWidgets_LIBRARIES} SDL2::SDL2 sndfile)

