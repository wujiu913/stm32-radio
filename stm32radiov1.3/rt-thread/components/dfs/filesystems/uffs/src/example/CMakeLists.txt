INCLUDE_DIRECTORIES(${uffs_SOURCE_DIR}/src/inc)
INCLUDE_DIRECTORIES(${uffs_SOURCE_DIR}/src/emu)

LINK_DIRECTORIES(${uffs_BINARY_DIR}/src/emu)
LINK_DIRECTORIES(${uffs_BINARY_DIR}/src/uffs)

SET(static_mem_SRCS static-mem-allocate.c)
SET(flash_if_SRCS flash-interface-example.c)
ADD_EXECUTABLE(static-mem-example ${static_mem_SRCS})
ADD_EXECUTABLE(flash-if-example ${flash_if_SRCS})
TARGET_LINK_LIBRARIES(static-mem-example emu uffs emu)
TARGET_LINK_LIBRARIES(flash-if-example emu uffs emu)
