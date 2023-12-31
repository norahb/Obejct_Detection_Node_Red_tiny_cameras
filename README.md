# Obejct detection On Node-RED using three Tiny cameras
This project uses 3 cameras and node-red on Raspberry Pi 4 to detect objects.


![Screenshot](obd.png)


The image depicts a visual representation of the object detection flow using Node-RED and three different cameras (ESP32 CAM, ESP-EYE, and Pi Camera) on a Raspberry Pi 4.

## Instructions
### ESP32 CAM (CamerWebServer)

a. Use the CameraWebServer sketch example from the ESP32 library on ESP-32.

b. Change the ssid and password in the sketch to match your network credentials.

c. Uncomment the line #define CAMERA_MODEL_AI_THINKER to select the appropriate camera model.

d. Upload the sketch to the ESP32 board.

e. Obtain the HTTP address of the camera after the sketch is uploaded.

### ESP-EYE

a. Install the Espressif IDF (IoT Development Framework) for ESP32 chips following the official guide: https://docs.espressif.com/projects/esp-idf/en/stable/esp32/get-started/index.html

b. Run the examples from the ESP-WHO platform to test the ESP-EYE camera module.

c. Obtain the HTTP address of the camera after the sketch is uploaded.


### Pi Camera
a. For the Pi Camera, you don't need to install any additional packages in Node-RED.

b. open Node-RED and import the Object_Detection_Flow.json flow file. 

c. Edit the HTTP request nodes and set it to the copied HTTP address (e.g., http://xxx.xxx.xxx.xxx/capture) for ESP32 CAM and ESP-EYE.

d. Click the "Deploy" button to deploy the flow.

e. Use the "Take photo" node in your Node-RED flow to capture images from one of the three cameras.

### Required hardware
- Raspberry Pi 4
- ESP32 CAM
- ESP-EYE
- Pi Camera

### Required Node-RED Packages:

Make sure you have the following Node-RED packages installed:

- node-red-contrib-camerapi: This package allows you to interact with the Pi Camera using Node-RED.

- node-red-contrib-tfjs-coco-ssd: This package enables object detection using TensorFlow.js and the COCO-SSD model in Node-RED.

With all the cameras connected and properly set up, you can create a Node-RED flow that captures images from each camera and then pass these images through the object detection module to identify objects in the images.

Please note that the process might be a bit more complex and may require additional configurations and troubleshooting based on your specific setup and environment.
