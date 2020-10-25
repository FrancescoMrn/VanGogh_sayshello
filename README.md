# Vincent Van Gogh - Says Hello

This repository contains a small implementation of the code used to reproduce the results of the paper [First Order Motion Model for Image Animation](https://papers.nips.cc/paper/8935-first-order-motion-model-for-image-animation) - [Github code](https://github.com/AliaksandrSiarohin/first-order-model). FOMM can create animation by combining a, so-called, driving video and an image. This idea catching my mind since is not too hard to see many potential applications ranging across several areas of interest like e-shops.

## Application

In the intent to explore the capability of the model and learn more about the architecture and the code behind I develop *Vincent Van Gogh - Says Hello*.
<br/>
<p align="center">
  <img src="./images/VanGogh_SaysHello.gif" width=40% height=40% />
</p>
<center>F.Marino: "Vincent Van Gogh - Says Hello"</center>
<br/>

The idea is inspired to those extraordinary Harry Potter’s moving paintings that made us dream in the childhoods and finally are possible🧙‍!

## Technical overview

### How it works

The FOMM model is mainly composed of two parts: the motion estimation module and the image generation module.

The first module uses a set of keypoints learned in a self-supervised way. The module tracks the motion in the driver video and in the target image. The locations of the keypoints separately predicted by an encoder-decoder network.

In the second module, a dense motion network combines the local approximations to obtain the resulting dense motion and feed the generation module renders an image of the source object moving as provided in the
driving video.

<p align="center">
  <img src="./images/detailed_architecture.png" width=60% height=60% />
</p>

### Code implementation

The entire code is wrapped into a notebook that can be run inside *Google Colab*. The project recalls the original GitHub repo and the pre-trained model provided by the author to provide a quick inference over the new application. No significant changes to the code have been included to test the code as described in the paper.

### Pre-trained checkpoint
Original checkpoints of the model can be found under following link: [google-drive](https://drive.google.com/open?id=1PyQJmkdCsAkOYwUyaj_l-l0as-iLDgeH).

### Possible developments

- Reuse the model to perform a full-body inference
- Retrain the model to extend to different categories
- Tune the model for a specific application
