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
MCU_DEFS += $(if $(CONFIG_CPU_MODEL_STM32F722XX),  -DSTM32F722xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F723XX),  -DSTM32F723xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F730XX),  -DSTM32F730xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F732XX),  -DSTM32F732xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F733XX),  -DSTM32F733xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F745XX),  -DSTM32F745xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F746XX),  -DSTM32F746xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F750XX),  -DSTM32F750xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F756XX),  -DSTM32F756xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F765XX),  -DSTM32F765xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F767XX),  -DSTM32F767xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F769XX),  -DSTM32F769xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F777XX),  -DSTM32F777xx) \
            $(if $(CONFIG_CPU_MODEL_STM32F779XX),  -DSTM32F779xx)

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
APPINCLUDE += -I$(srctree)/$(CMSIS_PATH)/cmsis-device-f7/Include \
              -I$(srctree)/$(DRIVER_PATH)/stm32f7xx-hal-driver/Inc \
              -I$(srctree)/$(DRIVER_PATH)/stm32f7xx-hal-driver/Inc/Legacy

include arch/arm/mach-stm/stm32f7xx/makefile-platform
