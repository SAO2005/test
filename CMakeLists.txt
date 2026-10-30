cmake_minimum_required(VERSION 3.10)
project(meostar)

# Thêm thư mục Dobby vào dự án
add_subdirectory(Dobby)

# Tìm thư viện log của Android
find_library(log-lib log)

# Tạo thư viện meostar
add_library(meostar SHARED libmeostar.cpp)

# Liên kết với Dobby và log
target_link_libraries(meostar dobby ${log-lib})