# TDX Rivals Script

## Overview
This is a comprehensive game enhancement script for Roblox Rivals that provides various features including aimbot, ESP, flight, and automation capabilities.

## Installation

### Loadstring
```lua
loadstring(game:HttpGet("https://raw.githubusercontent.com/7swazys/rbx-rivals-tdx-scripts/refs/heads/main/script"))()
```

## Features

### Aimbot System
- Three different modes: Smooth, Snappy, and Rage
- Customizable FOV (Field of View) for each mode
- Toggle between MouseRel and CFrame targeting methods
- Visibility checks to prevent targeting through walls
- Adjustable tracking range and smoothing values

### Visual ESP
- Player bounding boxes
- Tracers from mouse to players
- Color-coded health bars (green/gold/red based on health percentage)
- Dynamic visual updates based on selected mode
- Range-based visibility

### Movement Features
- Flight mode with WASD + Space controls
- Noclip to walk through walls
- Adjustable flight speed

### Automation
- Triggerbot (auto-click when targeting)
- Auto-collect for health and ammo drops
- Smart collection based on current needs

### User Interface
- Modern notification system with color-coded alerts
- Intro screen showing all features and keybinds
- Smooth animations and transitions
- Custom color palette for visual consistency

## Keybinds

### Aimbot Controls
- R: Toggle aimbot on/off
- [: Switch targeting method (MouseRel/CFrame)
- K: Switch between Mode 1 and Mode 2
- J: Toggle Rage mode

### Movement Controls
- B: Toggle flight
- N: Toggle noclip
- WASD: Flight movement
- Space: Fly upward

### Automation Controls
- ]: Toggle triggerbot
- G: Toggle auto-collect

## Color Palette
- Neon Purple: Primary UI color
- Emerald Green: Success states and high health
- Vibrant Rose: Rage mode and critical states
- Gold: Warning states and medium health
- Deep Abyss: Background color

## Technical Details

### Targeting System
The aimbot uses a multi-layered approach:
1. Calculates distance to all players within tracking range
2. Converts 3D positions to screen space
3. Checks if targets are within FOV circle
4. Performs raycast visibility checks
5. Selects closest valid target

### ESP Rendering
Uses Roblox Drawing API to create:
- Square boxes around players
- Lines from mouse to players
- Health bar indicators with smooth interpolation

### Auto-Collection
Scans workspace for objects named "_drop" and triggers touch events for:
- Health pickups (when player is damaged)
- Ammo pickups (always collected)

## Mode Specifications

### Mode 1 (Smooth)
- FOV: 35 pixels
- Smooth value: 1.1
- Best for: Precision tracking

### Mode 2 (Snappy)
- FOV: 150 pixels
- Smooth value: 0.50
- Best for: Quick target acquisition

### Mode 3 (Rage)
- FOV: 900 pixels (visual: 50)
- Smooth value: 1.0
- Best for: Maximum tracking range

## Configuration

### Default Settings
- Tracking Range: 250 studs
- Target Part: Head
- Flight Speed: 140
- Auto-collect: Health and Ammo enabled
- FOV Circle: Filled, 50% transparency

## Dependencies
- Roblox Drawing API
- TweenService
- RunService
- UserInputService
- Standard Roblox executor functions (mousemoverel, mouse1press, firetouchinterest)

## Initialization
The script automatically:
1. Waits for game to load
2. Sets up character event handlers
3. Creates ESP for all existing players
4. Displays intro screen
5. Begins render loop

## Notes
- Script runs in a separate thread using spawn
- Character changes are handled automatically
- All visual elements use consistent color theming
- Notifications auto-dismiss after 2.5 seconds
- Requires a Roblox executor with Drawing API support

## Credits
Made by tdxcripts
