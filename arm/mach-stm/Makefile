#
# USER CONFIGURATION VARIABLE
#
BSP_PATH    ?= libs/STMicroelectronics/bsp
CMSIS_PATH  ?= libs/STMicroelectronics/cmsis
DRIVER_PATH ?= libs/STMicroelectronics/driver

PLATFORM_PATH ?= platform

-include $(if $(CONFIG_CPU_SERIES_STM32F1XX), arch/arm/mach-stm/stm32f1xx/Makefile)
-include $(if $(CONFIG_CPU_SERIES_STM32F4XX), arch/arm/mach-stm/stm32f4xx/Makefile)
-include $(if $(CONFIG_CPU_SERIES_STM32F7XX), arch/arm/mach-stm/stm32f7xx/Makefile)
-include $(if $(CONFIG_CPU_SERIES_STM32H5XX), arch/arm/mach-stm/stm32h5xx/Makefile)
-include $(if $(CONFIG_CPU_SERIES_STM32H7XX), arch/arm/mach-stm/stm32h7xx/Makefile)
