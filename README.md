# Pets Detection And Segmentation Detectron2

## Dataset
The Oxford-IIIT Pet Dataset: https://www.robots.ox.ac.uk/~vgg/data/pets/

## Requirements
(Note: All the notebooks were executed on Google Colabs)
- Detectron2
- numpy==1.17
- pytorch
- opencv
- cocoapi==2.0

## Prepare data
Run all blocks in ```prepare_data.ipynb``` to generate ```train_segmentation.json```, ```test_segmentation.json```, ```train_object_detection.json``` and  ```test_object_detection.json```

## Train models
- Run the first 2 blocks in ```train.ipynb``` to install the required packages (if you use Colabs, you need to restart runtime after installation to update the environment). 
- You need to specify the paths to your image directory, ```train_{segmentation/detection}.json```, ```test_{segmentation/detection}.json``` and register the train and test set
- Pick a model config (```.yaml``` file) in Detectron2's model zoo (use COCOInstanceSegmentation models for segmentation task and COCOObjectDetection for detection task) and set it via ```cfg.merge_from_file()```
- Train the model
## Evaluate models
- Run the first block in ```evaluate.ipynb``` to install the required packages (if you use Colabs, you need to restart runtime after installation to update the environment). 
- Register dataset and set config 
- Load trained weights using ```DefaultTrainer()``` class and resume checkpoint by setting ```trainer.resume_or_load(True)```
- Execute function ```inferrence_on_dataset()``` to get the result
- Run the last block to visualize on images
