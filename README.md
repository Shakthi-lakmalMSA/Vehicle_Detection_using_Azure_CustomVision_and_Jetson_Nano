# Developing a Vehicle detection model using Microsoft Azure Custom Vision with NVIDIA Jetson Nano & DeepStream

This explains using NVIDIA DeepStream to install, boot, and operate an Object Detection model for tracking vehicles on an NVIDIA Jetson Nano. Docker is used for deployment on the Jetson Nano, and Azure Custom Vision is utilized to train an object detection model.

#Prerequisites

#Hardware Requirements:

NVIDIA Jetson Nano (B01 or 2GB model)
MicroSD card (32GB recommended)
Power Supply for Jetson Nano(5v, 2.5A)
HDMI display, USB keyboard, and mouse
Wi-Fi adapter or Ethernet cable for network connection

#Software Requirements:

Jetson Nano SD card image from NVIDIA’s website (with JetPack)
Azure Subscription with Azure Machine Learning and Azure Custom Vision set up
DeepStream SDK

#Steps
#1. Setting Up the Jetson Nano
Step 1.1: Prepare the MicroSD Card
Download the NVIDIA Jetson Nano Developer Kit SD Card Image.
Flash the image to your MicroSD card using a tool like Balena Etcher.
#Step 1.2: Booting Jetson Nano
Insert the flashed MicroSD card into your Jetson Nano.
Connect the display, keyboard, and mouse.
Power on the Jetson Nano by connecting it to the power supply.
Complete the initial setup steps on the Jetson Nano, including selecting your locale and Wi-Fi connection.

#How to setup jetson Nano : https://developer.nvidia.com/embedded/learn/get-started-jetson-nano-devkit


2. Installing NVIDIA DeepStream SDK
Step 2.1: Install Dependencies
Open a terminal on the Jetson Nano and run:


#Copy code
sudo apt update
sudo apt install -y libssl1.0.0 libgstreamer1.0-0 libgstreamer-plugins-base1.0-dev \
                    libgstreamer-plugins-good1.0-dev gstreamer1.0-tools
Step 2.2: Install NVIDIA DeepStream
Download the latest DeepStream SDK for Jetson from the NVIDIA Developer website.

#Install the DeepStream SDK:

#Copy code
sudo dpkg -i deepstream-<version>-jetson.deb
sudo apt --fix-broken install


#Verify the installation:

#Copy code
deepstream-app --version-all

Step 3.1: Train a Model on Azure
Sign in to Azure Custom vision
Use the Azure Custom Vision service for Object Detection. You can either upload your dataset for vehicle tracking or use a pre-existing dataset.
Train the model in Azure Vision. After training, export the model in Docker file compatible with NVIDIA DeepStream.
Step 3.2: Export and Download Model
Export the model as a Docker file.
Download the model and transfer it to your Jetson Nano using SCP or USB.

How to build an Object detection model with Azure Custom Vision: https://learn.microsoft.com/en-us/azure/ai-services/custom-vision-service/get-started-build-detector


Link to Demo presentation : https://stdntpartners-my.sharepoint.com/:p:/g/personal/shakthi_lakmal_studentambassadors_com/EZeOSh-XMitCixX7_6UIXO8BP2GoEi7sya4Z_hpuLghkUA?e=0CIzuO








