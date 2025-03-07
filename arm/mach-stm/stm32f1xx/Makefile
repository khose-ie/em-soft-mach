# CPU
CPU = -mcpu=cortex-m3

# FPU
FPU = -mfpu=fpv4-sp-d16

# Float-ABI
FLOAT_ABI = -mfloat-abi=hard

# MCU
MCU = $(CPU) -mthumb $(FPU) $(FLOAT_ABI)

# MCU Define
MCU_DEFS  = -DUSE_HAL_DRIVER
MCU_DEFS += $(if $(CONFIG_CPU_MODEL_STM32F100XB),  -DSTM32F100xB) \
            $(if $(CONFIG_CPU_MODEL_STM32F100XE),  -DSTM32F100xE) \
            $(if $(CONFIG_CPU_MODEL_STM32F101X6),  -DSTM32F101x6) \
            $(if $(CONFIG_CPU_MODEL_STM32F101XB),  -DSTM32F101xB) \
            $(if $(CONFIG_CPU_MODEL_STM32F101XE),  -DSTM32F101xE) \
            $(if $(CONFIG_CPU_MODEL_STM32F101XG),  -DSTM32F101xG) \
            $(if $(CONFIG_CPU_MODEL_STM32F102X6),  -DSTM32F102x6) \
            $(if $(CONFIG_CPU_MODEL_STM32F102XB),  -DSTM32F102xB) \
            $(if $(CONFIG_CPU_MODEL_STM32F103X6),  -DSTM32F103x6) \
            $(if $(CONFIG_CPU_MODEL_STM32F103XB),  -DSTM32F103xB) \
            $(if $(CONFIG_CPU_MODEL_STM32F103XE),  -DSTM32F103xE) \
            $(if $(CONFIG_CPU_MODEL_STM32F103XG),  -DSTM32F103xG) \
            $(if $(CONFIG_CPU_MODEL_STM32F105XC),  -DSTM32F105xC) \
            $(if $(CONFIG_CPU_MODEL_STM32F107XC),  -DSTM32F107xC)

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
APPINCLUDE += -I$(srctree)/$(CMSIS_PATH)/cmsis-core/RTOS2/Include \
              -I$(srctree)/$(DRIVER_PATH)/stm32f1xx-hal-driver/Inc \
              -I$(srctree)/$(DRIVER_PATH)/stm32f1xx-hal-driver/Inc/Legacy

include arch/arm/mach-stm/stm32f1xx/makefile-platform
