# apps include
includes += \
	-I$(ROOT)/apps/$(APP_CASE)/board/$(CPU) \
	-I$(ROOT)/apps/$(APP_CASE)/include \
	-I$(ROOT)/apps/common \
	-I$(ROOT)/apps/common/include \
	-I$(ROOT)/apps/common/config/include \
	-I$(ROOT)/apps/mesh/include \
	-I$(ROOT)/apps/common/third_party_profile/common/ \
    -I$(ROOT)/apps/common/third_party_profile/jieli/JL_rcsp/rcsp_updata/ \
	-I$(ROOT)/apps/common/third_party_profile/jieli/JL_rcsp \
	-I$(ROOT)/apps/common/third_party_profile/jieli/ \

# include_lib include
includes += \
	-I$(ROOT)/include_lib \
	-I$(ROOT)/include_lib/driver \
	-I$(ROOT)/include_lib/driver/device \
	-I$(ROOT)/include_lib/driver/cpu/$(CPU) \
	-I$(ROOT)/include_lib/system \
	-I$(ROOT)/include_lib/system/generic \
	-I$(ROOT)/include_lib/system/device \
	-I$(ROOT)/include_lib/system/fs \
	-I$(ROOT)/include_lib/system/os/FreeRTOS/ \
	-I$(ROOT)/include_lib/update \
	-I$(ROOT)/include_lib/btstack \
	-I$(ROOT)/include_lib/btctrler \
	-I$(ROOT)/include_lib/btctrler/port/$(CPU) \


# APP case code
objs += \
	$(ROOT)/apps/$(APP_CASE)/lib_config/lib_btctrler_config.o \
	$(ROOT)/apps/$(APP_CASE)/lib_config/lib_driver_config.o \
	$(ROOT)/apps/$(APP_CASE)/lib_config/lib_system_config.o \
	$(ROOT)/apps/$(APP_CASE)/lib_config/lib_profile_config.o \
	$(ROOT)/apps/$(APP_CASE)/lib_config/lib_update_config.o \
	$(ROOT)/apps/$(APP_CASE)/lib_config/lib_btstack_config.o \

objs += \
	$(ROOT)/apps/$(APP_CASE)/app_mesh.o \
	$(ROOT)/apps/$(APP_CASE)/app_main.o \
	$(ROOT)/apps/$(APP_CASE)/app_idle.o \
	$(ROOT)/apps/$(APP_CASE)/version.o \
	$(ROOT)/apps/$(APP_CASE)/log_config.o \
	$(ROOT)/apps/$(APP_CASE)/user_cfg.o \
	$(ROOT)/apps/common/update/update.o \
    $(ROOT)/apps/common/update/testbox_update.o \
	$(ROOT)/apps/common/third_party_profile/common/custom_cfg.o \
    $(ROOT)/apps/common/third_party_profile/jieli/JL_rcsp/rcsp_bluetooth.o \
    $(ROOT)/apps/common/third_party_profile/jieli/JL_rcsp/rcsp_updata/rcsp_user_update.o \
	$(ROOT)/apps/common/third_party_profile/jieli/JL_rcsp/rcsp_updata/rcsp_ch_loader_download.o \

objs += \
	$(ROOT)/apps/common/key/iokey.o \
	$(ROOT)/apps/common/key/adkey.o \
    $(ROOT)/apps/common/key/key_driver.o \

objs += \
	$(ROOT)/apps/mesh/MshMDL/lightness_srv.o \
	$(ROOT)/apps/mesh/MshMDL/generic_power_onoff_srv.o \
	$(ROOT)/apps/mesh/MshMDL/generic_level_srv.o \
	$(ROOT)/apps/mesh/MshMDL/generic_onoff_srv.o \
	$(ROOT)/apps/mesh/MshMDL/generic_onoff_cli.o \

mesh_dir = sig_mesh

# SIG Mesh source code
MESH_C = \
	$(wildcard common/third_party_profile/$(mesh_dir)/net/*.c) \
	$(wildcard common/third_party_profile/$(mesh_dir)/*.c) \
	$(wildcard common/third_party_profile/$(mesh_dir)/kernel/*.c) \
	$(wildcard common/third_party_profile/$(mesh_dir)/api/*.c) \
	$(wildcard common/third_party_profile/$(mesh_dir)/adaptation/*.c) \
	$(wildcard common/third_party_profile/$(mesh_dir)/adaptation/kernel/*.c) \
	$(wildcard common/third_party_profile/$(mesh_dir)/adaptation/ble_core/*.c) \
	common/third_party_profile/$(mesh_dir)/tinycrypt/source/cmac_mode.c \
	common/third_party_profile/$(mesh_dir)/tinycrypt/source/aes_encrypt.c \
	common/third_party_profile/$(mesh_dir)/tinycrypt/source/utils.c \

# SIG Mesh source include
MESH_H = \
	-I$(abspath common/third_party_profile) \
	-I$(abspath common/third_party_profile/$(mesh_dir)) \
	-I$(abspath common/third_party_profile/$(mesh_dir)/tinycrypt/include) \
	-I$(abspath common/third_party_profile/$(mesh_dir)/adaptation) \

# Mesh examples
MESH_C += \
	$(wildcard mesh/api/*.c) \
	$(wildcard mesh/examples/*.c) \

# Mesh examples include
MESH_H += \
	-I$(ROOT)/apps/mesh/api \

objs += $(patsubst %.c, %.o, $(MESH_C))

includes += $(MESH_H)

