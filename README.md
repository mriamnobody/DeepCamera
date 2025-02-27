<div align="center">
<h1>&nbsp;&nbsp;DeepCamera </h1>
  <p>
		<b>
        <h3> Empower camera with SOTA AI <br>ML pipeline for AI camera/CCTV <br>Easy to use Edge AI development</h3>
        </b>
	</p>

<p>
    <a href="https://join.slack.com/t/sharpai/shared_invite/zt-1g4l7c928-w6ANwRzdAjstIw3wYmwG1g">
        <img src="https://img.shields.io/badge/slack-purple?style=for-the-badge&logo=slack" height=25>
    </a>
    <a href="https://github.com/SharpAI/DeepCamera/issues">
        <img src="https://img.shields.io/badge/support%20forums-navy?style=for-the-badge&logo=github" height=25>
    </a>
    <a href="https://github.com/SharpAI/DeepCamera/releases">
        <img alt="GitHub release" src="https://img.shields.io/github/release/SharpAI/DeepCamera.svg?style=for-the-badge" height=25>
    </a>
    <a href="https://pypi.python.org/pypi/sharpai-hub">
        <img alt="Pypi release" src="https://img.shields.io/pypi/v/sharpai-hub.svg?style=for-the-badge" height=25>
    </a>
    <a href="https://pypi.python.org/pypi/sharpai-hub">
        <img alt="Monthly download" src="https://img.shields.io/pypi/dm/sharpai-hub.svg?style=for-the-badge" height=25>
    </a>
</p>

<br>
</div>

DeepCamera empowers your traditional surveillance cameras and CCTV/NVR with machine learning technologies. 
It provides open source facial recognition based intrusion detection, fall detection and parking lot monitoring with the inference engine on your local device.

SharpAI-hub is the cloud hosting for AI applications which help you deploy AI applications with your CCTV camera on your edge device in minutes. 



### Empower any camera with the state of the art AI
- facial recognition
- person recognition(RE-ID)
- parking lot management
- fall detection

###  ML pipeline for AI camera/CCTV development
- feature clustering with vector database Milvus
- labelling with Labelstudio
### Easy to use Edge AI development environment
- AI frameworks in docker
- desktop in docker with web vnc client, so you don't need even install vnc client

# Install SharpAI-Hub CLI
`pip3 install sharpai-hub`

# Self-supervised person recognition(REID) intruder detection
<img src="screenshots/reid_self_supervised.gif" width="960" height="540" />

