add_library(math SHARED 
    public/math_lib_crmath.f90
    private/math_io.f90
    private/math_pown.f90
    public/math_def.f90
)

target_link_libraries(math
PRIVATE
    utils
    const
    crmath
    crlibm
)

target_link_directories(math
PRIVATE
    /sql_nvme/phd/crmath/build
    /sql_nvme/phd/crlibm/build
)

target_include_directories(math
PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}/../const
    ${CMAKE_CURRENT_BINARY_DIR}/../utils
    /sql_nvme/phd/crmath/build
    /sql_nvme/phd/crlibm/build
)