# IBM Data Science Experience Desktop
**This project is no longer maintained.** If you have a problem, look through the [Troubleshooting](#troubleshooting) section and [existing issues](https://github.com/IBMDataScience/DSx-Desktop/issues?utf8=%E2%9C%93&q=) to see if it has been resolved before.

IBM Data Science Experience Desktop was built for those who want to download and play locally. Analyze, learn, and build with the tools you love, right on your desktop.
* [Download for Mac](https://github.com/IBMDataScience/DSx-Desktop/releases/download/1.2.4/IBM_DSX_Desktop-1.2.4.dmg)
* [Download for Windows](https://github.com/IBMDataScience/DSx-Desktop/releases/download/1.2.4/IBM_DSX_Desktop-1.2.4.exe)
* [Download for Linux](https://github.com/IBMDataScience/DSx-Desktop/releases/download/1.2.4/ibm-dsx-desktop.AppImage)

## Features
* The same Jupyter notebooks you know and love with the building blocks you need for Python, R, and Scala. 
* Easily access Apache Spark from your desktop so you can create and learn on the go. 
* Built-in tutorial notebooks to help jump start your learning experience.
* Support for RStudio IDE and Zeppelin notebooks, to meet your various needs.

![Jupyter Notebook](notebook.png)

## Documentation
Documentation for DSX Desktop can be found on the [content hub](https://content-dsxdesktop.mybluemix.net/).

## Troubleshooting
Troubleshooting problems in DSX Desktop.

### Compatibility
DSX Desktop works on all platforms (MacOS, Windows 7, Windows 10, and Linux), but certain platforms have more issues than others.
* MacOS and Linux have very few (if any) issues, the majority of them are Windows.
* Windows 10 Enterprise, Pro, and Education has [Hyper-V](https://docs.microsoft.com/en-us/virtualization/hyper-v-on-windows/quick-start/enable-hyper-v), which enables Docker to run natively, and is less error-prone.
* Windows 7 and Windows 10 Home runs Docker inside a VirtualBox VM, which is very error-prone.

### Check if the VM is Running (Windows 7, Windows 10 Home)
Windows 7 and Windows 10 Home runs Docker inside a VirtualBox VM named **ibm-dsx**. When you start DSX Desktop, it tries to start this VM (sometimes unsuccessfully).

If the VM fails to start after five attempts, **it will be removed and a new one will be created**, resulting in you having to go through the install again.

To get around this, you can attempt to start the VM manually, either through VirtualBox or the command line:
* **VirtualBox**: open VirtualBox, right-click the ibm-dsx machine, and click Start > Headless Start
* **Command Line**: open a command prompt and enter `docker-machine start ibm-dsx`

### Try Pulling an Image with Docker
If you're having problems on the installation screen (after the image selection), it may be that Docker is unable to pull the images.

To test, start Docker, then open a terminal or command prompt and enter `docker pull hello-world`. If that fails, then Docker is unable to pull any images, so the installation cannot complete.

**Note**: Windows 7 and Windows 10 Home users, use the Docker Quickstart Terminal.

### Ensure Shared Drives are Enabled (Windows 10 Enterprise, Pro, Education)
If you're trying to launch a Notebook or RStudio and DSX Desktop is saying you don't have it installed (even if you do), then it may be that Docker cannot access your files.

To check if you have shared drives enabled, right-click on the Docker tray icon, click settings, then on the "Shared Drives" tab, ensure that your primary drive is checked (usually `C:\`).

You can also test it by opening a command prompt and entering
```sh
docker run --rm -it -v c:\Users:/data alpine ls /data
```
which should result in a list of the users. If it doesn't, then check to see if you have shared drives enabled.

**Note**: if you're using Microsoft AD, then you will be unable to share your drive with Docker using your account's credentials. Instead, follow [these instructions](https://blogs.msdn.microsoft.com/wael-kdouh/2017/06/26/enabling-drive-sharing-with-docker-for-windows/).