SharpAI yolov7_reid is an open source python application leverages AI technologies to detect intruder with traditional surveillance camera. Source code is [here](https://github.com/SharpAI/DeepCamera/blob/master/src/yolov7_reid/src/detector_cpu.py)

It leverages Yolov7 as person detector, FastReID for person feature extraction, Milvus the local vector database for self-supervised learning to identity unseen person, Labelstudio to host image locally and for further usage such as label data and train your own classifier. It also integrates with Home-Assistant to empower smart home with AI technology. 

## Deploy yolov7_reid with sharpai-hub CLI

```
pip3 install sharpai-hub
sharpai-cli yolov7_reid start
```
If you are using Windows, you can use following command line to start yolov7_reid application
```
python3 -m sharpai_hub.cli yolov7_reid start
```

Then please following the instruction which sharpai-cli provides.   
The yolov7 detector is running in docker, you can access the docker desktop with http://localhost:8000  

Home-Assistant is hosted at http://localhost:8123  
Labelstudio is hosted at http://localhost:8080

# DeepCamera Facial Recognition local deployment
We received feedback from community, local deployment is needed. With local deepcamera deployment, all information/images will be saved locally.   
`sharpai-cli local_deepcamera start`

# DeepCamera Facial Recognition cloud deployment for free
- Register account on [SharpAI website](http://dp.sharpai.org:3000)
- Login on device: `sharpai-cli login`
- Register device: `sharpai-cli device register`
- Start DeepCamera: `sharpai-cli deepcamera start`

# [Laptop Screen Monitor](https://github.com/SharpAI/laptop_monitor) for kids/teens safe
SharpAI Screen monitor captures screen extract screen image features(embeddings) with AI model, save unseen features(embeddings) into AI vector database [Milvus](https://milvus.io/), raw images are saved to [Labelstudio](https://labelstud.io) for labelling and model training, all information/images will be only saved locally.

`sharpai-cli screen_monitor start`

### Access streaming screen: http://localhost:8000
### Access labelstudio: http://localhost:8080

# SharpAI-Hub AI Applications
SharpAI community is continually working on bringing state-of-the-art computer vision application to your device.

```
sharpai-cli <application name> start
```

|Application|SharpAI CLI Name| OS/Device |
|---|---|---|
|[Laptop Screen Monitor](https://github.com/SharpAI/laptop_monitor)| screen_monitor   | Windows/Linux/MacOS|
|[Facial Recognition Intruder Detection](docs/how_to_run_intruder_detection.md) | deepcamera | Jetson Nano|Windows/Linux/MacOS|
|[Local Facial Recognition Intruder Detection](docs/how_to_run_local_intruder_detection.md) | local_deepcamera | Windows/Linux/MacOS|
|[Parking Lot monitor](docs/Yolo_Parking.md) | yoloparking  | Jetson AGX |
|[Fall Detection](docs/FallDetection_with_shinobi.md) | falldetection   |Jetson AGX|

# Tested Devices
## Edge AI Devices / Workstation
- [Jetson Nano (ReComputer j1010)](https://www.seeedstudio.com/Jetson-10-1-H0-p-5335.html)
- Jetson Xavier AGX
- MacOS 12.4
- Windows 11
- Ubuntu 20.04

## Tested Camera:
- DaHua / Lorex / AMCREST: URL Path: `/cam/realmonitor?channel=1&subtype=0` Port: `554`
- Ip Camera Lite on IOS: URL Path: `/live` Port: `8554`   
- Nest Camera indoor/outdoor by Home-Assistant integration

# Support
- If you are using a camera but have no idea about the RTSP URL, please join SharpAI community for help.
- SharpAI provides commercial support to companies which want to deploy AI Camera application to real world.
## [Click to join sharpai slack channel](https://sharpai-invite-automation.herokuapp.com/)

# DeepCamera Architecture
![architecture](screenshots/DeepCamera_infrastructure.png)

# [DeepCamera Feature List](docs/DeepCamera_Features.md)

# Commercial Version
- Provide real time pipeline on edge device     
- E2E pipeline to support model customization  
- Cluster on the edge  
- Port to specific edge device/chipset
- Voice application (ASR/KWS) end to end pipeline  
- ReID model   
- Behavior analysis model    
- Transformer model  
- Contrastive learning  
- [Click to join sharpai slack channel for commercial support](https://sharpai-invite-automation.herokuapp.com/)

# FAQ

## [How to install python3](https://www.python.org/downloads)
## [How to install pip3](https://pip.pypa.io/en/stable/installation)
##  How to install Docker-compose on Jetson Nano
```
sudo apt-get install -y libhdf5-dev python3 python3-pip
pip3 install -U pip
sudo pip3 install docker-compose==1.27.4
```
## [How to use web gui](screenshots/how_to_config_on_web_gui.png)
## [How to config RTSP on GUI](https://github.com/SharpAI/DeepCamera/blob/master/docs/shinobi.md)   
## [Camera streaming URL format](https://shinobi.video)
## How to create token for Telegram Bot(DOC W.I.P)
- Create Telegram Bot through @BotFather
- Set Telegram Token in [Configure File](https://github.com/SharpAI/DeepCamera/blob/nano/docker/production_1.env#L15)
- Send message to the new bot you created

## [Contributions](Contributions.md)
