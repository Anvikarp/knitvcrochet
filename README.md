# Knit vs. Crochet

A deep learning project for automated textile classification using computer vision to distinguish between knitted and crocheted fabrics.

## Motivation

This project addresses an important labor rights issue in the textile industry. While knitted fabrics can be mass-produced using industrial machinery, crochet work can only be done by hand. This makes crochet items significantly more labor-intensive, with a single piece potentially requiring dozens of hours of skilled handwork.

The ability to automatically identify crochet versus knit textiles can help detect potential worker exploitation when crochet items are sold at very low prices.

## Results

**Validation Accuracy: 88.94%**

## Technical Implementation

I built a model using a deep convolutional neural network (CNN) in TensorFlow/Keras. It's structured with three convolutional blocks, progressively increasing the number of filters from 32 to 128. It takes in 180×180 RGB images and was trained on our custom dataset of 2,309 textile images, using an 80/20 split for training and validation.

To train the model, I used data augmentation (random flips and rotations), 50% dropout, and early stopping to prevent overfitting. It ultimately converged in 18 epochs, optimized with the Adam optimizer and binary crossentropy loss.

## Dataset
The training dataset consists of 2,309 images collected from the following knit/crochet stitch books:

### Crochet References:
- *The New Crochet Stitch Dictionary: 440 Patterns for Textures, Shells, Bobbles, Lace, Cables, Chevrons, Edgings, Granny Squares, and More* by Nele Braas and Eveline Hetty-Burkart (Stackpole Books, 2021)
- *The Big Book of Crochet Stitches: Fabulous Fans, Pretty Picots, Clever Clusters and a Whole Lot More* by Rita Weiss and Jean Leinhauser (Martingale, 2014)
- *Crochet Stitch Dictionary: 200 Essential Stitches with Step-by-Step Photos* by Sarah Hazell (Interweave Press, 2013)

### Knitting References:
- *Ultimate Knit Stitch Bible: 750 Knit, Purl, Cable, Lace and Colour Stitches* by Collins & Brown (David & Charles, 2015)
- *The Knitting All Around Stitch Dictionary: 150 New Stitch Patterns to Knit Top Down, Bottom Up, Back and Forth & In the Round* by Wendy Bernard

Images were manually categorized into knit and crochet classes, with 1,188 crochet samples and 1,121 knit samples.

## Future Improvements

The model could be improved through transfer learning, expanded datasets with more diverse samples, and mobile deployment for real-time classification. 

