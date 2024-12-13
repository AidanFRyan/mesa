add_library(auto_diff SHARED 
    private/auto_diff_real_1var_order1_module.f90
    private/auto_diff_real_2var_order1_module.f90
    private/auto_diff_real_2var_order2_module.f90
    private/auto_diff_real_2var_order3_module.f90
    private/auto_diff_real_4var_order1_module.f90
    private/auto_diff_real_star_order1_module.f90
    private/auto_diff_real_tdc_module.f90
    private/support_functions.f90
    public/auto_diff.f90
)

target_link_libraries(auto_diff PRIVATE math const utils)

target_include_directories(auto_diff
PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}/../const
    ${CMAKE_CURRENT_BINARY_DIR}/../utils
    ${CMAKE_CURRENT_BINARY_DIR}/../math
)