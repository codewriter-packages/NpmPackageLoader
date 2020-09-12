# Npm Package Loader [![Github license](https://img.shields.io/github/license/codewriter-packages/NpmPackageLoader.svg)](#)

Npm offers a convenient way to manage packages. However, 
some packages are too large and cannot be uploaded to the repository,
 or require installation directly into the project's Assets folder.
 
 Npm Package Loader allow you to archive some assets into a standard 
 `unitypackage` package and embed it into npm package or upload 
 on the ftp server This assets will be automatically downloaded 
 and unpacked directly into the project.

### How to create package?

#### 1. Install Npm Package Loader and [Npm Publisher Support](https://github.com/codewriter-packages/NpmPublisherSupport)
#### 2. Create package.json
Might look something like:
```
{
  "name": "com.codewriter.npm-package-loader-demo-sdk",
  "displayName": "Npm Package Loader DEMO",
  "description": "Do not use",
  "version": "0.1.0",
  "unity": "2019.1",
  "author": "Vanifatov Vlad (https://github.com/vanifatovvlad)",
  "dependencies": {}
}
```

#### 3. Create UnityPackage Loader asset
[![Create asset](https://user-images.githubusercontent.com/26966368/62519337-04367a00-b834-11e9-9279-327948c65fa0.png)](#)

Asset must be placed next to `package.json`

#### 4. Setup asset
[![Asset content](https://user-images.githubusercontent.com/26966368/62519851-0fd67080-b835-11e9-9cd0-d018c4a6bfc7.png)](#)

You can add individual files or entire folders to `Packed Assets`.

#### 5. Add dependency

`External loaders` section will appear in the` Npm Publish` window 
after creating the Loader. Add `npm-package-loader` dependency 
using the` Add` button and publish the package. 
Then it can be installed from the npm repository.

> If `npm-package-loader` dependency is marked as Unknown, 
> you need to check that Npm Package Loader package is installed correctly 
> or manually specify the current version of the package in `package.json`.

[![Install deps](https://user-images.githubusercontent.com/26966368/62523535-a35f6f80-b83c-11e9-9504-677e40907eca.png)](#)

### How to install package?

Created package can be downloaded from the npm registry. 
A confirmation window for downloading additional files 
should appear automatically after installing the package.

[![Install package](https://user-images.githubusercontent.com/26966368/62521665-c0923f00-b838-11e9-805a-f6fd1920bf2a.png)](#)

> Window can be manually opened from `Window / Check Npm Package Loaders` menu

Additional assets will be downloaded and unpacked after confirmation.

[![Import package](https://user-images.githubusercontent.com/26966368/62522173-cccacc00-b839-11e9-9052-3a99a31370aa.png)](#)

### Install
Library distributed as git package ([How to install package from git URL](https://docs.unity3d.com/Manual/upm-ui-giturl.html))
<br>Git URL: `https://github.com/codewriter-packages/NpmPackageLoader.git`

### FAQ

#### What is the Assets/Packages folder created for?
This is a system folder needed to keep track of installed packages.

#### How do I update a package to a new version?
The new version can be downloaded via npm. You should automatically be prompted to update additional files after updating the npm package.

#### How do I reinstall a package?
You can remove the asset subfolder from Assets/Packages and execute the command `Window/Check Npm Package Loaders`
