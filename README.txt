# Robot Control System

A Python-based control system for the **Marty robot**, developed as a collaborative robotics project.

This repository brings together several modules for:
- manual robot control through a graphical interface,
- movement execution at different granularities,
- path recording and replay preparation,
- obstacle and distance sensing,
- color detection and color-based reactions,
- emotion and LED-based robot expressions,
- scripted dance / movement execution from external files.

## Project Overview

The goal of this project was to design a modular control environment for a Marty robot, combining:
- **robot motion control**,
- **sensor-based interaction**,
- **human-robot interface design**,
- **movement scripting and replay**,
- **emotion-based feedback**.

The project was developed collaboratively using multiple Git branches, each contributor focusing on a different subsystem before integration.

## Main Features

### 1. Robot connection
The robot is controlled through the `martypy` library over Wi-Fi.

Typical workflow:
- connect to Marty using its IP address,
- send movement commands,
- read sensors,
- trigger visual / emotional feedback.

### 2. Manual movement control
The project supports:
- **single-step movements**
- **grid / cell-based movements**

Examples:
- forward / backward
- left / right sidestep
- stand straight reset

This makes the robot easier to control both for free movement and structured navigation.

### 3. Graphical control interface
A GUI was developed to provide a more user-friendly control panel.

Depending on the branch / version, the interface includes:
- directional buttons,
- robot connection by IP,
- battery level display,
- color calibration,
- action launching from buttons.

### 4. Path recording
The robot’s movements can be saved in a compact format inside `mouvement_path.txt`.

Successive identical moves are compressed into codes such as:
- `F` = forward
- `B` = backward
- `L` = left
- `R` = right

This makes it easier to:
- store movement histories,
- replay or transform movement sequences,
- prepare dance / navigation scripts.

### 5. Sensor-based interaction
Several scripts explore robot sensing capabilities:
- obstacle detection,
- distance reading,
- battery monitoring.

These components are useful for making movement safer and more autonomous.

### 6. Color-emotion interaction
A color-based reaction system was explored:
- detect a color from the robot sensor,
- map the color to an emotion,
- trigger robot feedback such as eye expressions or LED color changes.

This adds a simple human-robot interaction layer to the project.

### 7. Dance / scripted execution
The project also includes scripts that read movement instructions from external files and execute them as robot sequences.

This was used to explore:
- path following,
- choreography execution,
- movement scripting.

## Branch Contributions

### `initDylan`
Main focus:
- robot connection,
- low-level movement commands,
- basic GUI control,
- movement recording.

Notable files:
- `connection.py`
- `deplacement.py`
- `interface.py`
- `saveMouvement.py`
- `capteur_obstacle.py`

### `initCyrille`
Main focus:
- richer GUI,
- IP-based connection,
- battery display,
- color calibration,
- emotion reaction,
- obstacle / distance sensing,
- dance-file execution.

Notable files:
- `interface_test.py`
- `get_distance.py`
- `get_obstacle.py`
- `writeinfeels.py`
- `lecture_feels.py`
- `lecturedance.py`

### `initTaha`
Main focus:
- file-driven motion logic,
- path-following interpretation,
- robot emotion expressions,
- dance / sequence support.

Notable files:
- `followFile.py`
- `emotions.py`
- `lectureDance.py`
- `saveMouvement.py`

## Tech Stack

- **Python**
- **MartyPy**
- **PyQt6**
- File-based movement scripting

## Current Strengths

- Modular robotics project
- Team-based development with branches
- Combination of control, sensing, GUI, and interaction
- Good foundation for extending toward more autonomous behaviors

## Possible Improvements

- unify file naming conventions,
- centralize robot configuration (IP, constants, settings),
- remove hard-coded values from scripts,
- merge duplicated utilities,
- structure the project into folders (`gui/`, `control/`, `sensors/`, `scripts/`, `utils/`),
- add installation instructions and dependency list,
- document expected input file formats for `.dance` / path files,
- add screenshots or a short demo video.

## Repository Structure (recommended future layout)

```text
robot-control-system/
├── gui/
├── control/
├── sensors/
├── emotions/
├── scripts/
├── data/
├── README.md
└── requirements.txt
