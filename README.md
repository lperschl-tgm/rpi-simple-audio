# Simple PWM Audio Setup for Raspberry Pi (zero)

This is a simple Guide for a Simple Setup

## Mono Audio

### What you'll need:
- Speakers
- 2x Wires
- Raspberry Pi

### Wiring

The Wiring is as simple as connecting the speaker's vcc to a raspi's pwm0 or pwm1 (pwm1=GPIO13 or GPIO19, pwm0= GPIO18 or GPIO12)

![Mono Wiring](https://user-images.githubusercontent.com/73284582/157530011-1812c41b-64f2-44ab-bc78-5d3ffaa17012.png)

### Config

To set PWM Audio you just need to add following lines to your /boot/config.txt:

```
# Only tested this on Zero, check if next line is there before adding
dtparam=audio=on
# GPIO Pins, not Board
gpio=19,a5
audio_pwm_mode=2
dtoverlay=audremap,pins_19
```

Then go into raspi-config/system/audio and select the headphones

## Stereo Audio

### What you'll need:
- 2x Speakers
- 4x Wires
- Raspberry Pi

### Wiring

The Wiring is as simple as connecting the speaker's vcc to a raspi's pwm0 or pwm1 (pwm1=GPIO13 or GPIO19, pwm0= GPIO18 or GPIO12)
Exactly the Same as with Mono, but this time you need one on pwm0 and one on pwm1 (I think at least, could be that you can connect both to one pwm channel)

![Stereo Wiring](https://user-images.githubusercontent.com/73284582/157531123-badd41e4-79e7-4ce3-b252-cc238dd36d5c.png)

### Config

To set PWM Audio you just need to add following lines to your /boot/config.txt:

```
# Only tested this on Zero, check if next line is there before adding
dtparam=audio=on
# GPIO Pins, not Board
gpio=12,19,a5
audio_pwm_mode=2
dtoverlay=audremap,pins_12_19
```

Then go into raspi-config/system/audio and select the headphones
