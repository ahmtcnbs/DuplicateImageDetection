# DuplicateImageDetection

This system uses a perceptual hashing function, similar to Apple's CSAM Detection. Instead of generating image hashes using NeuralHash, it uses a difference hash (dHash), which is simpler and less computationally intensive as it doesn't require neural networks. Since we don't have the same privacy constraints as Apple, we will be using nearest neighbor searches to identify duplicate images.

