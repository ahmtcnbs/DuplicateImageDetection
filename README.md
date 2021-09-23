# Duplicate Image Detection

This system uses a perceptual hashing function, similar to Apple's CSAM Detection. Instead of generating image hashes using NeuralHash, it uses a difference hash (dHash), which is simpler and less computationally intensive as it doesn't require neural networks. Since we don't have the same privacy constraints as Apple, we will be using nearest neighbor searches to identify duplicate images.

![schema](https://user-images.githubusercontent.com/36485110/134481799-8cf1e1a1-a88c-43b2-9d3e-f69333e89b43.png)

## Difference Hash

dHash is a perceptual hashing function that produces hash values that are resilient to image scaling, as well as changes in color, brightness, and aspect ratio [1]. There are 4 main steps for creating a difference hash for an image:

![schema2](https://user-images.githubusercontent.com/36485110/134481936-a63e99a0-8b7f-4d67-a40f-ea6e6daa134d.png)

1. Convert to greyscale*
2. Resize image to (hash_size+1, hash_size)
3. Calculate horizontal gradient, reducing image size to (hash_size, hash_size)
4. Assign bits based on horizontal gradient values

*We convert the image to greyscale before resizing for optimal performance

## API

![main-image](https://user-images.githubusercontent.com/36485110/134481717-2e6a9259-674e-46ce-aa99-4e6d522f8ac4.png)

## References

[1] https://www.hackerfactor.com/blog/?/archives/529-Kind-of-Like-That.html
