## Contents

- [Contents](#Contents)
- [Prerequisites](#Prerequisites)
- [Overview](#Overview)
- [Installation Steps](#Installation Steps)
  1. [Connect to IEM (Industrial Edge Management) by IEAP (Industrial Edge APP Publisher)](#1. Connect to IEM (Industrial Edge Management) by IEAP (Industrial Edge APP Publisher))
  2. [Create a new empty app in IEM](#2. Create a new empty app in IEM)
  3. [Upload THT Close-Loop app to IEM](#3. Upload THT Close-Loop app to IEM)
  4. [Install THT Close-Loop app on IED](#4. Install THT Close-Loop app on IED)
- [Navigation](#navigation)



## Prerequisites

- Get familiar with the Industrial Edge App Developer Guide, which is available on [SIOS](https://support.industry.siemens.com/cs/ww/en/view/109795865). It contains description of the requirements as well as the step-by-step description how to install and work with the [Industrial Edge APP Developer Guide repository](https://github.com/industrial-edge/Developer-Guide-Hands-on-App).
- Install and onboard an IEM (Industrial Edge Management), install an IEAP (Industrial Edge APP Publisher).



## Overview

The following picture shows the technical routing of the THT Close-Loop APP deployment, the number in the picture is corresponded to the steps in the [Installation Steps](#Installation Steps).

![install_tht_overview](graphics/install_tht_overview.png)



## Installation Steps

#### 1. Connect to IEM (Industrial Edge Management) by IEAP (Industrial Edge APP Publisher)

Click on "+Docker Engine" button to add the local Docker Engine to the IEAP of your development environment. 

![install_tht_step1-1](graphics/install_tht_step1-1.png)

Configure the Docker Engine connection and Click on "Connect" button to connect the local Docker Engine.

<img src="graphics/install_tht_step1-2.png" alt="install_tht_step1-1" style="zoom:67%;" />

Click on “Go Online” to connect to the IEM system.



![install_tht_step1-3](graphics/install_tht_step1-3.png)

A new window will open to enter the IEM URL, aftering entering the IEM URL, click on the "Connect" button.

<img src="graphics/install_tht_step1-4.png" style="zoom:67%;" />

Then you need to provide your personal credentials to login IEM.

<img src="graphics/install_tht_step1-5.png" alt="install_tht_step1-5" style="zoom:67%;" />

#### 2. Create a new empty app in IEM

After you connect to the IEM you should see the picture below, to view the apps loaded in the IEM. Then you can click on the "+Create Application" button to add a new empty app for the importing preparation of the THT Close-Loop app.

![install_tht_step2-1](graphics/install_tht_step2-1.png)

Then please fill out all fields in the picture below, the content is used to describe the THT Close-Loop app, then you can click on the "Create" button. 

![install_tht_step2-2](graphics/install_tht_step2-2.png)

After you complete the THT Close-Loop app repository creation, you can see your currently created app repository with selected icon in the IEM. Then you can import your THT Close-Loop app instance into this repository.

![image-20220509143046963](graphics/install_tht_step2-3.png)

#### 3. Upload THT Close-Loop app to IEM

Click on the icon of your app, you will enter the app version management page. Then you click on "+Add New Version", a new dialog to select your docker compose version. 

![install_tht_step3-1](graphics/install_tht_step3-1.png)

**Since the THT Close-Loop app is a third-party app with non-open source, we cannot fully open the app image, so we ignore the image installation step in the development environment and directly enter the docker-compose file configuration step.**

Now you have two options to create a docker-compose file of your app in IEAP: 

1. "+Add Services": graphical supported by dialogues to create a corresponding docker-compose.yml file 
2. "Import YAML": import of an existing docker-compose.yml file and adapt it afterwards

In this use case, you can select the 2nd option to import an existing docker-compose.yaml file directly.

![install_tht_step3-2](graphics/install_tht_step3-2.png)

After all the docker-compse.yml configuration completed, a window with ‘Add version’ appears. As it is the first version of your app, you do not modify anything and just click on ‘Create’.

<img src="graphics/install_tht_step3-3.png" alt="install_tht_step3-3" style="zoom: 50%;" />

If everything in the docker-compose is correct and the built images exist are available, your first version of your THT Close-Loop app is available. This might take a second. 

![image-20220509145358015](graphics/install_tht_step3-4.png)

#### 4. Install THT Close-Loop app on IED

So far, you have completed the app uploading to IEM, and you can see the app version list in IEM. Then you can click on the download icon of your version and a new window to install the app is opened. 

![image-20220509150928757](graphics/install_tht_step4-1.png)

Select the IED of the list, where the app should run on. Click on the "Install now" button to execute the deployment to the IED immediately. This will take a while.

<img src="graphics/install_tht_step4-2.png" alt="install_tht_step4-2" style="zoom: 67%;" />

When the app deployment is successfully done, you will see the icon shown as below.

![install_tht_step4-3](graphics/install_tht_step4-3.png)



## Navigation

- [Overview](../README.md)