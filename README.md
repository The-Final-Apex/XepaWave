# Airwave MIDI Controller - User Guide

## Overview

Airwave MIDI Controller transforms your webcam into a hands-free MIDI control surface. Using computer vision technology, it tracks hand movements and converts them into MIDI signals for controlling digital audio workstations and synthesizers.

---

## System Requirements

### Hardware
- Webcam (built-in or external)
- 4GB RAM minimum (8GB recommended)
- Integrated graphics cards are supported, though performance may vary

### Software
- Python 3.8 or higher
- Windows, macOS, or Linux operating system
- MIDI-compatible audio software (DAW, VST host, or hardware synthesizer)

---

## Installation Instructions

### Step 1: Install Python

Download and install Python 3.8+ from [python.org](https://python.org). Ensure Python is added to your system PATH during installation.

### Step 2: Download the Application

Clone the repository or download the source code:

```bash
git clone https://github.com/yourusername/airwave-midi-controller.git
cd airwave-midi-controller
```

### Step 3: Install Dependencies

Open a terminal or command prompt and run:

```bash
pip install opencv-python mediapipe numpy mido
```

This installs the required libraries for camera processing, hand tracking, and MIDI communication.

### Step 4: Launch the Application

Start the program with:

```bash
python airwave_controller.py
```

---

## Using the Application

### Starting the Controller

1. Click the **"Start Controller"** button in the graphical interface
2. The application will activate your webcam and establish a virtual MIDI port named "Xepawave"
3. A camera window will open showing hand tracking and visual feedback

### Connecting to Your DAW

The application creates a virtual MIDI output port. To use it:

**Ableton Live:**
- Preferences → Link MIDI → Enable "Xepawave" as input source

**FL Studio:**
- Options → MIDI Settings → Enable "Xepawave" under Input

**Logic Pro:**
- Preferences → MIDI → Check "Xepawave" in Inputs

**Other DAWs:**
- Look for "Xepawave" in MIDI input settings and enable it

### Default Control Mapping

| Hand Movement | MIDI CC | Function |
|--------------|---------|----------|
| Left hand horizontal | CC 74 | Filter Cutoff |
| Left hand vertical | CC 71 | Resonance |
| Left hand depth | CC 76 | LFO Rate |
| Right hand horizontal | CC 1 | Modulation |
| Right hand vertical | CC 11 | Expression |
| Right hand depth | Aftertouch | Channel Pressure |
| Distance between hands | CC 91 | Reverb |

### Gesture Controls

| Gesture | Effect |
|---------|--------|
| Left hand pinch (thumb + index) | Sustain Pedal |
| Left hand tight pinch | Soft Pedal |
| Right hand pinch (index + middle) | Sostenuto |
| Right hand tight pinch | Portamento |

---

## Customizing MIDI Assignments

Each movement parameter can be reassigned to any MIDI CC:

1. Select the parameter tab (Left X, Right Y, etc.)
2. Choose a MIDI CC from the dropdown menu
3. Adjust the minimum and maximum value range
4. Click **"Apply Settings"** to save changes

### Saving Configurations

- Click **"Save Configuration"** to export your custom settings
- Click **"Load Configuration"** to import previously saved settings

---

## Performance Considerations

The application is optimized for 60+ frames per second, but performance depends on hardware capabilities. For integrated graphics systems:

- Close other applications to free system resources
- Maintain good lighting for reliable hand tracking
- Use plain backgrounds for improved detection accuracy
- Lower camera resolution if experiencing performance issues

### Performance Indicators

The camera window displays:
- **FPS counter** - Shows current frame rate
- **Processing latency** - Time per frame in milliseconds

---

## Troubleshooting

### Webcam Issues
- Verify camera is connected and not in use by another application
- Check operating system privacy settings for camera access
- Try a different USB port

### MIDI Connection Issues
- Install a virtual MIDI driver (LoopMIDI recommended for Windows)
- Ensure your DAW is configured to receive MIDI from "Xepawave"
- Restart the application and DAW

### Poor Hand Tracking
- Ensure adequate lighting (natural or artificial)
- Position yourself so hands are clearly visible
- Avoid moving too quickly
- Remove cluttered backgrounds

### Performance Issues
- Reduce camera resolution in the source code
- Disable visual effects (motion trails, parameter bars)
- Close background applications

---

## Stopping the Application

Press the **"Stop Controller"** button or press **'Q'** in the camera window to exit.

---

## Support

For issues or feature requests, please refer to the project repository or contact the development team.

---

*Last Updated: June 2026*
