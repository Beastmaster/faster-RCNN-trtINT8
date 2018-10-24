The FasterRCNN sample uses the dataset from here:
https://dl.dropboxusercontent.com/s/o6ii098bu51d139/faster_rcnn_models.tgz

The dataset needs to be placed into the data/faster-rcnn directory.

The commands to do this on linux are as follows:

cd <TensorRT directory>
wget --no-check-certificate https://dl.dropboxusercontent.com/s/o6ii098bu51d139/faster_rcnn_models.tgz?dl=0 -O data/faster-rcnn/faster-rcnn.tgz
tar zxvf data/faster-rcnn/faster-rcnn.tgz -C data/faster-rcnn --strip-components=1 --exclude=ZF_*


src: /usr/src/tensorrt/samples/
model and data: /usr/src/tensorrt/data/faster-rcnn


Convert to INT8 
Refer to sampleINT8 in tensorrt examples





