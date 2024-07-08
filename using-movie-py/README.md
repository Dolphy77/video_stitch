
# Video Stitching with MoviePy

This repository provides a Python script to concatenate two video files without any transitions using the `moviepy` library. The script leverages `moviepy` to load, process, and encode the videos.

## Requirements

- Python 3.x
- `moviepy` library

## Installation

First, ensure you have Python 3.x installed. Then, install the `moviepy` library:

```bash
pip install moviepy
```

## Usage

1. Clone this repository or download the script.

2. Update the script with the paths to your input video files and desired output path.

3. Run the script.

### Example Script

```python
from moviepy.editor import VideoFileClip, concatenate_videoclips

def concatenate_videos(input_video1, input_video2, output_video):
    # Load the video files
    clip1 = VideoFileClip(input_video1)
    clip2 = VideoFileClip(input_video2)

    # Concatenate the videos
    final_clip = concatenate_videoclips([clip1, clip2])

    # Write the output to a file
    final_clip.write_videofile(output_video, codec='libx264', audio_codec='aac')

# Example usage
concatenate_videos('path/to/video1.mp4', 'path/to/video2.mp4', 'path/to/output.mp4')
```

### Running the Script

Save the script as `video_stitch.py` and run it using Python:

```bash
python video_stitch.py
```

### Customization

- **Input Videos**: Update the `input_video1` and `input_video2` variables with the paths to your video files.
- **Output Video**: Set the `output_video` variable to your desired output file path.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
