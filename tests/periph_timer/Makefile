include ../Makefile.tests_common

FEATURES_REQUIRED = periph_timer

BOARDS_TIMER_25kHz := \
    arduino-duemilanove \
    arduino-leonardo \
    arduino-mega2560 \
    arduino-uno \
    atmega256rfr2-xpro \
    atmega328p \
    waspmote-pro \
    #

BOARDS_TIMER_32kHz := \
    hifive1 \
    hifive1b \
    %-kw41z \
    openlabs-kw41z-mini \
    frdm-k64f \
    frdm-k22f \
    slstk3401a \
    slstk3402a \
    sltb001a \
    stk3600 \
    stk3700 \
    #

BOARDS_TIMER_CLOCK_CORECLOCK := \
  cc2538dk \
  openmote-b \
  openmote-cc2538 \
  remote-reva \
  remote-revb \
  #

ifneq (,$(filter $(BOARDS_TIMER_25kHz),$(BOARD)))
  TIMER_SPEED ?= 250000
else ifneq (,$(filter $(BOARDS_TIMER_32kHz),$(BOARD)))
  TIMER_SPEED ?= 32768
else ifneq (,$(filter $(BOARDS_TIMER_CLOCK_CORECLOCK),$(BOARD)))
  TIMER_SPEED ?= CLOCK_CORECLOCK
endif

TIMER_SPEED ?= 1000000

CFLAGS += -DTIMER_SPEED=$(TIMER_SPEED)
include $(RIOTBASE)/Makefile.include
