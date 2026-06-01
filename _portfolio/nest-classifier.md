---
title: "Polistes Nest Classifier (Deep Learning)"
excerpt: "A deep-learning image classifier that detects European paper wasp (Polistes dominula) nests in field photos."
collection: portfolio
---
I built a deep-learning image classifier that automatically detects European paper wasp (*Polistes dominula*) nests in photographs, distinguishing nest images from non-nest images.

The model fine-tunes a pretrained **EfficientNet-B0** convolutional neural network using a two-phase transfer-learning strategy — first training the classifier head with the backbone frozen, then gradually unfreezing the final feature blocks at a lower learning rate. To handle the variability of real field photos and class imbalance, it uses heavy data augmentation (random crops, flips, rotation, color jitter, grayscale, blur, and random erasing) together with a class-weighted loss. After training, the decision threshold is tuned on a validation set to balance precision and recall.

The classifier is designed to support **STL Wasp Watch** by automatically flagging likely nests in community-submitted photos, reducing the manual effort of sorting field observations.

Built with Python, PyTorch, torchvision, and scikit-learn.
