# The C++ interface requires the C library to have been built with the netCDF-4 API
find_package(netCDF 4.6.0 REQUIRED)

file(GLOB CXX_SOURCES nc*.cpp)

add_library(netcdf-cxx4 STATIC ${CXX_SOURCES})

target_link_libraries(netcdf-cxx4
        PRIVATE netCDF::netcdf
)

get_target_property(NC_INC_DIRS netCDF::netcdf INTERFACE_INCLUDE_DIRECTORIES)

target_include_directories(netcdf-cxx4
        PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}
        PUBLIC ${NC_INC_DIRS}
)
