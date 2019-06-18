# -----------------------------------------------------------------------------------------------------
# Copyright (c) 2006-2019, Knut Reinert & Freie Universität Berlin
# Copyright (c) 2016-2019, Knut Reinert & MPI für molekulare Genetik
# This file may be used, modified and/or redistributed under the terms of the 3-clause BSD-License
# shipped with this file and also available at: https://github.com/eseiler/minimizer_thresholds/blob/master/LICENSE
# -----------------------------------------------------------------------------------------------------

cmake_minimum_required (VERSION 3.4...3.12)

project(minimizer_thresholds CXX)

if(NOT SEQAN3_DIR)
    set(SEQAN3_DIR ${CMAKE_SOURCE_DIR}/submodules/seqan3)
endif()

find_package (SeqAn3 REQUIRED
              HINTS ${SEQAN3_DIR}/build_system)

add_executable (query ${CMAKE_SOURCE_DIR}/src/query.cpp)
include_directories (${CMAKE_SOURCE_DIR}/src)
target_link_libraries (query seqan3::seqan3)

add_executable (random_data ${CMAKE_SOURCE_DIR}/src/random_data.cpp)
include_directories (${CMAKE_SOURCE_DIR}/src)
target_link_libraries (random_data seqan3::seqan3)
