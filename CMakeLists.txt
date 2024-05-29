cmake_minimum_required(VERSION 3.10)

# 项目名称和版本
project(MyProject VERSION 1.0)

# 指定 C++ 标准
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

# 包含头文件目录
include_directories(include)

# 查找 spdlog 库
find_package(spdlog REQUIRED)

# 使用 file(GLOB ...) 匹配源文件
file(GLOB SOURCES "src/*.cpp")

# 添加可执行文件
add_executable(net_formwork ${SOURCES} main.cpp)


# 链接 spdlog 库
target_link_libraries(net_formwork PRIVATE spdlog::spdlog)
