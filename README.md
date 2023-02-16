**Target-aware Dual Adversarial Learning (TarDAL)**

The paper addresses the issue of fusing infrared and visible images that appear differently for object detection. Aiming at generating an image of high visual quality, which preserves structural information of targets from the infrared and textural details from the visible images. detection-oriented fusion.

![Image](https://user-images.githubusercontent.com/117992631/219347521-ee15413c-4f02-4d37-89b1-d2e5c1244ea0.png)

The target discriminator DT is used to distinguish the foreground thermal targets of fused result to the infrared while the detail discriminator DD contributes to distinguish the background details of fused result to the visible.
The annotation folder of dataset has been used to calculate the target mask m from infrared images so that the two discriminators can perform on their respective regions (target and background).
The generator contributes to generate a fused image that preserves overall structures and maintains a similar intensity distribution as source images



![Image](https://user-images.githubusercontent.com/117992631/219347606-0c04c785-154e-440e-8407-d5df4a7a95d6.png)

**Parameter Settings**
I performed evaluations on M3FD dataset which contains 4200 aligned and registered pairs.
1000 images are selected and used random cropping for training the fusion task. The tuning parameters of the losses of generator and discriminators α and β are set to 20 and 0.1, respectively. The Adam optimizer updates the network parameters with the learning rate of 1.0 × 10−4 . The epoch is set to 100 with batch size of 32

**Generator and discriminator architecture**
The two discriminators DT and DD share the same network structur.
![image](https://user-images.githubusercontent.com/117992631/219350441-a0b210e4-ebc0-4b7e-9080-ec5e6fc72b87.png)

**Generated images**

![image](https://user-images.githubusercontent.com/117992631/219350518-8c610d84-c94a-44c8-843e-17dc696cf3c5.png)

**Object detection using YOLO**

![image](https://user-images.githubusercontent.com/117992631/219350625-86c92480-3673-46fa-8a93-f897b70bf884.png)

