
PROJECT (libhevcdev)

SET (CMAKE_C_FLAGS " -D_LIB -DMULTICORE -fPIC -O3 -DANDROID -DX86 -DDISABLE_AVX2 -msse4.2 -mno-avx -DDEFAULT_ARCH=D_ARCH_X86_SSE42 ") 

SET (libhevc_top_srcdir ..)

SET (hevcdev_src_files
	../common/ihevc_quant_tables.c
	../common/ihevc_inter_pred_filters.c
	../common/ihevc_weighted_pred.c
	../common/ihevc_padding.c
	../common/ihevc_deblk_edge_filter.c
	../common/ihevc_deblk_tables.c
	../common/ihevc_cabac_tables.c
	../common/ihevc_common_tables.c
	../common/ihevc_intra_pred_filters.c
	../common/ihevc_chroma_intra_pred_filters.c
	../common/ihevc_mem_fns.c
	../common/ihevc_sao.c
	../common/ihevc_trans_tables.c
	../common/ihevc_recon.c
	../common/ihevc_itrans.c
	../common/ihevc_itrans_recon.c
	../common/ihevc_iquant_recon.c
	../common/ihevc_iquant_itrans_recon.c
	../common/ihevc_itrans_recon_32x32.c
	../common/ihevc_itrans_recon_16x16.c
	../common/ihevc_itrans_recon_8x8.c
	../common/ihevc_chroma_itrans_recon.c
	../common/ihevc_chroma_iquant_recon.c
	../common/ihevc_chroma_iquant_itrans_recon.c
	../common/ihevc_chroma_recon.c
	../common/ihevc_chroma_itrans_recon_16x16.c
	../common/ihevc_chroma_itrans_recon_8x8.c
	../common/ihevc_buf_mgr.c
	../common/ihevc_disp_mgr.c
	../common/ihevc_dpb_mgr.c
	../common/ithread.c
	ihevcd_version.c
	ihevcd_api.c
	ihevcd_decode.c
	ihevcd_nal.c
	ihevcd_bitstream.c
	ihevcd_parse_headers.c
	ihevcd_parse_slice_header.c
	ihevcd_parse_slice.c
	ihevcd_parse_residual.c
	ihevcd_cabac.c
	ihevcd_intra_pred_mode_prediction.c
	ihevcd_process_slice.c
	ihevcd_utils.c
	ihevcd_job_queue.c
	ihevcd_ref_list.c
	ihevcd_get_mv.c
	ihevcd_mv_pred.c
	ihevcd_mv_merge.c
	ihevcd_iquant_itrans_recon_ctb.c
	ihevcd_itrans_recon_dc.c
	ihevcd_common_tables.c
	ihevcd_boundary_strength.c
	ihevcd_deblk.c
	ihevcd_inter_pred.c
	ihevcd_sao.c
	ihevcd_ilf_padding.c
	ihevcd_fmt_conv.c
	x86/ihevcd_function_selector.c
	x86/ihevcd_function_selector_generic.c
	x86/ihevcd_function_selector_ssse3.c
	x86/ihevcd_function_selector_sse42.c
	x86/ihevcd_fmt_conv_ssse3_intr.c
	x86/ihevcd_it_rec_dc_ssse3_intr.c
	x86/ihevcd_it_rec_dc_sse42_intr.c
	../common/x86/ihevc_inter_pred_filters_ssse3_intr.c
	../common/x86/ihevc_weighted_pred_ssse3_intr.c
	../common/x86/ihevc_intra_pred_filters_ssse3_intr.c
	../common/x86/ihevc_chroma_intra_pred_filters_ssse3_intr.c
	../common/x86/ihevc_itrans_recon_ssse3_intr.c
	../common/x86/ihevc_itrans_recon_16x16_ssse3_intr.c
	../common/x86/ihevc_itrans_recon_32x32_ssse3_intr.c
	../common/x86/ihevc_sao_ssse3_intr.c
	../common/x86/ihevc_deblk_ssse3_intr.c
	../common/x86/ihevc_padding_ssse3_intr.c
	../common/x86/ihevc_mem_fns_ssse3_intr.c
	../common/x86/ihevc_inter_pred_filters_sse42_intr.c
	../common/x86/ihevc_weighted_pred_sse42_intr.c
	../common/x86/ihevc_intra_pred_filters_sse42_intr.c
	../common/x86/ihevc_chroma_intra_pred_filters_sse42_intr.c
	../common/x86/ihevc_itrans_recon_sse42_intr.c
	../common/x86/ihevc_16x16_itrans_recon_sse42_intr.c
	../common/x86/ihevc_32x32_itrans_recon_sse42_intr.c
	../common/x86/ihevc_tables_x86_intr.c

)
 
INCLUDE_DIRECTORIES(
	${libhevc_top_srcdir}/decoder
	${libhevc_top_srcdir}/common
	${libhevc_top_srcdir}/common/x86
)

ADD_DEFINITIONS (${CMAKE_C_FLAGS})

ADD_LIBRARY (hevcdev STATIC ${hevcdev_src_files})

SET(LIBRARY_OUTPUT_PATH ${libhevc_top_srcdir}/lib)



