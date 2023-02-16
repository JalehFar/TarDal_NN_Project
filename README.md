**Target-aware Dual Adversarial Learning (TarDAL)**

The paper addresses the issue of fusing infrared and visible images that appear differently for object detection. Aiming at generating an image of high visual quality, which preserves structural information of targets from the infrared and textural details from the visible images. detection-oriented fusion.

![Image](https://user-images.githubusercontent.com/117992631/219347521-ee15413c-4f02-4d37-89b1-d2e5c1244ea0.png)

The target discriminator DT is used to distinguish the foreground thermal targets of fused result to the infrared while the detail discriminator DD contributes to distinguish the background details of fused result to the visible.
The annotation folder of dataset has been used to calculate the target mask m from infrared images so that the two discriminators can perform on their respective regions (target and background).
The generator contributes to generate a fused image that preserves overall structures and maintains a similar intensity distribution as source images



![Image](https://user-images.githubusercontent.com/117992631/219347606-0c04c785-154e-440e-8407-d5df4a7a95d6.png)
