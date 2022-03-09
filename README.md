# Simple PWM Audio Setup for Raspberry Pi (zero)

This is a simple Guide for a Simple Setup

## Mono Audio

### What you'll need:
- Speakers
- 2x Wires
- Raspberry Pi

### Wiring

The Wiring is as simple as connecting the speaker's vcc to a raspi's pwm0 or pwm1 (pwm1=GPIO13 or GPIO19, pwm0= GPIO18 or GPIO12)

Picture coming soon

### Config

To set PWM Audio you just need to add following lines to your /boot/config.txt:

```
# Only tested this on Zero, check if next line is there before adding
dtparam=audio=on
# GPIO Pins, not Board
gpio=12,13,a5
audio_pwm_mode=2
dtoverlay=audremap,pins_12_13
```

Then go into raspi-config/system/audio and select the headphones
