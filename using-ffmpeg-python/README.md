
# Video Stitching

This repository provides a Python script to concatenate two video files without any transitions using the `ffmpeg-python` library. The script leverages FFmpeg to decode, process, and encode the videos.

## Requirements

- Python 3.x
- `ffmpeg-python` library
- FFmpeg installed on your system

## Installation

First, ensure you have Python 3.x installed. Then, install the `ffmpeg-python` library:

```bash
pip install ffmpeg-python
```

You also need to have FFmpeg installed on your system. You can download it from the [official FFmpeg website](https://ffmpeg.org/download.html) and follow the installation instructions for your operating system.

## Usage

1. Clone this repository or download the script.

2. Update the script with the paths to your input video files and desired output path.

3. Run the script.

### Example Script

```python
import ffmpeg

def concatenate_videos(input_video1, input_video2, output_video):
    try:
        # Create the FFmpeg input streams
        input1 = ffmpeg.input(input_video1)
        input2 = ffmpeg.input(input_video2)

        # Run FFmpeg to concatenate videos without transitions
        (
            ffmpeg
            .concat(input1, input2, v=1, a=1)
            .output(output_video, vcodec='libx264', acodec='aac')
            .run()
        )

        print("Video processing completed. Output saved at:", output_video)
    except ffmpeg.Error as e:
        print('Error:', e.stderr.decode())

# Example usage
concatenate_videos('path/to/video1.mp4', 'path/to/video2.mp4', 'path/to/output.mp4')
```

### Running the Script

Ensure FFmpeg is installed and accessible from your PATH. Save the script as `video_stitch.py` and run it using Python:

```bash
python video_stitch.py
```

### Customization

- **Input Videos**: Update the `input_video1` and `input_video2` variables with the paths to your video files.
- **Output Video**: Set the `output_video` variable to your desired output file path.

## License

This project is licensed under the MIT License - see the [LICENSE](LICENSE) file for details.
