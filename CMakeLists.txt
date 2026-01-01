# The C++ interface requires the C library to have been built with the netCDF-4 API
find_package(netCDF 4 REQUIRED)

file(GLOB CXX_SOURCES nc*.cpp)

add_library(netcdf-cxx4 STATIC ${CXX_SOURCES})

target_include_directories(netcdf-cxx4
        PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
)

target_link_libraries(netcdf-cxx4
        PUBLIC netCDF::netcdf
)
