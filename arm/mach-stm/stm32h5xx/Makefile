CPU = -mcpu=cortex-m33

# FPU
FPU = -mfpu=fpv4-sp-d16

# Float-ABI
FLOAT_ABI = -mfloat-abi=hard

# MCU
MCU = $(CPU) -mthumb $(FPU) $(FLOAT_ABI)

# MCU Define
MCU_DEFS  = -DUSE_HAL_DRIVER
MCU_DEFS += $(if $(CONFIG_CPU_MODEL_STM32H503XX),  -DSTM32H503xx) \
            $(if $(CONFIG_CPU_MODEL_STM32H523XX),  -DSTM32H523xx) \
            $(if $(CONFIG_CPU_MODEL_STM32H533XX),  -DSTM32H533xx) \
            $(if $(CONFIG_CPU_MODEL_STM32H562XX),  -DSTM32H562xx) \
            $(if $(CONFIG_CPU_MODEL_STM32H563XX),  -DSTM32H563xx) \
            $(if $(CONFIG_CPU_MODEL_STM32H573XX),  -DSTM32H573xx)

# MCU C Flags
KBUILD_CFLAGS   += $(MCU) \
                   $(MCU_DEFS) \
                   -fdata-sections \
                   -ffunction-sections

# MCU C++ Flags
KBUILD_CXXFLAGS += $(MCU) \
                   $(MCU_DEFS) \
                   -fdata-sections \
                   -ffunction-sections

# MCU A Flags
KBUILD_AFLAGS   += $(MCU) \
                   $(MCU_DEFS) \

# MCU Linker Flags
KBUILD_LDFLAGS  += $(MCU) \
                   -specs=nano.specs \
                   -lc -lm -lnosys

# STM32 Common CMSIS Includes
APPINCLUDE += -I$(srctree)/$(CMSIS_PATH)/cmsis-core/Include \
              -I$(srctree)/$(CMSIS_PATH)/cmsis-core/Core/Include \
              -I$(srctree)/$(CMSIS_PATH)/cmsis-core/NN/Include \
              -I$(srctree)/$(CMSIS_PATH)/cmsis-core/RTOS2/Include

# MCU Includes
APPINCLUDE += -I$(srctree)/$(CMSIS_PATH)/cmsis-device-h5/Include \
              -I$(srctree)/$(DRIVER_PATH)/stm32h5xx-hal-driver/Inc \
              -I$(srctree)/$(DRIVER_PATH)/stm32h5xx-hal-driver/Inc/Legacy

include arch/arm/mach-stm/stm32h5xx/makefile-platform
