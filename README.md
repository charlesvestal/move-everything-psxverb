# Move Everything PSX Verb

PlayStation 1 SPU reverb emulation audio effect module for Move Everything.

## Prerequisites

- [Move Everything](https://github.com/charlesvestal/move-everything) installed on your Ableton Move

## Installation

### Via Module Store (Recommended)

1. Launch Move Everything on your Move
2. Select **Module Store** from the main menu
3. Navigate to **Audio FX** → **PSX Verb**
4. Select **Install**

### Manual Installation

```bash
./scripts/install.sh
```

## Features

- **Preset**: 6 classic PSX reverb types (Room, Studio S/M/L, Hall, Space Echo)
- **Decay**: Wall reflection feedback amount
- **Mix**: Dry/wet blend

## Algorithm

Simplified PSX SPU reverb structure:

```
Input --> [IIR lowpass] --> [Comb bank (4x)] --> [Allpass (2x)] --> Output
                                   ^                    |
                                   |____ feedback ______|
```

## Building

```bash
./scripts/build.sh      # Build for ARM64 via Docker
./scripts/install.sh    # Deploy to Move
```

## Presets

| # | Name | Character |
|---|------|-----------|
| 0 | Room | Small, tight |
| 1 | Studio S | Short studio |
| 2 | Studio M | Medium studio |
| 3 | Studio L | Large studio |
| 4 | Hall | Concert hall |
| 5 | Space Echo | Long ethereal |

## Installation

The module installs to `/data/UserData/move-anything/modules/chain/audio_fx/psxverb/`

## Credits

Ported from [CVCHothouse](https://github.com/charlesvestal/CVCHothouse) (Daisy Seed effects pedal collection).

Based on the PlayStation 1 SPU reverb architecture as documented in:
- [No$psx SPU documentation](https://problemkaputt.de/psx-spx.htm#spureverbformula) by Martin Korth
- [Mednafen PSX emulator](https://mednafen.github.io/) SPU implementation

## License

MIT License - Copyright (c) 2025 Charles Vestal

## AI Assistance Disclaimer

This module is part of Move Everything and was developed with AI assistance, including Claude, Codex, and other AI assistants.

All architecture, implementation, and release decisions are reviewed by human maintainers.  
AI-assisted content may still contain errors, so please validate functionality, security, and license compatibility before production use.
