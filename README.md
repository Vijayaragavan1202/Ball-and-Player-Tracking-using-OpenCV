# Ball-and-Player-Tracking-using-OpenCV


## Overview

This project provides an automated solution for tracking players and the ball in sports videos using a YOLOv11-based object detection model. Each player is assigned a unique ID while visible, and their positions are exported to a CSV file for further analysis. The system also produces an annotated output video with bounding boxes and labels for both players and the ball.

## Features

- **Player and Ball Detection:** Uses YOLOv11 to detect players and the ball in each frame.
- **Consistent Player IDs:** Assigns and maintains unique IDs for each player while they are in view.
- **CSV Export:** Logs player positions (frame, ID, x_center, y_center) for every frame.
- **Annotated Output Video:** Saves a video with visualized bounding boxes and labels.
- **Modular CSV Logger:** Reusable class for easy data export.

## Directory Structure

```
project_root/
├── main_tracking.py
├── csv_utils.py
├── yolov11_players.pt
├── 15sec_input_720p.mp4
├── output_tracking.mp4
└── player_positions.csv
```

## Usage

1. **Requirements**
   - Python 3.x
   - ultralytics
   - opencv-python
   - numpy
   - scikit-learn
   - scipy

   Install dependencies:
   ```
   pip install ultralytics opencv-python numpy scikit-learn scipy
   ```

2. **Setup**
   - Place `csv_utils.py` and your main script (`main_tracking.py` or notebook) in the same directory.
   - Ensure `yolov11_players.pt` (the YOLOv11 model) and your input video are present.

3. **Run the Tracker**
   ```
   python main_tracking.py
   ```
   - The output video will be saved as `output_tracking.mp4`.
   - Player positions will be logged in `player_positions.csv`.

## CSV Output Example

| frame | player_id | x_center | y_center |
|-------|-----------|----------|----------|
|   0   |     0     |   320    |   120    |
|   0   |     1     |   540    |   200    |

## Customization

- Adjust matching parameters (`appearance_weight`, `position_weight`, `similarity_threshold`) in the main script for your dataset.
- The modular CSV logger can be reused for other tracking or analytics projects.

## License

This project is for educational and research purposes.  
Feel free to adapt and extend it for your own use.
