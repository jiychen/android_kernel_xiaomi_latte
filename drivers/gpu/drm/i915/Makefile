#
# Makefile for the drm device driver.  This driver provides support for the
# Direct Rendering Infrastructure (DRI) in XFree86 4.1.0 and higher.

ccflags-y := -Iinclude/drm -Werror

# Please keep these build lists sorted!

# core driver code
i915-y := i915_drv.o \
	  i915_params.o \
          i915_suspend.o \
	  i915_sysfs.o \
	  i915_scheduler.o \
	  intel_pm.o
i915-$(CONFIG_COMPAT)   += i915_ioc32.o
i915-$(CONFIG_DEBUG_FS) += i915_debugfs.o
i915-$(CONFIG_SUPPORT_LPDMA_HDMI_AUDIO) += hdmi_audio_if.o

# GEM code
i915-y += i915_cmd_parser.o \
	  i915_gem_context.o \
	  i915_gem_render_state.o \
	  i915_gem_debug.o \
	  i915_gem_dmabuf.o \
	  i915_gem_evict.o \
	  i915_gem_execbuffer.o \
	  i915_gem_gtt.o \
	  i915_gem.o \
	  i915_gem_stolen.o \
	  i915_gem_tiling.o \
	  i915_gem_userptr.o \
	  i915_gpu_error.o \
	  i915_irq.o \
	  i915_perfmon.o \
	  i915_trace_points.o \
	  intel_huc_chv.o \
	  intel_lrc.o \
	  intel_ringbuffer.o \
	  intel_uncore.o

# autogenerated null render state
i915-y += intel_renderstate_gen6.o \
	  intel_renderstate_gen7.o \
	  intel_renderstate_gen8.o

# modesetting core code
i915-y += intel_bios.o \
	  intel_display.o \
	  intel_modes.o \
	  intel_overlay.o \
	  intel_sideband.o \
	  intel_sprite.o
i915-$(CONFIG_ACPI)		+= intel_acpi.o intel_opregion.o
i915-$(CONFIG_DRM_I915_FBDEV)	+= intel_fbdev.o

# modesetting output/encoder code
i915-y += dvo_ch7017.o \
	  dvo_ch7xxx.o \
	  dvo_ivch.o \
	  dvo_ns2501.o \
	  dvo_sil164.o \
	  dvo_tfp410.o \
	  intel_crt.o \
	  intel_ddi.o \
	  intel_dp.o \
	  intel_dsi_cmd.o \
	  intel_dsi.o \
	  intel_dsi_pll.o \
	  intel_dsi_panel_vbt.o \
	  intel_dvo.o \
	  intel_hdmi.o \
	  intel_i2c.o \
	  intel_lvds.o \
	  intel_panel.o \
	  intel_sdvo.o \
	  intel_tv.o \
	  i915_dpst.o \
	  intel_clrmgr.o \
	  i915_sprite_csc.o \
	  i915_adf_wrapper.o \
	  intel_drrs.o \
	  intel_dsi_drrs.o \
	  intel_edp_drrs.o

# legacy horrors
i915-y += i915_dma.o \
	  i915_ums.o

# Extended ioctl interface
# Note that these are separated out to reduce the chance of conflicts
# with the upstream Linux
i915-y += i915_ext_ioctl.o
i915-y += i915_gem_userdata.o
i915-$(CONFIG_DRM_I915_SYNC)  += intel_sync.o

obj-$(CONFIG_DRM_I915)  += i915.o


CFLAGS_i915_trace_points.o := -I$(src)
