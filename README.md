# Pitch-The-Future
This is an implementation of two generative models. It contains implementations of the following:
* Autoregressive Models: PixelCNN
* Normalized Flows: Generative Flow (Glow)



The code is ready to train the models using shapes, colored shapes, MNIST, and colored MNIST. Instructions on how to add new datasets can be found in datasets/datasets.py
Models can also be easily added, see instructions in main.py

## How to use
* Create a [Neptune](https://neptune.ai/") account, create a project and use the API token of your project in the API_TOKEN key in the appropriate config file in the configs folder
* Run the command <code> python main.py --configs ./configs/model_name/dataset_name.yaml</code>
* You can find the config details of each dataset and logging settings in the yaml files
* You will find the training results, generated samples, and others on neptune (make sure that log_neptune is set to True in the yaml file)

## Model tests
The models are tested for their ability to classify anomalies.
By flipping a percentage of the 1-bit pixels in images of shapes , the model should be able to classify these images as corrupted.
Here's a sample of images and their corrupted counterparts:<br />
![This is an image](/assets/images/original.png)<br />
![This is an image](/assets/images/corrupted.png)


The following is the ROC curve when 0.05 of the pixels were flipped in the corrupted images.
![This is an image](/assets/images/ROC0.05.png)