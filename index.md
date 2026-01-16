---
layout: default
---

<h1 align="center">
	<a href="https://github.com/In-spectrum/CamOnTime" target="_blank">
    	<img src="manual/images/baner.png" width="750" style="height:auto;" alt="CamOnTime | Personal media service.">
	</a>
	<br>
	<a href="https://github.com/In-spectrum/CamOnTime" target="_blank">
		Personal streaming media service
	</a>
</h1>

<br>

**Purpose**
* to create personal media service for viewing, recording RTSP streams from video cameras;
* share the video stream with other users;
 
**Application was tested**
* <a href="https://github.com/In-spectrum/CamOnTime/releases" target="_blank">Windows 10, Ubuntu 20.04.6, Android 11;</a>

**Planned**
* iOS, macOS;

**Preview**
<p align="center">
  <a href="manual/videos/demo.mp4">
    <img src="manual/images/demo_preview.png" width="600">
  </a>
</p>


## Table of contents

* [**CamOnTime-server**](#CamOnTime-server)
  * [Functions](#functions)
  * [Properties](#properties)
  * [Install](#install)
* [**CamOnTime-client**](#CamOnTime-client)
  * [Functions](#functions-1)
  * [Install](#install-1)
* [**Installing additional software**](#installing-additional-software)
* [**Contacts**](https://github.com/In-spectrum)
* [**License**](#license)

## **CamOnTime-server**
### Functions  
  &emsp;&nbsp;- user registration;
  <br>&emsp;&nbsp;- recording video files;
  <br>&emsp;&nbsp;- user access to cameras and files (depending on the status);

### Properties
**-pas** - set server password (default: 1111); _**CamOnTimeServer -pas 2227**_<br>
**-p** - set listen port (default: 1255); _**CamOnTimeServer -p 1675**_<br>
**-prtsp** - set rtsp-server port for viewing video files (default: 8554); _**CamOnTimeServer -prtsp 8654**_<br>
**-f** - set path to video files folder (default: home/user_name/Video); _**CamOnTimeServer -f D://VideoBox**_<br>

### Install
 - [GStreamer install](#installing-additional-software);
 - download <a href="https://github.com/In-spectrum/CamOnTime/releases" target="_blank">application archive</a> and unzip;
 - start the server with parameters: **_CamOnTimeServer -pas 2227 -p 1675 -prtsp 8654_**

## CamOnTime-client
The administrator create users and has access to all cameras.

### Functions
- adding/deleting RTSP stream of camera;
- simultaneous viewing of several video cameras;
- setting the total time for recording files;
- setting the status of the video camera as publicly available for all users on the server;
- generating code for viewing the video camera by clients who are not connected to the server but have the application installed;
- copy/delete files;

### Install
 - [GStreamer install](#installing-additional-software);
 - download <a href="https://github.com/In-spectrum/CamOnTime/releases" target="_blank">application archive</a> and unzip;
 - start the CamOnTimeClient;
   
## Installing additional software
### Windows
- download installation files: <a href="https://gstreamer.freedesktop.org/data/pkg/windows/1.26.7/mingw/" target="_blank">gstreamer-1.0-mingw-x86_64-1.26.7.msi и gstreamer-1.0-devel-mingw-x86_64-1.26.7.msi</a>;
- run with administrator rights;
- select **Custom** and **check all plugins**;
- add __C:\gstreamer\1.0\mingw_x86_64\bin__ to **PATH** system;
- if after run the application there is an error with **libgst3d11.dll** or **libgst3d12.dll**- delete them from __C:\gstreamer\1.0\mingw_x86_64\lib\gstreamer-1.0__
### Ubuntu
```
#sudo apt-get update && upgrade
```
- for show user interface:
```
#sudo apt-get install '^libxcb.*-dev' libx11-xcb-dev libglu1-mesa-dev libxrender-dev -y
```
- install the GStreamer plugins **version 1.26.7**: _gstreamer1.0-plugins-ugly, gstreamer1.0-plugins-bad, gstreamer1.0-rtsp_.

## License
All code in this repository is released under the <a href="https://github.com/In-spectrum/CamOnTime/blob/main/LICENSE">MIT license</a>. 
<br>Application archives and compiled binaries make use of some third-party dependencies:
- Qt - the primary <a href="https://www.qt.io/licensing/open-source-lgpl-obligations#" target="_blank">open-source license</a> is the GNU Lesser General Public License v.3 <a href="https://www.gnu.org/licenses/lgpl-3.0.txt" target="_blank">“LGPL v3”</a>;
- GStreamer - <a href="https://github.com/GStreamer/gstreamer/blob/main/LICENSE" target="_blank">licensed under the LGPL v2.1;
