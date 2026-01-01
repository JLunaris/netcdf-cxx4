# NetCDF-4 C++ Library

本项目是 [NetCDF-4 C++ library](https://github.com/Unidata/netcdf-cxx4)（版本：4.3.1）的精简版，源码内容做了一些微小调整（主要是为了使其适配现代 C++），并为其创建了`CMakeLists.txt`，将该库编译为**静态库**，方便在项目中直接使用。

## 使用方法

将本项目（`netcdf-cxx4`目录）拷贝到你的项目目录中。在你的`CMakeLists.txt`中添加如下内容（假设要使用该库的目标名称为`tar`）：

```cmake
add_subdirectory(netcdf-cxx4)

target_link_libraries(tar PUBLIC netcdf-cxx4)
```

这样，目标`tar`就可以直接使用 NetCDF C++ 库提供的头文件和功能。

## 依赖

- [NetCDF-4 C libraries](https://downloads.unidata.ucar.edu/netcdf/)

## 参考

- 官方文档：[NetCDF-C++ Documentation](https://docs.unidata.ucar.edu/netcdf-cxx/current/)
