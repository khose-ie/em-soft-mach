# CPU
CPU = -mcpu=cortex-m7

# FPU
FPU = -mfpu=fpv4-sp-d16

# Float-ABI
FLOAT_ABI = -mfloat-abi=hard

# MCU
MCU = $(CPU) -mthumb $(FPU) $(FLOAT_ABI)

# MCU Define
MCU_DEFS  = -DUSE_HAL_DRIVER
MCU_DEFS += $(if $(CONFIG_CPU_MODEL_STM32H723XX),  -DSTM32H723xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H725XX),  -DSTM32H725xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H730XX),  -DSTM32H730xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H730XXQ), -DSTM32H730xxQ) \
            $(if $(CONFIG_CPU_MODEL_STM32H733XX),  -DSTM32H733xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H735XX),  -DSTM32H735xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H742XX),  -DSTM32H742xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H743XX),  -DSTM32H743xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H745XG),  -DSTM32H745xG)  \
            $(if $(CONFIG_CPU_MODEL_STM32H745XX),  -DSTM32H745xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H747XG),  -DSTM32H747xG)  \
            $(if $(CONFIG_CPU_MODEL_STM32H747XX),  -DSTM32H747xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H750XX),  -DSTM32H750xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H753XX),  -DSTM32H753xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H755XX),  -DSTM32H755xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H757XX),  -DSTM32H757xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H7A3XX),  -DSTM32H7A3xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H7A3XXQ), -DSTM32H7A3xxQ) \
            $(if $(CONFIG_CPU_MODEL_STM32H7B0XX),  -DSTM32H7B0xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H7B0XXQ), -DSTM32H7B0xxQ) \
            $(if $(CONFIG_CPU_MODEL_STM32H7B3XX),  -DSTM32H7B3xx)  \
            $(if $(CONFIG_CPU_MODEL_STM32H7B3XXq), -DSTM32H7B3xxQ)

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
              -I$(srctree)/$(CMSIS_PATH)/cmsis-core/RTOS2/Include

# MCU Includes
APPINCLUDE += -I$(srctree)/$(CMSIS_PATH)/cmsis-device-h7/Include \
              -I$(srctree)/$(DRIVER_PATH)/stm32h7xx-hal-driver/Inc \
              -I$(srctree)/$(DRIVER_PATH)/stm32h7xx-hal-driver/Inc/Legacy

-include arch/arm/mach-stm/stm32h7xx/platform.mk
