![Darknet Logo](http://pjreddie.com/media/files/darknet-black-small.png)

#Darknet#
Darknet is an open source neural network framework written in C and CUDA. It is fast, easy to install, and supports CPU and GPU computation.

For more information see the [Darknet project website](http://pjreddie.com/darknet).

For questions or issues please use the [Google Group](https://groups.google.com/forum/#!forum/darknet).

# Changes in this fork

* Instead of taking a single image file path, the modified darknet CLI now takes a file that contains a list of image file paths to predict objects for, one image file path per line.
* Instead of writing out an image annotated with bounding boxes, the modified darknet CLI writes out a TSV file of bounding box annotations, one per input image file. The TSV file has the same path and basename as the input image and a .tsv suffix. Format of the file is (image file path, predicted entity, prediction probability, top left x, top left y, bottom right x, bottom right y).

The old command to run the pre-trained YOLO detector was as follows:

    ./darknet detector test cfg/coco.data cfg/yolo.cfg yolo.weights data/dog.jpg

Post the changes described above, the command is:

    ./darknet detector test cfg/coco.data cfg/yolo.cfg yolo.weights mylist.txt

where mylist.txt looks like this:

    data/dog.jpg
    data/person.jpg

Example output for bounding boxes for dog.jpg looks like this:

    data/dog.jpg	car	0.542268	247	56	364	125
    data/dog.jpg	truck	0.261111	247	56	364	125
    data/dog.jpg	bicycle	0.509336	53	89	301	317
    data/dog.jpg	cat	0.346415	63	152	173	390
    data/dog.jpg	dog	0.558766	63	152	173	390

