# Image-to-Image Translation using cGAN (Pix2Pix)

Converts a facade label map into a realistic building photo using a conditional GAN, built with PyTorch and trained on Google Colab.

## Objective
Learn to translate an input image into a realistic output image from paired examples.

## Model
*Pix2Pix (conditional GAN)*
- *Generator:* U-Net (encoder-decoder with skip connections)
- *Discriminator:* PatchGAN (70x70)
- *Loss:* Adversarial loss + 100 x L1 loss

## Technologies
Python, PyTorch, torchvision, Pillow, Matplotlib, Google Colab (GPU), Google Drive

## Dataset
CMP Facades: 400 train and 100 validation pairs (label map + real photo).
Link: http://efrosgans.eecs.berkeley.edu/pix2pix/datasets/facades.tar.gz

## How It Works
1. Split each paired image into input and target.
2. Resize, random crop and flip, then normalize.
3. Generator creates a fake image from the input.
4. Discriminator checks whether the image is real or fake.
5. Both networks are updated for 40 epochs.
6. At test time, only the Generator is used.

## How to Run
1. Open the notebook in Google Colab and select a T4 GPU.
2. Set your Google Drive folder in BASE.
3. Run all cells in order.
4. For testing, call translate("my_image.png", use_left_half=False).

## Limitations
- Needs paired data.
- Only 400 training images, so results are not fully realistic.


