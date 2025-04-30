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

darakshan/ssd/data

## Checkpoints

- present in 
darakshan/ssd/weights

## Final Checkpoint
- present in 

darakshan/ssd/weights/checkpoint_200.pth

- can be downloaded using `https://68dcb5851a57b28e-dot-us-east1.notebooks.googleusercontent.com/files/darakshan/ssd/weights/checkpoint_200.pth?_xsrf=2%7C3f3191c0%7C5b3d1b98821e872df59d5fc2d5698d85%7C1735108375`

## For Training 

- run this command if you want to resume from a checkpoint 

`python main.py data/WIDER/wider_face_split/wider_new_train.txt data/WIDER/wider_face_split/wider_new_val.txt --dataset-root data/WIDER/WIDER_train --resume weights/checkpoint_90.pth`

## For Inference:
- run the model for single image

`python detect_single_image.py path_to_image --checkpoint weights/checkpoint_100.pth --output_dir path_output_directory`

- run the model for a whole directory of images

`python detect_image_dir.py path_to_image_directory --checkpoint path_to_checkpoint.pth --output_dir path_to_output_directory`

## Results are stored in 
darakshan/ssd/Result_200_finalckpt_wider_test_original
darakshan/ssd/Result_200_finalckpt_some_test_images

## comparison of retinaface_aftershoot and our single shot detection model
- inference time:
2 hrs and 45 minutes for test, for aftershoot retinaface
1534.10 seconds = 25.6 minutes, for our single shot detector model
inference time is for WIDER test data. 

- tiny faces

Our model is able to detect tiny faces of around 19x19(smallest recorded was around 11x14) which is much less than 40x40 as deliverable expected

- Number of Faces

The maximum number of faces detected is 511 by our model, while only around 90 for Aftershoot RetinaFace on the world's largest selfie
`darakshan/ssd/worldslargestselfiem.jpg`
