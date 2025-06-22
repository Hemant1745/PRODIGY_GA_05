# PRODIGY_GA_05

🧠 Neural Style Transfer – Theory Explanation

📌 What is Neural Style Transfer?

Neural Style Transfer (NST) is a deep learning technique that blends the content of one image with the style of another image using Convolutional Neural Networks (CNNs).

It was first introduced in the paper:
"A Neural Algorithm of Artistic Style" by Gatys et al., 2015

🔍 How It Works

NST uses a pre-trained CNN (typically VGG19) to extract features from images and performs optimization to generate a new image that:
- Matches the content of a "content image"
- Matches the style of a "style image"

⚙️ Key Concepts

1. Content Representation
- Captured from deeper layers of the CNN.
- Understands the structure and layout of the image.
- Usually taken from layer like conv_4.

2. Style Representation
- Captured from multiple shallower layers.
- Uses Gram matrices to represent texture, color, and patterns.
- Gram Matrix = Feature correlations (used to represent style).

3. Loss Functions
NST combines two losses:
- Content Loss: Difference between target and content image features.
- Style Loss: Difference between target and style image Gram matrices.

4. Optimization
- The target image is initialized as a copy of the content image.
- An optimizer (like Adam) updates the target image pixels to minimize total loss.
- Result: The image evolves to look like the content image with the style of the style image.

🔧 Model Used: VGG19
- A CNN pre-trained on ImageNet.
- Only its feature extractor (features) is used.
- Parameters are frozen; only the target image is optimized.

🧪 Summary of Steps

1. Load content and style images.
2. Load the VGG19 model (pre-trained).
3. Extract features from content and style.
4. Compute content and style losses.
5. Optimize the target image to minimize the total loss.
6. Save the final stylized image.

📸 Applications

- Art generation
- Filters in apps (like Prisma)
- Video style transfer
- Design & fashion automation
