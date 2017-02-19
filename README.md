# electronjsSample
This application demonstrates the building of application with electronjs

## Getting started:
Get the sample electronjs app from the repository:
https://github.com/electron/electron-quick-start
Follow the steps on the repository
1. Clone this repository
git clone https://github.com/electron/electron-quick-start
2. Go into the repository
cd electron-quick-start
3. Install dependencies
npm install
4. Run the app
npm start

## Building the application:
Build the application using the web technologies and the nodejs frameworks.
The inbuild development tools can be opened programatically by "mainWindow.webContents.openDevTools()"
Or "Ctrl+Shift+I" will open developmenttools

## Packaging:
The electron community provides a node module for packaging the application to different platforms
https://github.com/electron-userland/electron-packager
Some help across the community:
https://www.christianengvall.se/electron-packager-tutorial/
https://github.com/electron-userland/electron-packager

Initially to build packages, it will download the packages. Further repeatition of builds will not require the download
To build for windows:
electron-packager . --overwrite --asar=true --platform=win32 --arch=ia32 --icon=images/treeIcon.ico --prune=true --out=release-builds --version-string.CompanyName=CE --version-string.FileDescription=CE --version-string.ProductName=\"Image-Viewer\"

To build for MAC:
electron-packager . --overwrite --platform=darwin --arch=x64 --icon=images/treeIcon.icns --prune=true --out=release-builds

To build for Linux:
electron-packager . --overwrite --platform=linux --arch=x64 --icon=images/treeIcon.png --prune=true --out=release-builds

Troubles with packaging:
1. If your development environment is windows, then the packaging of applications must be done in admin mode. But due to its file system not supporting symbolic links, it is recommended not to package the mac or linux packages on windows platform. Workarounds are available in the community support.
2. If your development environment is linux, then packaging for linux and MAC will be seamless. To transfer the application via USB, the USB must be formatted to a file system that supports symbolic links. Or else the file packaged release can be compressed to a tar file to export.
But, buiding the windows packages will give missing additional module support. Workarounds are available, though building the windows package on windows environment would be easy.


