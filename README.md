# Video Text Detection Tool (Google Cloud Video Intelligence Api)


This script utilizes the Google Cloud Video Intelligence API to detect text in a video file. The detected text, along with its location, confidence score, and time offset, is saved in a JSON file for further analysis.

> **Note**: Before using this tool, make sure to replace the `GOOGLE_APPLICATION_CREDENTIALS` environment variable with the path to your own Google Cloud Service Account key file (`loyal-vent-356807-b0c9c97dce30.json`) generated from the Google Cloud Console.

## Prerequisites

- Python 3.x installed
- Google Cloud Video Intelligence API enabled
- Google Cloud Service Account key file (JSON) with appropriate permissions

## Installation

1. Clone this repository to your local machine.
2. Install the required Python dependencies using the following command:

```bash
pip install -r requirements.txt
```

## Usage

To detect text in a video file, use the following command in your terminal or command prompt:

```bash
python video_detect_text.py
```

The tool will process the video (`sample_video.mp4`) and generate a JSON file (`text_detection.json`) containing the detected text, its location, confidence score, and time offset.

```python
# Replace these values with your desired video file and output JSON file paths
filename = "sample_video.mp4"
output = "text_detection.json"
video_detect_text(filename, output)
```

Please ensure that you have properly set up the Google Cloud Service Account key file and enabled the necessary APIs in your Google Cloud Console before running the tool.

## Output

After running the tool, the `text_detection.json` file will contain the detected text and its information in the following format:

```json
{
    "text_detection_results": [
        {
            "text": "Hello, World!",
            "start_time": "0.0s",
            "end_time": "2.4s",
            "confidence": 0.876,
            "bounding_box_vertices": [
                {"x": 36.98, "y": 79.8},
                {"x": 69.86, "y": 79.8},
                {"x": 69.86, "y": 93.04},
                {"x": 36.98, "y": 93.04}
            ]
        },
        ...
    ]
}
```

## Bounding Box on Videos

For drawing bounding boxes on the video using the JSON responses from Google Cloud Vision API, you can use the following repository: [draw-bounding-boxes-on-google-cloud-vision-api-response](https://github.com/raoumairwaheed/draw-bounding-boxes-on-google-cloud-vision-api-response). Please follow the instructions in that repository to visualize the detected labels with bounding boxes on your video.

## Reference

For more information about the Google Cloud Video Intelligence API, please visit the [official documentation](https://cloud.google.com/video-intelligence).
