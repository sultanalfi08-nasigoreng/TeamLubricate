# 🎮 Night Forest Horror Game - FPS with Chasing Creature

A thrilling first-person survival horror game set in a dense, dark forest. Navigate through the endless trees with only your flashlight, while being hunted by a mysterious glowing creature. Can you survive the night?

## 🎯 Features

### 🏞️ Environment
- **Procedurally Generated Forest**: Thousands of uniquely placed trees and bushes
- **Dynamic Lighting**: Realistic flashlight with spotlight effect
- **Atmospheric Fog**: Creates depth and enhances horror atmosphere
- **Night Setting**: Dark environment with minimal ambient light

### 👤 Player Mechanics
- **First-Person Controls**: WASD movement + mouse look
- **Stamina System**: Sprint with Shift key (limited stamina)
- **Flashlight**: Your only source of light in the dark forest
- **Tree Collision**: Realistic obstacle avoidance

### 👹 Horror Elements
- **Chasing Creature**: AI-powered entity that hunts you down
- **Dynamic AI Behavior**:
  - Wanders randomly when player is far
  - Actively chases when player is detected
  - Speed increases as it gets closer
  - Basic obstacle avoidance
- **Jumpscare System**: Full-screen jumpscare when caught
- **Sound Design**:
  - Ambient forest sounds
  - Heartbeat chase music (intensifies as creature approaches)
  - Jumpscare scream sound effect
- **Visual Warnings**: On-screen alerts when creature is nearby

## 🎮 Controls

| Key | Action |
|-----|--------|
| **Click** | Lock/Unlock mouse pointer |
| **W/A/S/D** | Move forward/left/backward/right |
| **Mouse** | Look around |
| **Shift** | Sprint (consumes stamina) |
| **ESC** | Release mouse pointer |

## 🚀 How to Run

### Quick Start
1. **Clone the repository**:
   ```bash
   git clone https://github.com/yourusername/night-forest-horror.git
   ```

2. **Navigate to the project directory**:
   ```bash
   cd night-forest-horror
   ```

3. **Add your sound files**:
   - Place `jumpscare.mp3` in the project root directory
   - *(Optional)* Add custom sound files for ambient and chase music

4. **Open the game**:
   - Simply open `index.html` in your web browser
   - Or use a local server:
     ```bash
     # Using Python
     python -m http.server 8000
     
     # Using Node.js with http-server
     npx http-server
     ```

5. **Play the game**:
   - Click on the game screen to lock mouse pointer
   - Use WASD to move around
   - Keep an eye on your stamina and listen for the creature!

### File Structure
```
night-forest-horror/
├── index.html          # Main game file
├── jumpscare.mp3       # Jumpscare sound effect (required)
├── README.md           # This file
├── ambient.mp3         # Optional: Ambient forest sounds
└── chase.mp3          # Optional: Chase music
```

## 🛠️ Technical Details

### Built With
- **Three.js** (v0.160.0) - 3D graphics library
- **HTML5 Canvas** - Rendering
- **Web Audio API** - Sound management
- **Vanilla JavaScript** - Game logic

### Game Mechanics
- **AI System**: State-based behavior (wander/chase) with distance-based speed scaling
- **Collision Detection**: Circle-based collision for trees and creature
- **Procedural Generation**: Custom algorithm for dense tree placement
- **Performance**: Optimized for 3000+ trees with collision detection

### Sound System
- **jumpscare.mp3**: Local file (required)
- **Ambient/Chase Sounds**: Online sources by default (replaceable with local files)
- **Dynamic Volume**: Chase music volume scales with creature proximity

## 🔧 Customization

### Easy Modifications

1. **Change Game Difficulty**:
   ```javascript
   // In index.html, find these variables:
   chaserSpeed = 3.5;              // Adjust creature speed
   chaserDetectionRange = 40;      // Adjust detection distance
   chaserMinSpeed = 2.0;           // Minimum chase speed
   chaserMaxSpeed = 5.0;           // Maximum chase speed
   ```

