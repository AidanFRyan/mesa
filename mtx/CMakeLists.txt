add_subdirectory(lapack_src)
add_subdirectory(lapack_quad)
add_subdirectory(blas_src)

add_library(mtx SHARED
    public/mtx_def.f
    private/my_lapack95_dble.f90
    private/my_lapack95_quad.f90
    private/mtx_support.f90
    private/DGBSVX_wrapper.f90
    private/pre_conditioners.f90
    private/bcyclic.f90
    public/mtx_lib.f90
)

target_link_libraries(mtx PRIVATE
mesalapack_quad
mesalapack
mesablas
const
utils
)

target_include_directories(mtx
PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}/../const
    ${CMAKE_CURRENT_SOURCE_DIR}/../utils
    ${CMAKE_CURRENT_BINARY_DIR}/../utils
)