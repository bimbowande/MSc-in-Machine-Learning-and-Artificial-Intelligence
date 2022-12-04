# U-Net: Architecture - II

The output from the encoder is fed into the decoder via the bottleneck. These sections will use the feature maps provided by the encoder to upscale and generate the final segmentation masks for the image. Let’s hear more about these elements in the upcoming video.

**VIDEO**

### Bottleneck

This layer acts as a bridge between the encoder and the decoder. It is a simple convolutional layer that generates more feature maps. However, there is no pooling layer to follow. As a result, you can see that the output now holds 1024 feature maps and the dimensions have reduced due to the convolutional layers.

### Decoder/Expansion  

This phase is responsible for mapping each pixel with a class, that is, the generation of the pixel map. In the process, the decoder also upsamples the output from the bottleneck to match the dimensions of the input image. 

- The bottom of the architecture shows that the expansion starts with a feature map of size 28 x 28. As the first step, this block is **upsampled** to size 56 x 56. You will learn about the upsampling techniques in the future segment. However, the depth decreases from 1024 to 512 feature maps.   
   
- The upsampled output is combined with the output of the encoder phase at the same level through the **skip connection** which results in a feature map of size 56 x 56 x 1024. This process helps in reconstructing the image as concatenation will help in preserving the information at that level.   
   
- The concatenated set of 1024 filters is then passed through 2 convolutional layers which reduce the depth to 512 feature maps.

The above process is repeated till you have an equivalent number of feature maps on both sides (encoder and decoder). The table below summarises the operations for the example used in the segment.

| Level | Input           | Output          |
| ----- | --------------- | --------------- |
| 1     | 28 x 28 x 1024  | 52 x 52 x 512   |
| 2     | 52 x 52 x 512   | 100 x 100 x 256 |
| 3     | 100 x 100 x 256 | 196 x 196 x 128 |
| 4     | 196 x 196 x 128 | 388 x 388 x 64  |

Notice that in this example, the encoder layer and decoder layer are of different sizes. However, you can tune the convolution parameters to result in the same height and width across the phases.

- Lastly, the process is followed by a 1 x 1 convolution to generate the output segmentation map. Here, the number of filters is equal to the number of classes (2 in our case) required in the final output. 

#### U-Net

Qn: In the U-Net architecture, skip connections are responsible for:

- feature extraction

- reconstruction of image

- pixel map generation

Ans: B. *The upsampled output is combined with the output of the encoder phase at the same level using the skip connections as concatenation helps in preserving the information at that level.*

Now, you must now have a clear understanding of different sections of the U-Net architecture. Moving to the next segment, you will now explore the concept of upsampling.
