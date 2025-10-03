# SLAM Navigation Stack — UCR Robotics Project

**TL;DR:** Full SLAM + navigation stack on TurtleBot3 in Gazebo & real-world testbed. Includes mapping, localization, global/local planners, and Nav2 integration.

**Highlights**
- **Mapping:** Gmapping + Cartographer; occupancy grid maps
- **Localization:** AMCL (particle filter) with adaptive resampling
- **Planning:** Global (A*) + Local (DWB, TEB)
- **Control:** Tuned velocity constraints for safe indoor navigation
- **Results (UCR lab):** ~25% map accuracy improvement (Cartographer vs. Gmapping), stable localization over 10m trajectories

## Repo Layout
- `src/` — ROS2 packages/nodes
- `launch/` — bringup & Nav2 launch files
- `config/` — costmap, planner, controller params
- `maps/` — saved maps (YAML + PGM)
- `scripts/` — helper scripts (bag-to-map, teleop logging)
- `media/` — GIF/MP4 demos
- `docs/` — project report, diagrams

## Quick Start
```bash
# Launch sim
ros2 launch slam_nav_tb3 slam_sim.launch.py

# Run Nav2
ros2 launch slam_nav_tb3 nav2.launch.py map:=maps/ucr_lab.yaml
