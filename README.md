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

To test, start Docker, then open a terminal or command prompt and enter `docker pull hello-world`. If that succeeds, then Docker _is_ able to pull images and that is not the problem.

**Note**: Windows 7 and Windows 10 Home users, use the Docker Quickstart Terminal.
