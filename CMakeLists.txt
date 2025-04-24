cmake_minimum_required(VERSION 3.20)

project(BotanTest VERSION 1.0.0 LANGUAGES CXX)

add_executable(${PROJECT_NAME} main.cc)

find_package(botan CONFIG REQUIRED)

if(${BUILD_SHARED_LIBS})
    target_link_libraries(${PROJECT_NAME} PRIVATE Botan::Botan)
else()
    target_link_libraries(${PROJECT_NAME} PRIVATE Botan::Botan-static)
endif()

target_compile_features(${PROJECT_NAME} PRIVATE cxx_std_20)