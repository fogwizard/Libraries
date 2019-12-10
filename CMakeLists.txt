cmake_minimum_required(VERSION 2.4.4)
set(CMAKE_ALLOW_LOOSE_LOOP_CONSTRUCTS ON)

project(m4f C)

set(VERSION "1.2.11")

# this one is important
SET(CMAKE_SYSTEM_NAME Linux)

#this one not so much
SET(CMAKE_SYSTEM_VERSION 1)

SET(CMAKE_C_COMPILER "/usr/bin/arm-none-eabi-gcc")

add_definitions("-DSTM32F401xC")
add_definitions("-DUSE_HAL_DRIVER")

SET(CMAKE_C_FLAGS "-mcpu=cortex-m4 -mthumb -mlittle-endian -mfpu=fpv4-sp-d16 -mfloat-abi=hard -mthumb-interwork ")

include_directories(CMSIS/Include/)
include_directories(CMSIS/Device/ST/STM32F4xx/Include)
include_directories(STM32F4xx_HAL_Driver/Inc)
include_directories(../platform/include/)

set(ZLIB_PUBLIC_HDRS
)
set(ZLIB_PRIVATE_HDRS
)

set(ZLIB_SRCS
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_usart.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_sdram.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_adc_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_spdifrx.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_flash_ramfunc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_cec.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dac.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_fmpi2c.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_fmpi2c_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_cortex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_dac.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_flash_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_utils.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dcmi.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_smartcard.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_timebase_rtc_wakeup_template.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_spi.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_rtc_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_wwdg.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_tim_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_cryp_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_usart.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_flash.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dma2d.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_ltdc_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_sdmmc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_pwr_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_hash.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_rtc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_i2s.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_dma.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_mmc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_uart.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_rcc_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_dma2d.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_crc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_sd.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_i2c.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dfsdm.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_hcd.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_adc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dac_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_pcd_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_eth.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_sai.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dcmi_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_adc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_spi.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_timebase_rtc_alarm_template.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_rng.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_iwdg.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_ltdc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_gpio.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dsi.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_cryp.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_rng.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_pcd.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_can.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_tim.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_msp_template.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_rtc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_pccard.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_pwr.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_gpio.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_fmc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_exti.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_tim.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_rcc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_i2s_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_usb.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dma_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_hash_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_sai_ex.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_irda.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_sram.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_nor.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_lptim.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_rcc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_dma.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_nand.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_pwr.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_qspi.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_lptim.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_fsmc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_i2c.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_ll_crc.c
    STM32F4xx_HAL_Driver/Src/stm32f4xx_hal_i2c_ex.c
    CMSIS/Device/ST/STM32F4xx/Source/Templates/system_stm32f4xx.c)

add_library(m4f STATIC ${ZLIB_SRCS} ${ZLIB_ASMS} ${ZLIB_PUBLIC_HDRS} ${ZLIB_PRIVATE_HDRS})
