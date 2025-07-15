# 3D Video Depth and Anaglyph Processing

## Overview

This project processes standard videos to generate:
- **Depth map videos** using state-of-the-art deep learning models.
- **3D anaglyph (red-cyan) videos** viewable with red-cyan glasses for a stereo 3D effect.

It leverages deep learning (MiDaS), computer vision (OpenCV), and visualization tools (matplotlib) in Python, optimized for use in Google Colab or any Python 3.7+ environment.

## Features

- **Depth Estimation:** Leverages MiDaS deep learning models for per-frame depth estimation.
- **3D Anaglyph Creation:** Creates red-cyan anaglyph visuals combining RGB frames with depth data.
- **Batch Video Processing:** Efficient frame batching with progress indicators.
- **Downloadable Results:** Processed videos are easily downloadable.
- **Preview Frames:** Inline visualization of sample frames and depth maps.

## Demo Output

- `depth_output.mp4`: Grayscale video where brightness indicates depth.
- `anaglyph_output.mp4`: 3D anaglyph video (use red-cyan glasses to view).

## Setup

### Prerequisites

- Python 3.7 or higher
- (Recommended) Google Colab with GPU

**Install dependencies:**

!pip install opencv-python-headless torch torchvision timm matplotlib tqdm pillow


## Usage

### 1. Upload Video
Upload your video file when prompted in the Colab or Jupyter Notebook environment.

### 2. Run the Processing Script

The primary script (`3d_video.py`) does the following:
- Loads and preprocesses video frames (color correction, denoising)
- Estimates depth for each frame via MiDaS
- Exports two MP4 videos:
  - Grayscale depth map video
  - 3D red-cyan anaglyph video

### 3. Download Results

After processing, download links will appear in the notebook output.

## Key Functions

| Function                        | Description                                       |
|----------------------------------|---------------------------------------------------|
| `preprocess_frame()`             | Color correction and denoising                     |
| `estimate_depth()`               | Runs MiDaS model for depth inference              |
| `create_depth_video()`           | Generates grayscale depth-mapped video             |
| `create_anaglyph_frame()`        | Produces 3D anaglyph frame from depth and RGB      |
| `process_video_to_anaglyph()`    | Full video processing pipeline for 3D effect       |


## Customization

- **3D Effect Strength:** Adjust `strength` in `create_anaglyph_frame`.
- **Frame Skipping:** Set `frame_step` for performance vs. output quality.
- **Max Video Length:** Modify `max_frames` as needed.

## References

- [MiDaS: Robust Monocular Depth Estimation](https://github.com/isl-org/MiDaS)
- [OpenCV Documentation](https://opencv.org/)
- [PyTorch Documentation](https://pytorch.org/)

## Credits

Developed as a final year B.E. project.

If you use or adapt this code, consider citing or starring the GitHub repository!


