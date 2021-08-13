### Tensorflow object detection installation procedure

1. Clone the Tensorflow models repository  
   ``` git clone https://github.com/tensorflow/models.git```
2. Install the application's dependencies  
    ``` pip install --user Cython contextlib2 pillow lxml jupyter matplotlib```
3. Download the Microsoft COCO (Common Objects in Context) API  
    - Linux  
        ```
        git clone https://github.com/cocodataset/cocoapi.git
        cd cocoapi/PythonAPI/
        make
        cp -r pycocotools <path-to-tensorflow>/models/research/
        ```  
    - Windows
        ```
        pip install git+https://github.com/philferriere/cocoapi.git#subdirectory=PythonAPI
        ```
4. Install Proto Buffer. Download the protoc packages for your os version from [link](https://github.com/protocolbuffers/protobuf/releases). 
    - Linux  
        ```sh
        cd <path-to-tensorflow>/models/research/
        mkdir protoc
        cd protoc
        wget https://github.com/protocolbuffers/protobuf/releases/download/v3.17.3/protoc-3.17.3-linux-x86_64.zip      
        unzip protoc-3.17.3-linux-x86_64.zip
        rm *.zip
        cd ..        
        ```
5. Compile protos.  
    ```
    cd <path-to-tensorflow>/models/research/
    protoc/bin/protoc object_detection/protos/*.proto --python_out=.
    ```
6. Update the paths to environment variables for your operating systems.
    ```sh
    export PYTHONPATH=$PYTHONPATH:<path-to-tensorflow>/models/research
    export PYTHONPATH=$PYTHONPATH:<path-to-tensorflow>/models/research/object_detection
    export PYTHONPATH=$PYTHONPATH:<path-to-tensorflow>/models/research/slim
    ```
7. Install TensorFlow Object Detection API.
   ```
   cd <path-to-tensorflow>/models/research/
   cp object_detection/packages/tf2/setup.py .
   python -m pip install --use-feature=2020-resolver .
   python setup.py build
   python setup.py install
   ```
8. Test the installation - ```python object_detection/builders/model_builder_tf2_test.py```
### Comment
The installation procedure was tested on Ubuntu 18.04.5 LTS (bionic) distribution on Linux 5.4.10+ x86_64.


### References
* Gilber Tanner YouTube video, [Installing the Tensorflow Object Detection API ](https://www.youtube.com/watch?v=qDm_YOwP2zY)  
* Object Detection API with TensorFlow 2 [Github page](https://github.com/tensorflow/models/blob/master/research/object_detection/g3doc/tf2.md)
