add_library(
    utils
    SHARED 
    public/utils_def.f90
    private/utils_dict.f90
    private/utils_idict.f90
    public/utils_lib.f90
    private/utils_nan.f90
    private/utils_nan_sp.f90
    private/utils_nan_dp.f90
    private/utils_nan_qp.f90
    private/utils_c_system.c
    private/utils_system.f90
    private/utils_openmp.f90
)

target_include_directories(utils PRIVATE ${CMAKE_CURRENT_BINARY_DIR}/../const)
target_link_libraries(utils PRIVATE const)