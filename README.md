# Project: Object Tracking and Visualization

This repository provides tools for tracking objects in videos and visualizing the tracking results. It consists of two primary modules: `track_saver` for processing videos and saving tracking data, and `visualizer` for rendering the tracking data and manipulating frame-level details.

---

## Project Structure

```
.
├── track_saver
│   ├── input_videos              # Folder for input video files
│   │   └── new_test2.mp4         # Example input video
│   ├── json_output               # Folder for output tracking JSON files
│   │   └── new_test2_modified.json # Example output JSON
│   ├── models                    # YOLO model weights
│   │   ├── best.pt
│   │   ├── best_yt.pt
│   │   └── last.pt
│   ├── save_track.py             # Script for tracking objects and saving data
│   └── visualize_track.py        # Script for visualizing tracking data
└── visualizer
    ├── index.html                # Web-based tracking visualizer
    ├── main.js                   # JavaScript logic for visualization
    ├── output_frames             # Folder for extracted video frames
    │   └── frame_XXXX.png        # Example frame images
    └── frames_generator.py       # Script for extracting frames from videos
```

---

## Features

1. **Object Tracking with ByteTrack and YOLO**:
   - The `save_track.py` script tracks objects in videos using a YOLO model and ByteTrack, saving the results in JSON format.

2. **Interactive Visualization**:
   - The `visualize_track.py` script allows visualizing tracking data on video frames with matplotlib.
   - The `index.html` and `main.js` enable a web-based viewer for interactive exploration of frames and bounding boxes.

3. **Frame Extraction**:
   - The `frames_generator.py` script extracts frames from input videos for further processing.

---

## Requirements

### Python Dependencies
- Python 3.8+
- Required libraries:
  - `ultralytics` (for YOLO model)
  - `supervision` (for ByteTrack)
  - `matplotlib`
  - `opencv-python`

Install them using:
```bash
pip install ultralytics supervision matplotlib opencv-python
```

### Web Dependencies
- A modern web browser for running the visualizer.

---

## Usage

### 1. Tracking Objects
Run the following to track objects in a video and save results:
```bash
cd track_saver
python save_track.py <videoname> <modelname> <outputjson> [device]
```
Example:
```bash
python save_track.py new_test2.mp4 best.pt new_test2_modified.json gpu
```

### 2. Visualizing Tracking Data
```bash
python visualize_track.py <jsonname> <videoname> [confidence_threshold]
```
Example:
```bash
python visualize_track.py new_test2_modified.json new_test2.mp4 0.2
```

### 3. Extracting Frames
```bash
cd visualizer
python frames_generator.py <videoname>
```
Example:
```bash
python frames_generator.py new_test2.mp4
```

### 4. Web-based Visualization
Open `visualizer/index.html` in a browser. Use the controls to explore tracking data and manipulate bounding boxes.

---


## Acknowledgments

- **YOLO**: Object detection framework by Ultralytics.
- **ByteTrack**: Multi-object tracking implementation in the `supervision` library.
- **Matplotlib**: Python library for data visualization.
- **OpenCV**: Video processing and frame extraction.

---

Feel free to open issues or contribute to this repository. Happy tracking and visualizing!

