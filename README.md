![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

#Darknet#
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).

# Changes in this fork

* Instead of taking a single image file path, the modified darknet CLI now takes a file that contains a list of image file paths to predict objects for, one image file path per line.
* Instead of writing out an image annotated with bounding boxes, the modified darknet CLI writes out a TSV file of bounding box annotations, one per input image file. The TSV file has the same path and basename as the input image and a .tsv suffix. Format of the file is (image file path, predicted entity, prediction probability, top left x, top left y, bottom right x, bottom right y).