2. **Modify Forest Density**:
   ```javascript
   // Adjust number of trees (current: 3000)
   for (let i = 0; i < 3000; i++) {
   ```

3. **Customize Player Stats**:
   ```javascript
   stamina = 100;                   // Starting stamina
   drainRate = 25;                  // Sprint stamina drain
   regenRate = 15;                  // Stamina regeneration
   ```

### Advanced Customization

1. **Replace Creature Model**:
   Modify the `createChaser()` function to use different geometries/materials

2. **Add More Entities**:
   Extend the AI system and add new creature types

3. **Enhance Graphics**:
   - Add particle effects (fog, fireflies)
   - Implement day/night cycle
   - Add weather effects

## 🎨 Art & Assets

### Current Assets
- **3D Models**: Procedurally generated trees and creature
- **Textures**: Basic Three.js materials
- **Sounds**:
  - `jumpscare.mp3` - Local file (required)
  - Ambient sounds - Online source (replaceable)

### Recommended Assets
For best results, consider adding:
- Custom tree textures
- Better creature model
- Footstep sound effects
- More environmental sounds

## 🐛 Known Issues & Limitations

1. **Browser Audio Policies**: Some browsers require user interaction before playing audio
2. **Performance**: Very old computers may experience lag with 3000+ trees
3. **Mobile Support**: Not optimized for touch devices
4. **Save System**: No save/load functionality
5. **Graphics**: Basic lighting and materials

## 🚀 Future Improvements

### Planned Features
- [ ] Multiple creature types
- [ ] Day/night cycle
- [ ] Weapon system (for defense)
- [ ] Objectives/quests
- [ ] More environmental hazards
- [ ] Save/Load system
- [ ] Settings menu (graphics, audio, controls)

### Technical Improvements
- [ ] WebGL shader effects
- [ ] Improved AI pathfinding
- [ ] Procedural terrain generation
- [ ] Better performance optimization
- [ ] Touch/mobile controls

## 🤝 Contributing

Contributions are welcome! Here's how you can help:

1. **Report Bugs**: Open an issue with detailed bug reports
2. **Suggest Features**: Share your ideas for new features
3. **Submit Pull Requests**: 
   - Fork the repository
   - Create your feature branch (`git checkout -b feature/AmazingFeature`)
   - Commit your changes (`git commit -m 'Add some AmazingFeature'`)
   - Push to the branch (`git push origin feature/AmazingFeature`)
   - Open a Pull Request

### Development Setup
```bash
# 1. Fork and clone the repository
# 2. Make your changes
# 3. Test locally by opening index.html
# 4. Submit a pull request
```

## 📝 License

This project is open source and available under the **MIT License**.

## 🙏 Acknowledgments

- **Three.js** community for the amazing 3D library
- **Mixkit** for free sound effects
- **All contributors** who help improve this game

## 📊 Performance Tips

1. **For Low-End PCs**:
   - Reduce tree count in the code
   - Disable antialiasing in renderer settings
   - Lower fog density

2. **For Better Graphics**:
   - Increase tree count for denser forest
   - Add more environmental details
   - Implement post-processing effects

## 🆘 Troubleshooting

### Common Issues

1. **Game doesn't start**:
   - Ensure you're using a modern browser (Chrome, Firefox, Edge)
   - Check browser console for errors (F12)

2. **No sound**:
   - Make sure `jumpscare.mp3` is in the correct directory
   - Check browser audio permissions
   - Click on the game to trigger audio (browser requirement)

3. **Poor performance**:
   - Reduce tree count in the code
   - Close other browser tabs
   - Update your graphics drivers

4. **Controls not working**:
   - Click on the game to lock mouse pointer
   - Check if another element has focus

### Getting Help
If you encounter issues:
1. Check the console for error messages (F12 → Console)
2. Search existing issues
3. Create a new issue with details about:
   - Browser and version
   - Error messages
   - Steps to reproduce

---

**Enjoy the game!** Remember: In the dark forest, you're never alone... 👹

---

*Created with ❤️ by TeamLubricate. Feel free to star the repository if you enjoy the game!*
