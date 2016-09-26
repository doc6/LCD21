################################################################################
# Automatically-generated file. Do not edit!
################################################################################

-include ../makefile.init

RM := rm -rf

# All of the sources participating in the build are defined here
-include sources.mk
-include subdir.mk
-include objects.mk

ifneq ($(MAKECMDGOALS),clean)
ifneq ($(strip $(ASM_DEPS)),)
-include $(ASM_DEPS)
endif
ifneq ($(strip $(S_DEPS)),)
-include $(S_DEPS)
endif
ifneq ($(strip $(S_UPPER_DEPS)),)
-include $(S_UPPER_DEPS)
endif
ifneq ($(strip $(C_DEPS)),)
-include $(C_DEPS)
endif
endif

-include ../makefile.defs

# Add inputs and outputs from these tool invocations to the build variables 
LSS += \
LCD21.lss \

FLASH_IMAGE += \
LCD21.hex \

EEPROM_IMAGE += \
LCD21.eep \

SIZEDUMMY += \
sizedummy \


# All Target
all: LCD21.elf secondary-outputs

# Tool invocations
LCD21.elf: $(OBJS) $(USER_OBJS)
	@echo 'Building target: $@'
	@echo 'Invoking: AVR C Linker'
	avr-gcc -Wl,-Map,LCD21.map -mmcu=atmega328p -o "LCD21.elf" $(OBJS) $(USER_OBJS) $(LIBS)
	@echo 'Finished building target: $@'
	@echo ' '

LCD21.lss: LCD21.elf
	@echo 'Invoking: AVR Create Extended Listing'
	-avr-objdump -h -S LCD21.elf  >"LCD21.lss"
	@echo 'Finished building: $@'
	@echo ' '

LCD21.hex: LCD21.elf
	@echo 'Create Flash image (ihex format)'
	-avr-objcopy -R .eeprom -R .fuse -R .lock -R .signature -O ihex LCD21.elf  "LCD21.hex"
	@echo 'Finished building: $@'
	@echo ' '

LCD21.eep: LCD21.elf
	@echo 'Create eeprom image (ihex format)'
	-avr-objcopy -j .eeprom --no-change-warnings --change-section-lma .eeprom=0 -O ihex LCD21.elf  "LCD21.eep"
	@echo 'Finished building: $@'
	@echo ' '

sizedummy: LCD21.elf
	@echo 'Invoking: Print Size'
	-avr-size --format=berkeley -t LCD21.elf
	@echo 'Finished building: $@'
	@echo ' '

# Other Targets
clean:
	-$(RM) $(FLASH_IMAGE)$(ELFS)$(OBJS)$(ASM_DEPS)$(EEPROM_IMAGE)$(S_DEPS)$(SIZEDUMMY)$(S_UPPER_DEPS)$(LSS)$(C_DEPS) LCD21.elf
	-@echo ' '

secondary-outputs: $(LSS) $(FLASH_IMAGE) $(EEPROM_IMAGE) $(SIZEDUMMY)

.PHONY: all clean dependents
.SECONDARY:

-include ../makefile.targets
