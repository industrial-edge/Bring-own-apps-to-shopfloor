## Contents

- [Contents](#Contents)
- [Prerequisites](#Prerequisites)
- [Overview](#Overview)
- [Installation Steps](#Installation-Steps)
  - [Connect to Industrial Edge Management by Industrial Edge APP Publisher](#Connect-to-Industrial-Edge-Management-by-Industrial-Edge-APP-Publisher)
  - [Create a new empty app in Industrial Edge Management](#Create-a-new-empty-app-in-Industrial-Edge-Management)
  - [Upload SQL Server app to Industrial Edge Management](#Upload-SQL-Server-app-to-Industrial-Edge-Management)
  - [Install SQL Server app on Industrial Edge Device](#Install-SQL-Server-app-on-Industrial-Edge-Device)
- [Navigation](#navigation)



## Prerequisites

- Get familiar with the Industrial Edge App Developer Guide, which is available on [SIOS](https://support.industry.siemens.com/cs/ww/en/view/109795865). It contains description of the requirements as well as the step-by-step description how to install and work with the [Industrial Edge APP Developer Guide repository](https://github.com/industrial-edge/Developer-Guide-Hands-on-App).
- Install and onboard an Industrial Edge Management, install an IEAP (Industrial Edge APP Publisher).



## Overview

Main features of the SQL Server in this application example:

- Store all historical data and key results of the THT Close-Loop APP
- Provide data support for data interaction between MinIO and THT Close-Loop APP

The following picture shows the technical routing of the THT Close-Loop APP deployment, the indexes in the picture are corresponded to the steps in the [Installation Steps](#Installation-Steps).

![install_sqlserver_overview](graphics/install_sqlserver_overview.png)



## Installation Steps

#### Connect to Industrial Edge Management by Industrial Edge APP Publisher

The installation description of this step is the same as the 1st step of the [THT Close-Loop APP Installation](./install_THT-Close-Loop-APP.md), for more details can see the related document.

#### Create a new empty app in Industrial Edge Management

The installation description of this step is the same as the 2nd step of the [THT Close-Loop APP Installation](./install_THT-Close-Loop-APP.md), for more details can see the related document.

#### Upload SQL Server app to Industrial Edge Management

The installation description of this step is similar with the 3rd step of the [THT Close-Loop APP Installation](./install_THT-Close-Loop-APP.md), for more details can see the related document.

The only difference is that SQL Server is an open source software, you can use the `docker pull` command to pull the specified SQL Server image from the GitHub repository.

Then you can import the docker-compose.yml file of SQL Server app into IEAP to install it on Industrial Edge Management directly. The template of the SQL Server yml file can be found in [Docker: Install containers for SQL Server on Linux - SQL Server | Microsoft Docs](https://docs.microsoft.com/en-us/sql/linux/quickstart-install-connect-docker?view=sql-server-2017&pivots=cs1-bash). The only difference is that you need to define the memory limitation of the app in the yml file.

#### Install SQL Server app on Industrial Edge Device

So far, you have completed the app uploading to Industrial Edge Management, and you can see the app version list in Industrial Edge Management. Then you can click on the download icon of your version and a new window to install the app is opened. ![install_sql_step4-1](graphics/install_sql_step4-1.png)

Select the Industrial Edge Device of the list, where the app should run on. Click on the "Install now" button to execute the deployment to the Industrial Edge Device immediately. This will take a while.

<img src="graphics/install_sql_step4-2.png" alt="install_sql_step4-2" style="zoom:67%;" />

When the app installation is successfully done, you will see the icon shown as below.![install_sql_step4-3](graphics/install_sql_step4-3.png)



## Navigation

- [Overview](../README.md)
