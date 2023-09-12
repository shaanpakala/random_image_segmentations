# "Abstract"
These are just some random image segmentations I've done, mainly for practice.

# Models
Started off by trying a simple encoder -> decoder network which yielded okay results.

Then went to implementing a UNet using encoders and decoders with skip connections, which yielded much better results.
- Encoder was 2 Conv2D layers with ReLU activation, followed by a MaxPooling layer for downsizing.
- Decoder was similarly 2 Conv2D layers with ReLU activation, but followed by a ConvTranspose2D layer for upsizing.
    - I also tried upsampling for the decoder but this seemed to not produce as good results for me.
- Lastly, there was class predictions block which was two Conv2D layers, outputing the same number of channels as classes I wanted to predict.
    - Outchannels was 1 for Cell and People segmentation, 2 for Bears/Deers segmentation.

# Bears/Deers segmentation
This one was me starting from scratch, finding pictures of bears and deers online and filling in the masks myself. This means the train set was not as big as I would like though.

# Cell Segmenation
This dataset I was able to find online, so the train set was pretty decent and I achieved the best results here. Also I got good results here since cells are just circles and pretty easily distinguishable.

# People Segmentation
This dataset I was also able to find online, and got some promising results.

# Highlights
