cmake_minimum_required(VERSION 2.6.4)
project(CFE_SAMPLE_APP C)

include_directories(fsw/mission_inc)
include_directories(fsw/platform_inc)

# Include the public API from sample_lib to demonstrate how
# to call library-provided functions
include_directories(${sample_lib_MISSION_DIR}/fsw/public_inc)

aux_source_directory(fsw/src APP_SRC_FILES)

# Create the app module
add_cfe_app(sample_app ${APP_SRC_FILES})

# Add table
add_cfe_tables(sampleTable fsw/src/sample_table.c)
