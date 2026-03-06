# 🧺 3D Washing Machine Diagnostic Dashboard

A modern, interactive web application that simulates a 3D washing machine with a real-time diagnostic dashboard. Built with Three.js for 3D visualization and vanilla JavaScript for logic.

## ✨ Features

### 🎨 3D Visualization
- **Realistic Washing Machine Model**: Complete with body, drum, door, and control panel
- **Animated Drum**: Rotates based on motor RPM during wash and spin cycles
- **Dynamic Water Level**: Blue transparent sphere that grows/shrinks during the cycle
- **Door Lock Indicator**: LED changes color (red/green) based on lock status
- **Subtle Vibrations**: Machine subtly vibrates during operation for realism

### 🎛️ Control Panel
- **6 Wash Programs**:
  - Cotton (120s demo)
  - Quick Wash (30s demo)
  - Delicate (60s demo)
  - Single Spin (15s demo)
  - Silk (45s demo)
  - Down (90s demo)

- **Variable Settings**:
  - Temperature: 40°C or 60°C
  - Spin Speed: 800 or 1200 RPM

### 📊 Diagnostic Dashboard
Real-time monitoring of internal systems:

| System | Metrics |
|--------|---------|
| ⚡ Motor | Status (Off/Running) + Live RPM |
| 💧 Water Inlet Valve | Open/Closed Status |
| 🌀 Drain Pump | Active/Idle Status |
| 🔥 Heater | On/Off + Current Temperature |
| 🔒 Door Lock | Locked/Unlocked + LED Indicator |
| 📊 Cycle Progress | Visual Progress Bar (0-100%) |

### 🔄 Cycle Phases
The washing machine sequences through realistic phases:
1. **Fill** - Water inlet opens, drum fills
2. **Heat** - Heater activates to reach target temperature
3. **Wash** - Drum rotates, clothes tumble
4. **Drain** - Pump removes water
5. **Rinse** - Fresh water added and drained
6. **Spin** - High-speed rotation to extract water
7. **Done** - Cycle complete message displayed

## 🚀 Quick Start

### Option 1: Direct Download
1. Save the `washing-machine-dashboard.html` file to your computer
2. Open it in any modern web browser (Chrome, Firefox, Edge, Safari)
3. That's it! No server required.

### Option 2: Local Server (Optional)
```bash
# Using Python
python -m http.server 8000

# Using Node.js
npx serve .

# Then open http://localhost:8000/washing-machine-dashboard.html
```

## 🎮 How to Use

1. **Select a Program**: Click one of the 6 program buttons (Cotton, Quick Wash, etc.)
2. **Adjust Variables** (optional): Choose temperature and spin speed
3. **Start Cycle**: Click the large START button
4. **Watch & Monitor**: Observe the 3D animation and diagnostic data
5. **Stop Early** (optional): Click STOP to halt the cycle
6. **Completion**: Wait for "Cycle Complete!" message

## 🏗️ Technical Architecture

### File Structure
```
washing-machine-dashboard/
├── washing-machine-dashboard.html  # Main application (all-in-one)
└── README.md                        # This file
```

### Technologies Used
- **Three.js r128**: 3D rendering engine
- **HTML5**: Semantic structure
- **CSS3**: Modern styling with gradients, animations, and flexbox
- **Vanilla JavaScript**: ES6+ features, no frameworks needed

### Key Components

#### 3D Scene (`Three.js`)
- Scene, Camera, Renderer
- Lighting (Ambient + Directional + Point)
- Meshes: Body, Drum, Door, Water, Lock LED, Feet
- Materials: Phong materials with transparency and shininess

#### State Machine
```
States: Ready → Fill → Heat → Wash → Drain → Rinse → Spin → Done
```

#### Update Loop
- **Animation Frame**: 60 FPS for smooth 3D rendering
- **Diagnostic Updates**: Every 500ms for live data simulation
- **Phase Logic**: Time-based progression through cycle

## 🎨 Design Highlights

### Color Scheme
- **Primary**: Cyan (#00ffff) - Futuristic accent
- **Secondary**: Neon Green (#00ff88) - Active states
- **Background**: Dark Blue Gradient (#1a1a2e → #16213e)
- **Alerts**: Red (#ff4444) - Inactive/Error states

### UI Effects
- Glass morphism backdrop blur
- Neon glow text shadows
- Smooth hover transitions
- Pulsing completion message
- Custom scrollbar styling

## 🔧 Customization

### Adjust Cycle Duration
Modify the `programs` object in the JavaScript:
```javascript
const programs = {
    cotton: { duration: 120, phases: [...] },  // Change 120 to desired seconds
    // ...
};
```

### Change Colors
Update CSS variables or directly modify color values in the `<style>` section.

### Add More Programs
Extend the `programs` object with new phase sequences:
```javascript
eco: { duration: 180, phases: ['Fill', 'Heat', 'Wash', 'Rinse', 'Spin', 'Done'] }
```

## 📱 Browser Compatibility

| Browser | Version | Status |
|---------|---------|--------|
| Chrome | 80+ | ✅ Full Support |
| Firefox | 75+ | ✅ Full Support |
| Safari | 13+ | ✅ Full Support |
| Edge | 80+ | ✅ Full Support |
| Opera | 65+ | ✅ Full Support |

**Note**: Requires WebGL support for 3D rendering.

## 🐛 Troubleshooting

### 3D Scene Not Loading
- Ensure JavaScript is enabled in your browser
- Check browser console for errors (F12)
- Verify internet connection (Three.js loads from CDN)

### Controls Not Responding
- Make sure you're not in an active cycle (variables locked during operation)
- Try refreshing the page

### Performance Issues
- Close other browser tabs
- Update graphics drivers
- Reduce browser zoom level

## 📝 Code Structure Overview

```html
<!DOCTYPE html>
<html>
<head>
    <style>/* ~250 lines of CSS */</style>
</head>
<body>
    <div class="container">
        <div id="canvas-container"></div>  <!-- 3D Scene -->
        <div id="ui-panel">...</div>        <!-- Control Panel -->
    </div>
    
    <script src="three.js-cdn"></script>
    <script>
        // Three.js Setup (~150 lines)
        // Application State (~30 lines)
        // UI Event Handlers (~80 lines)
        // Diagnostic Updates (~60 lines)
        // Phase Logic (~50 lines)
        // Animation Loop (~30 lines)
    </script>
</body>
</html>
```

## 🎯 Future Enhancements

Potential features for future versions:
- [ ] Sound effects for different phases
- [ ] Cloth particles inside the drum
- [ ] Error code simulation
- [ ] Energy/water consumption tracking
- [ ] Multiple language support
- [ ] Mobile-responsive layout
- [ ] Save custom programs
- [ ] Historical cycle data

## 📄 License

This project is provided as-is for educational and demonstration purposes. Feel free to use, modify, and distribute.

## 🙏 Acknowledgments

- Three.js community for the excellent 3D library
- Modern CSS techniques inspiration from various UI designers

---

**Created with ❤️ by Your Frontend Developer**

*Last Updated: 2024*
