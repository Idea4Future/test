
# Spawn Gazebo World

## Download

### Package

After downloading this package file, unzip it and place it under:

```bash
$HOME/{your workspace}/src
```

### Model Files

Please visit the following website and download `models.zip`:

[http://u.uma.es/dr3/datasetcode/](http://u.uma.es/dr3/datasetcode/)

Then, unzip `models.zip` to:

```bash
$HOME/{your workspace}/src/spawn_gazebo/models
```

## Configuration

Open your `.bashrc` file and add the following command:

```bash
export GAZEBO_MODEL_PATH=$HOME/{your workspace}/src/spawn_gazebo/models:$GAZEBO_MODEL_PATH
```

> **Note:** This path should be the actual location where your downloaded `models` folder is placed.

## Build

Navigate to your workspace directory and build using:

```bash
colcon build --symlink-install
```

## Run

Spawn a Gazebo world with the desired environment argument. Supported environments:
- `forest`
- `hill` *(Default)*
- `lake`
- `park`
- `forest_tagged`
- `hill_tagged`
- `lake_tagged`
- `park_tagged`

Launch command:

```bash
ros2 launch spawn_gazebo spawn_gazebo_world.launch.py world_name="{environment name}"
```

### Example:

```bash
ros2 launch spawn_gazebo spawn_gazebo_world.launch.py world_name="hill_tagged"
```

> **Recommended:** For our research, spawning `hill` or `hill_tagged` is recommended.

> **Note:** Loading the world may take some time; please be patient. Specifically, in the `forest` environment, you may initially observe the ground appearing sunken after Gazebo starts. If you wait longer, the ground plane will load correctly, and the environment will function normally.
