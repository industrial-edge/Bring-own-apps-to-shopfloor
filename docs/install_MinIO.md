## Contents

- [Contents](#Contents)
- [Prerequisites](#Prerequisites)
- [Overview](#Overview)
- [Installation Steps](#Installation Steps)
  1. [Connect to Industrial Edge Management by IEAP (Industrial Edge APP Publisher)](#1. Connect to Industrial Edge Management by IEAP (Industrial Edge APP Publisher))
  2. [Create a new empty app in Industrial Edge Management](#2. Create a new empty app in Industrial Edge Management)
  3. [Upload MinIO app to Industrial Edge Management](#3. Upload MinIO app to Industrial Edge Management)
  4. [Install MinIO app on Industrial Edge Device](#4. Install MinIO app on Industrial Edge Device)
- [Navigation](#navigation)



## Prerequisites

- Get familiar with the Industrial Edge App Developer Guide, which is available on [SIOS](https://support.industry.siemens.com/cs/ww/en/view/109795865). It contains description of the requirements as well as the step-by-step description how to install and work with the [Industrial Edge APP Developer Guide repository](https://github.com/industrial-edge/Developer-Guide-Hands-on-App).
- Install and onboard an Industrial Edge Management , install an IEAP (Industrial Edge APP Publisher).



## Overview

The following picture shows the technical routing of the THT Close-Loop APP deployment, the number in the picture is corresponded to the steps in the [Installation Steps](#Installation Steps).

![install_minio_overview](graphics/install_minio_overview.png)



## Installation Steps

#### 1. Connect to Industrial Edge Management by IEAP (Industrial Edge APP Publisher)

The installation description of this step is the same as the 1st step of the [THT Close-Loop APP Installation](./install_THT-Close-Loop-APP.md), for more details can see the related document.

#### 2. Create a new empty app in Industrial Edge Management

The installation description of this step is the same as the 2nd step of the [THT Close-Loop APP Installation](./install_THT-Close-Loop-APP.md), for more details can see the related document.

#### 3. Upload MinIO app to Industrial Edge Management

The installation description of this step is similar with the 3rd step of the [THT Close-Loop APP Installation](./install_THT-Close-Loop-APP.md), for more details can see the related document.

The only difference is that MinIO is an open source software, you can pull the image from the public repository, using the following code to download the specified MinIO image.

```
docker pull minio/minio:latest
```

Then you can import the following docker-compose.yaml file into IEAP to install MinIO app on Industrial Edge Management directly.

```
version: "2.4"
services: 
    minio:
        image: minio/minio:latest
        container_name: minio
        ports: 
            - 9000:9000
            - 9001:9001
        restart: on-failure
        command: server /data --console-address ":9001"
        volumes: 
            - storage_app_minio:/data 
        mem_limit: 1gb
        environment:
            MINIO_ROOT_USER: <user>
            MINIO_ROOT_PASSWORD: <password>
            
volumes:
    storage_app_minio:
```

#### 4. Install MinIO app on Industrial Edge Device

So far, you have completed the app uploading to Industrial Edge Management, and you can see the app version list in Industrial Edge Management. Then you can click on the download icon of your version and a new window to install the app is opened. ![install_minio_step4-1](graphics/install_minio_step4-1.png)

Select the Industrial Edge Device of the list, where the app should run on. Click on the "Install now" button to execute the deployment to the Industrial Edge Device immediately. This will take a while.

<img src="graphics/install_minio_step4-2.png" alt="install_minio_step4-1" style="zoom:67%;">

When the app deployment is successfully done, you will see the icon shown as below.![image-20220510091032940](graphics/install_minio_step4-3.png)



## Navigation

- [Overview](../README.md)
