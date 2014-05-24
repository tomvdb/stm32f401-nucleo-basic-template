CC=arm-none-eabi-gcc
AR=arm-none-eabi-ar

###########################################

vpath %.c STM32F4xx_HAL_Driver/Src

CFLAGS  = -ggdb -O0 -Wall -Wextra -Warray-bounds
CFLAGS += -mcpu=cortex-m4 -mthumb -mlittle-endian -mthumb-interwork
CFLAGS += -mfloat-abi=hard -mfpu=fpv4-sp-d16
CFLAGS += -DUSE_STDPERIPH_DRIVER -DSTM32F4XX -DSTM32F401xE
CFLAGS += -ICMSIS/Include -ICMSIS/Device/ST/STM32F4xx/Include -ISTM32F4xx_HAL_Driver/Inc

SRCS = stm32f4xx_hal.c           stm32f4xx_hal_msp_template.c \
 stm32f4xx_hal_adc.c       stm32f4xx_hal_nand.c \
 stm32f4xx_hal_adc_ex.c    stm32f4xx_hal_nor.c \
 stm32f4xx_hal_can.c       stm32f4xx_hal_pccard.c \
 stm32f4xx_hal_cortex.c    stm32f4xx_hal_pcd.c \
 stm32f4xx_hal_crc.c stm32f4xx_hal_pwr.c \
 stm32f4xx_hal_cryp.c      stm32f4xx_hal_pwr_ex.c \
 stm32f4xx_hal_cryp_ex.c   stm32f4xx_hal_rcc.c \
 stm32f4xx_hal_dac.c       stm32f4xx_hal_rcc_ex.c \
 stm32f4xx_hal_dac_ex.c    stm32f4xx_hal_rng.c \
 stm32f4xx_hal_dcmi.c      stm32f4xx_hal_rtc.c \
 stm32f4xx_hal_dma.c       stm32f4xx_hal_rtc_ex.c \
 stm32f4xx_hal_dma2d.c     stm32f4xx_hal_sai.c \
 stm32f4xx_hal_dma_ex.c    stm32f4xx_hal_sd.c \
 stm32f4xx_hal_eth.c       stm32f4xx_hal_sdram.c \
 stm32f4xx_hal_flash.c     stm32f4xx_hal_smartcard.c \
 stm32f4xx_hal_flash_ex.c  stm32f4xx_hal_spi.c \
 stm32f4xx_hal_gpio.c      stm32f4xx_hal_sram.c \
 stm32f4xx_hal_hash.c      stm32f4xx_hal_tim.c \
 stm32f4xx_hal_hash_ex.c   stm32f4xx_hal_tim_ex.c \
 stm32f4xx_hal_hcd.c       stm32f4xx_hal_uart.c \
 stm32f4xx_hal_i2c.c       stm32f4xx_hal_usart.c \
 stm32f4xx_hal_i2c_ex.c    stm32f4xx_hal_wwdg.c \
 stm32f4xx_hal_i2s.c       stm32f4xx_ll_fmc.c \
 stm32f4xx_hal_i2s_ex.c    stm32f4xx_ll_fsmc.c \
 stm32f4xx_hal_irda.c      stm32f4xx_ll_sdmmc.c \
 stm32f4xx_hal_iwdg.c      stm32f4xx_ll_usb.c \
 stm32f4xx_hal_ltdc.c


OBJS = $(SRCS:.c=.o)

.PHONY: libstmf4.a

all: libstmf4.a

%.o : %.c
	$(CC) $(CFLAGS) -c -o $@ $^

libstmf4.a: $(OBJS)
	$(AR) -r $@ $(OBJS)

clean:
	rm -f $(OBJS) libstmf4.a
