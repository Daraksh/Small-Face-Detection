# Small-Face-Detection
## Getting Started

- Install dependencies with `pip install -r requirements.txt`.

## Data
- data should follow WIDERFace database directory for training

```
- data
    - WIDER
        - README.md
        - wider_face_split
        - WIDER_train
        - WIDER_val
        - WIDER_test
```

## For Inference the image folder can be placed directly in this location 

/data

## Checkpoints

- present in 
/weights

## Final Checkpoint
- present in 

/weights/checkpoint_200.pth

## For Training 

- run this command if you want to resume from a checkpoint 

`python main.py data/WIDER/wider_face_split/wider_new_train.txt data/WIDER/wider_face_split/wider_new_val.txt --dataset-root data/WIDER/WIDER_train --resume weights/checkpoint_90.pth`

## For Inference:
- run the model for single image

`python detect_single_image.py path_to_image --checkpoint weights/checkpoint_100.pth --output_dir path_output_directory`

- run the model for a whole directory of images

`python detect_image_dir.py path_to_image_directory --checkpoint path_to_checkpoint.pth --output_dir path_to_output_directory`


