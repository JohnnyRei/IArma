# IArma

A convolutional neural network that classifies images into two groups: with a firearm or without one. Built with Keras and TensorFlow in a Jupyter notebook.

## How it works

Images are resized to 64x64 pixels and go through two convolution and max pooling blocks, a dense layer with 128 units and a sigmoid output. The model is trained with Adam and binary cross-entropy for 38 epochs.

The training data is split 80/20 into training and validation. Augmentation (shear, zoom and horizontal flip) is applied to the training part only. After training, the notebook prints a confusion matrix and accuracy, precision, recall and F1 on the validation images, then runs the model on the images in `dataset_test`.

## Dataset

| Folder | Contents |
|---|---|
| `dataset_training/guns` | 847 images with firearms |
| `dataset_training/random` | 848 images without firearms |
| `dataset_test` | 11 images for a quick visual test at the end of the notebook |
| `dataset_validation` | 888 extra images without labels, not used in training |

## Running

```bash
git clone https://github.com/JohnnyRei/IArma.git
cd IArma
pip install tensorflow scikit-learn pillow notebook
jupyter notebook IArma.ipynb
```

The repository is large because the images are versioned with the code, so the clone takes a while.

## Next steps

- Try transfer learning with a pretrained network such as MobileNet or ResNet.
- Train with more varied images and at a higher resolution than 64x64.
- Save the trained model so it can be used without training again.

## License

[MIT](LICENSE)
