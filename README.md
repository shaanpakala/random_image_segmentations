# "Abstract"
These are just some random image segmentations I've done, mainly for practice.

# Preprocessing
As far as preprocessing, I experimented with several methods, the main one was kmeans clustering to further distinguish the colors in the images.

# Models
Started off by trying a simple encoder decoder network which yielded okay results.

Then went to implementing a UNet using encoders and decoders with skip connections, which yielded much better results.
- Encoder was 2 Conv2D layers with ReLU activation, followed by a MaxPooling layer for downsizing.
- Decoder was similarly 2 Conv2D layers with ReLU activation, but followed by a ConvTranspose2D layer for upsizing.
    - I also tried upsampling for the decoder but this seemed to not produce as good results for me.
- Lastly, there was class predictions block which was two Conv2D layers, outputing the same number of channels as classes I wanted to predict.
    - Outchannels was 1 for Cell and People segmentation, 2 for Bears/Deers segmentation.
 
# Postprocessing
For postprocessing (of the predicted mask) I experimented with some blurring, which seemed to help in most cases (to eliminate some random specs on the predicted mask).
I also tried different threshholds, where anything under the threshhold was eliminated and anything over was set to 255 (maximum brightness) in order to highlight the predicted masks and eliminate random specs again. 

# People Segmentation
This dataset I was also able to find online, and got some promising results.

# Cell Segmenation
This dataset I was able to find online, so the train set was pretty decent and I achieved the best results here. Also I got good results here since cells are just circles and pretty easily distinguishable.

# Bears/Deers segmentation
This one was me starting from scratch, finding pictures of bears and deers online and filling in the masks myself. This means the train set was not as big as I would like though. I still got some decent results for the size of the train set, I thought.

# Some Test Images and Segmentations

![Screen Shot 2023-09-12 at 11 08 51 AM](https://github.com/shaanpakala/random_image_segmentations/assets/68576257/e590927a-3ebc-4c8b-ad8d-6d5336a8a994)


![Screen Shot 2023-09-12 at 11 07 02 AM](https://github.com/shaanpakala/random_image_segmentations/assets/68576257/645358cd-f45b-4bc3-9717-9d5dafa29f47)


<img width="1199" alt="Screen Shot 2023-09-21 at 2 14 39 PM" src="https://github.com/shaanpakala/random_image_segmentations/assets/68576257/d807c5c5-1203-4566-a5e0-0ebe7aad8e1d">

<img width="1194" alt="Screen Shot 2023-09-21 at 2 15 26 PM" src="https://github.com/shaanpakala/random_image_segmentations/assets/68576257/2ef63b72-0531-47ec-ad1c-954fbf279aa1">


