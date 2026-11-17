
# HeartBeat: Gesture-Controlled Audio

A touchless music player on an STM32. Swipe to play, pause, skip and change volume, while a 16×16 LED matrix pulses to the music.

Built for EECS 373 (Embedded System Design) at the University of Michigan.

**Demo video and poster:** [shaniya.me/#eecs373](https://shaniya.me/#eecs373)

## Why

Traditional audio controls need physical contact, which is a problem when you're multitasking or have limited hand mobility. HeartBeat is controlled entirely by gestures, with lights that match the pace and mood of each song.

## How it works

| Part | Details |
|---|---|
| Audio | A laptop streams PCM audio over UART to the STM32's on-chip DAC |
| Gestures | Two APDS9960 sensors over I²C detect swipes |
| Display | An ILI9488 LCD over SPI shows the song title, artist and album art |
| Lighting | FFTs computed with ARM CMSIS-DSP drive a 16×16 SK6812 LED equalizer |

**Hardware:** STM32L4R5ZI (Nucleo-144), 2× APDS9960, ILI9488 LCD, SK6812 16×16 matrix

## Repository layout

| File | Purpose |
|---|---|
| `main.c` | Main loop: audio playback, gesture handling, display and LED updates |
| `apds9960.c/.h` | Gesture sensor driver |
| `ili9488.c/.h`, `lcd_io_spi_hal.c` | LCD driver over SPI |
| `sk6812.c/.h` | LED matrix driver |

