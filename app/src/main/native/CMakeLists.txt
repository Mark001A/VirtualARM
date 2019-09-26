cmake_minimum_required(VERSION 3.4.1)
project(VirtualARM)

set(CMAKE_CXX11_EXTENSION_COMPILE_OPTION "-std=c++17")
ENABLE_LANGUAGE(ASM)

include_directories(.)

include_directories(externals/ext-boost)

add_library(VirtualARM SHARED
    virtual_arm.cc
    base/marcos.cc
    instruction/instruction.cc
    frontend/arm64/instruction_fields.cc
    frontend/arm64/instruction_aarch64.cc
    frontend/arm64/instruction_table.cc
    frontend/arm64/instruction_decode.cc
    frontend/arm64/decodes/decode_system_branch.cc
    frontend/arm64/cpu_arm64.cc
)


target_link_libraries(VirtualARM android log)