#----------------------------------------------------------------------------
# On command line:
#
# make all = Make software.
#
# make clean = Clean out built project files.
#
# make coff = Convert ELF to AVR COFF.
#
# make extcoff = Convert ELF to AVR Extended COFF.
#
# make program = Download the hex file to the device.
#                Please customize your programmer settings(PROGRAM_CMD)
#
# make teensy = Download the hex file to the device, using teensy_loader_cli.
#               (must have teensy_loader_cli installed).
#
# make dfu = Download the hex file to the device, using dfu-programmer (must
#            have dfu-programmer installed).
#
# make flip = Download the hex file to the device, using Atmel FLIP (must
#             have Atmel FLIP installed).
#
# make dfu-ee = Download the eeprom file to the device, using dfu-programmer
#               (must have dfu-programmer installed).
#
# make flip-ee = Download the eeprom file to the device, using Atmel FLIP
#                (must have Atmel FLIP installed).
#
# make debug = Start either simulavr or avarice as specified for debugging, 
#              with avr-gdb or avr-insight as the front end for debugging.
#
# make filename.s = Just compile filename.c into the assembler code only.
#
# make filename.i = Create a preprocessed source file for use in submitting
#                   bug reports to the GCC project.
#
# To rebuild project do "make clean" then "make all".
#----------------------------------------------------------------------------

# Target file name (without extension).
TARGET = ergodox_pjrc

# Directory common source filess exist
TOP_DIR = ../..

# Directory keyboard dependent files exist
TARGET_DIR = .

# project specific files
SRC =	keymap.c \
	matrix.c \
	led.c \
	ergodox.c \
	twimaster.c

CONFIG_H = config.h


# MCU name, you MUST set this to match the board you are using
# type "make clean" after changing this, so all files will be rebuilt
MCU = atmega32u4


# Processor frequency.
#   Normally the first thing your program should do is set the clock prescaler,
#   so your program will run at the correct speed.  You should also set this
#   variable to same clock speed.  The _delay_ms() macro uses this, and many
#   examples use this variable to calculate timings.  Do not add a "UL" here.
F_CPU = 16000000


# Boot Section Size in *bytes*
#   Teensy halfKay   512
#   Atmel DFU loader 4096
#   LUFA bootloader  4096
OPT_DEFS += -DBOOTLOADER_SIZE=512 -DFLASH_SIZE_BYTES=0x8000


# Build Options
#   comment out to disable the options.
#
BOOTMAGIC_ENABLE = yes	# Virtual DIP switch configuration(+1000)
MOUSEKEY_ENABLE = no	# Mouse keys(+5000)
EXTRAKEY_ENABLE = yes	# Audio control and System control(+600)
CONSOLE_ENABLE = yes    # Console for debug
COMMAND_ENABLE = yes    # Commands for debug and configuration
SLEEP_LED_ENABLE = yes  # Breathing sleep LED during USB suspend
NKRO_ENABLE = yes	# USB Nkey Rollover(+500)
#PS2_MOUSE_ENABLE = yes	# PS/2 mouse(TrackPoint) support
INVERT_NUMLOCK = yes 	# invert state of NumLock led


# Search Path
VPATH += $(TARGET_DIR)
VPATH += $(TOP_DIR)

include $(TOP_DIR)/protocol/pjrc.mk
include $(TOP_DIR)/common.mk
include $(TOP_DIR)/rules.mk

dvorak: OPT_DEFS += -DKEYMAP_DVORAK
dvorak: all

colemak: OPT_DEFS += -DKEYMAP_COLEMAK
colemak: all

workman: OPT_DEFS += -DKEYMAP_WORKMAN
workman: all

cub: OPT_DEFS += -DKEYMAP_CUB
cub: all

jccolemak: OPT_DEFS += -DKEYMAP_JCCOLEMAK
jccolemak: all

