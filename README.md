# Splat Destroy using spark.js

An interactive 3D experience using Gaussian Splatting with real-time physics. Click on splats to create explosions with customizable radius.

## Features

- Click on splats to trigger radius-based explosions
- Real-time physics simulation (gravity, bounce, friction)
- Adjustable explosion strength, radius and gravity via GUI
- Support for up to 128 simultaneous explosions
- Reset button to restore original state

## Usage

1. Move mouse to look around
2. Click on splats to create explosions
3. Use the GUI panel to adjust parameters
4. Click "Reset Splat" to restore the scene

## Tech Stack

- Three.js
- Spark (@sparkjsdev/spark)
- lil-gui for controls

## Local Setup

```bash
git clone https://github.com/kali-shade/spark-splat-destroy.git
cd spark-splat-destroy
# Serve with any HTTP server
python -m http.server 8000
# Open http://localhost:8000
```

## License

Open source project.
