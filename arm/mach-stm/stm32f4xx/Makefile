# CPU
CPU = -mcpu=cortex-m4

# FPU
FPU = -mfpu=fpv4-sp-d16

# Float-ABI
FLOAT_ABI = -mfloat-abi=hard

# MCU
MCU = $(CPU) -mthumb $(FPU) $(FLOAT_ABI)

# MCU Define
MCU_DEFS  = -DUSE_HAL_DRIVER
MCU_DEFS += $(if $(CONFIG_CPU_MODEL_STM32F401XC),  -DSTM32F401xC) \
            $(if $(CONFIG_CPU_MODEL_STM32F401XE),  -DSTM32F401xE) \
            $(if $(CONFIG_CPU_MODEL_STM32F405XX),  -DSTM32F405xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F407XX),  -DSTM32F407xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F410CX),  -DSTM32F410Cx) \
            $(if $(CONFIG_CPU_MODEL_STM32F410RX),  -DSTM32F410Rx) \
            $(if $(CONFIG_CPU_MODEL_STM32F410TX),  -DSTM32F410Tx) \
            $(if $(CONFIG_CPU_MODEL_STM32F411XE),  -DSTM32F411xE) \
            $(if $(CONFIG_CPU_MODEL_STM32F412CX),  -DSTM32F412Cx) \
            $(if $(CONFIG_CPU_MODEL_STM32F412RX),  -DSTM32F412Rx) \
            $(if $(CONFIG_CPU_MODEL_STM32F412VX),  -DSTM32F412Vx) \
            $(if $(CONFIG_CPU_MODEL_STM32F412ZX),  -DSTM32F412Zx) \
            $(if $(CONFIG_CPU_MODEL_STM32F413XX),  -DSTM32F413xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F415XX),  -DSTM32F415xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F417XX),  -DSTM32F417xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F423XX),  -DSTM32F423xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F427XX),  -DSTM32F427xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F429XX),  -DSTM32F429xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F437XX),  -DSTM32F437xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F439XX),  -DSTM32F439xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F446XX),  -DSTM32F446xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F469XX),  -DSTM32F469xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F479XX),  -DSTM32F479xx)

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
APPINCLUDE += -I$(srctree)/$(CMSIS_PATH)/cmsis-device-f4/Include \
              -I$(srctree)/$(DRIVER_PATH)/stm32f4xx-hal-driver/Inc \
              -I$(srctree)/$(DRIVER_PATH)/stm32f4xx-hal-driver/Inc/Legacy

include arch/arm/mach-stm/stm32f4xx/makefile-platform
