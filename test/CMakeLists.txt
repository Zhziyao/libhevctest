
SET (CMAKE_C_FLAGS " -DPROFILE_ENABLE -DARM -fPIC -DMD5_DISABLE ")

SET (libhevc_top_srcdir ..)

SET (hevctest_src_files
	decoder/main.c
)

INCLUDE_DIRECTORIES(
	${libhevc_top_srcdir}/decoder
	${libhevc_top_srcdir}/common
)

LINK_DIRECTORIES (
	${libhevc_top_srcdir}/lib
)

ADD_DEFINITIONS (${CMAKE_C_FLAGS})

ADD_EXECUTABLE (hevcdecode ${hevctest_src_files})

TARGET_LINK_LIBRARIES (hevcdecode hevcdev pthread)

SET (EXECUTABLE_OUTPUT_PATH ${libhevc_top_srcdir}/bin)
