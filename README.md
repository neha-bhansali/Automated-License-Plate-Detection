## Automated License Plate Detection:

Automated License Plate Detection with AI and deep learning technologies is used to identify license plates, especially in real-time systems. This has numerous uses. Some of these are as follows
- Helps in controlling traffic
- Helps in Parking Lots

### Block 1 :

* We have read and passed images to the model, and images are labeled in a proper way.
* Dataset for vehicle detection Classes - car, truck, bus, bike, van
* Dataset for License plate Detection Classes - License

### Block 2 :

CNN Architecture & components:

An input layer, an output layer, and multiple hidden layers make up convolutional networks. The neurons in the layers of a convolutional network are arranged in three dimensions, unlike those in a standard neural network (width, height, and depth measurements). This enables the CNN to convert a three-dimensional input volume into an output volume. Convolution, pooling, normalizing, and fully connected layers make up the hidden layers. Multiple Conv layers are used in CNNs to filter input volumes to higher levels of abstraction.

### Block 3 :

Dataset Collections -

* We got an annotated dataset for License Plate Detection
* For Vehicle Detection we Mixed a bit of the dataset we found and annotated it with another annotated dataset for the best results
* In that dataset, we divided the photos in a ratio of 1:4 for testing and training respectively.

### Block 4 :

* Then we, trained the model using code - `!python model_main_tf2.py --model_dir=models/my_ssd_mobilenet_v1_fpn --pipeline_config_path=models/my_ssd_mobilenet_v1_fpn/pipeline.config`
* Later, we exported the model using code - `!python exporter_main_v2.py --input_type image_tensor --pipeline_config_path ./models/my_ssd_mobilenet_v1_fpn/pipeline.config --trained_checkpoint_dir ./models/my_ssd_mobilenet_v1_fpn/ --output_directory ./exported-models/my_model`
* And then we performed Inference and plotted the image using the code
<details><summary> Code: </Summary>
![image](https://user-images.githubusercontent.com/78554453/233795915-88f0d65b-7b25-453c-8b35-b72a33a403a7.png)
![image](https://user-images.githubusercontent.com/78554453/233795924-1b58f026-0081-48f3-b2c0-142cf6749be9.png)
</details>

* Its results are:


![image](https://user-images.githubusercontent.com/78554453/233795817-965ba540-4f36-4751-b9a0-e3fd47654bc7.png)
![image](https://user-images.githubusercontent.com/78554453/233795832-92c2f1b7-4f3b-4ae8-9650-aba934ff7dfe.png)
![image](https://user-images.githubusercontent.com/78554453/233795846-24ec6134-9504-4969-8bf7-51d45c24f000.png)

### Block 5 :

* Evaluated the model using the code : `!python model_main_tf2.py --model_dir=models/my_ssd_mobilenet_v1_fpn --pipeline_config_path=models/my_ssd_mobilenet_v1_fpn/pipeline.config --checkpoint_dir=models/my_ssd_mobilenet_v1_fpn`
* Its results are as follows :
For vehicle detection:


![image](https://user-images.githubusercontent.com/78554453/233795951-ed44a682-9eed-4ae0-84b3-e38ef4c95f1c.png)
![image](https://user-images.githubusercontent.com/78554453/233795967-ec4ada54-bbe2-4d89-9fb4-200663153691.png)

For License Plate Detection:

![image](https://user-images.githubusercontent.com/78554453/233795978-c1e88b9a-77b1-45ac-8755-e6899242543a.png)
![image](https://user-images.githubusercontent.com/78554453/233795989-b52479de-8b34-4a4d-a351-8ac09a435630.png)

Colab Links For
* Vehicle Detection: https://colab.research.google.com/drive/15IKu0kxf9jIXRXDUNiP8NOS_JTCoCS97?usp=sharing
* License Plate Detection: https://colab.research.google.com/drive/1_wlN7_oRfQ3XcFyPwrtFCqwrx4CK7QgO?usp=sharing
* Combined : https://colab.research.google.com/drive/1zmEHT_-oShxsFsCq-SXWpxY3qScvovLb?usp=sharing

Dataset Link: https://drive.google.com/drive/folders/1IrXJXYvWMO9EdjUcEPel6p20fVvpD_i3?usp=sharing
