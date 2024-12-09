# :guardsman: Mask Generator

A Python script for automatic mask generation from video frames, leveraging Meta AI’s **Segment Anything** model. This notebook enables:

- :movie_camera: Frame extraction from videos.
- :art: Application of segmentation masks.
- :floppy_disk: Export of masks in **Run-Length Encoding (RLE)** format.

## :star2: Features

- :robot: Loads the **Segment Anything** model and its pre-trained weights.
- :framed_picture: Automatically generates masks for each video frame.
- :file_cabinet: Encodes masks in **RLE (Run-Length Encoding)** format.
- :bar_chart: Visualizes segmented masks directly in the notebook.

## :wrench: Requirements

- **Python Libraries**:  
  `segment-anything`, `opencv-python`, `torch`, `matplotlib`, `supervision`, `jupyter_bbox_widget`, `dataclasses-json`
  
- **Hardware**: :desktop_computer: A **GPU** is recommended for optimal performance.  
  
- **Model Weights**: :arrow_down: Download the weights [here](https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth).

## :clipboard: Installation

1. **Clone the repository**:

    ```bash
    git clone https://github.com/your-repo/maskGenerator.git
    cd maskGenerator
    ```

2. **Install the required dependencies**:

    ```bash
    pip install -r requirements.txt
    ```

3. **Download the model weights**:

    ```bash
    mkdir weights
    wget https://dl.fbaipublicfiles.com/segment_anything/sam_vit_h_4b8939.pth -P weights/
    ```

## :rocket: Usage

1. **Prepare your video**: :video_camera: Place your video file in the `data/videoTest` directory.

2. **Run the notebook**:
    - :notebook_with_decorative_cover: Open the `maskGenerator.ipynb` file.
    - :sparkles: Execute the cells in sequence.

3. **Results**:
    - The generated masks are saved in **RLE format** in the `encodingRLE.txt` file.
    - Segmented frames can be visualized directly within the notebook.

## :movie_camera: Examples

### Segmenting a Specific Frame

You can choose a specific video frame (based on a timestamp) and run the segmentation. For example:

```python
minutes = 0
seconds = 15.25
frame_id = int(fps * (minutes * 60 + seconds))
cap.set(cv2.CAP_PROP_POS_FRAMES, frame_id)
ret, frame = cap.read()
sam_result = mask_generator.generate(frame)
```


## Visualizing Mask
The notebook includes a function to display the mask contours and their IDs directly on the frame:
```python
show_masks_with_ids(frame, sam_result)
```
## :memo:Contributions
Contributions and suggestions are welcome! Feel free to open an Issue or submit a Pull Request.

## :file_cabinet:License
This project is distributed under the MIT License. See the LICENSE file for more details.
