## Target-aware Dual Adversarial Learning (TarDAL)

The paper addresses the issue of fusing infrared and visible images that appear differently for object detection. Aiming at generating an image of high visual quality, which preserves structural information of targets from the infrared and textural details from the visible images. detection-oriented fusion.

![Image](https://user-images.githubusercontent.com/117992631/219347521-ee15413c-4f02-4d37-89b1-d2e5c1244ea0.png)

<hr/>

The target discriminator DT is used to distinguish the foreground thermal targets of fused result to the infrared while the detail discriminator DD contributes to distinguish the background details of fused result to the visible.
The annotation folder of dataset has been used to calculate the target mask m from infrared images so that the two discriminators can perform on their respective regions (target and background).
The generator contributes to generate a fused image that preserves overall structures and maintains a similar intensity distribution as source images

![Image](https://user-images.githubusercontent.com/117992631/219347606-0c04c785-154e-440e-8407-d5df4a7a95d6.png)

## Parameter Settings
I performed evaluations on M3FD dataset which contains 4200 aligned and registered pairs.
1000 images are selected and used random cropping for training the fusion task. The tuning parameters of the losses of generator and discriminators α and β are set to 20 and 0.1, respectively. The Adam optimizer updates the network parameters with the learning rate of 1.0 × 10−4 . The epoch is set to 100 with batch size of 32

<hr/>

## Benchmark
M3FD: 4200 aligned and registered 1024×768 pairs
![Preview](https://user-images.githubusercontent.com/117992631/219354975-3b70dfa2-87d0-4122-a674-5264af02de87.gif)


<hr/>

## Generator and discriminator architecture

The two discriminators DT and DD share the same network structur.
![image](https://user-images.githubusercontent.com/117992631/219350441-a0b210e4-ebc0-4b7e-9080-ec5e6fc72b87.png)

<hr/>

## Plot losses

L f = LSSIM + αLpixel + βL adv f

where LSSIM denotes structure similarity loss. To balance the pixel intensity distribution of source images, they introduce a pixel loss based on the saliency degree weight (SDW). The adversarial loss functions of these discriminators calculate the Wasserstein divergence to mutually identify whether the foreground thermal targets and background texture details are realistic

![image](https://user-images.githubusercontent.com/117992631/219351625-0e20f36c-92c1-49be-8f09-5e7a82c6963a.png)

<hr/>

## Generated images

![image](https://user-images.githubusercontent.com/117992631/219350518-8c610d84-c94a-44c8-843e-17dc696cf3c5.png)

<hr/>

## Object detection using YOLO

![image](https://user-images.githubusercontent.com/117992631/219350625-86c92480-3673-46fa-8a93-f897b70bf884.png)

