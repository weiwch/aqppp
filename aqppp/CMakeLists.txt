cmake_minimum_required(VERSION 3.16.0 FATAL_ERROR)

set(PROJECT_NAME aqppp)

project(${PROJECT_NAME})
################################################################################
# Source groups
################################################################################
set(Header_Files
    "src/aqpp/aqpp.h"
    "src/aqpp/assign_budget_for_dimensions.h"
    "src/aqpp/bootstrap.h"
    "src/aqpp/common_content.h"
    "src/aqpp/configuration.h"
    "src/aqpp/hill_climbing.h"
    "src/aqpp/precompute.h"
    "src/aqpp/query_template.h"
    "src/aqpp/sampling.h"
    "src/aqpp/sql_interface.h"
    "src/aqpp/stratified_aqpp.h"
    "src/aqpp/stratified_sampling.h"
    "src/aqpp/tool.h"
    "src/exp/comprehensive_exp.h"
    "src/exp/exp_common.h"
)
source_group("Header Files" FILES ${Header_Files})

set(Source_Files
    "src/aqpp/aqpp.cpp"
    "src/aqpp/assign_budget_for_dimensions.cpp"
    "src/aqpp/bootstrap.cpp"
    "src/aqpp/common_content.cpp"
    "src/aqpp/configuration.cpp"
    "src/aqpp/hill_climbing.cpp"
    "src/aqpp/precompute.cpp"
    "src/aqpp/query_template.cpp"
    "src/aqpp/sampling.cpp"
    "src/aqpp/sql_interface.cpp"
    "src/aqpp/stratified_aqpp.cpp"
    "src/aqpp/stratified_sampling.cpp"
    "src/aqpp/tool.cpp"
    "src/exp/comprehensive_exp.cpp"
    "src/exp/exp_common.cpp"
    "src/main.cpp"
)
source_group("Source Files" FILES ${Source_Files})

set(ALL_FILES
    ${Header_Files}
    ${Source_Files}
)

add_executable(${PROJECT_NAME} ${ALL_FILES})

set_property(TARGET ${PROJECT_NAME} PROPERTY CXX_STANDARD 17)
target_link_libraries(${PROJECT_NAME} odbc pthread)