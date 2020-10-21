---
title: "Deep Dive Asp.Net Mvc Part1"
date: 2020-10-20T23:25:25-04:00
draft: false
---

Recently I started exploring the Asp.Net source code. I will writing my finding in this Deep Dive Asp.Net Mvc series.

Today we will prepare the source code, specifically download the source code, build and run a sandbox web application that comes with Asp.Net Mvc project. This is needed to follow the code examples from feature posts. The sandbox project allows us to debug and step into breakpoints.

There is very detailed page for building the Asp.Net project from the source - [https://github.com/dotnet/aspnetcore/.../BuildFromSource.md](https://github.com/dotnet/aspnetcore/blob/master/docs/BuildFromSource.md). Quick and short form for this page would look like this:

### Step 1. Clone the source code

```
git clone --recursive https://github.com/dotnet/aspnetcore
```

### Step 2. Install pre-requisites (Win)
* Prepare Visual Studio
this command makes sure Visual Studio will have all the required components for the development
```
PS> ./eng/scripts/InstallVisualStudio.ps1  [-Edition {Enterprise|Community|Professional}] [-Channel {Release|Preview}]
```
* NodeJS
```
choco install nodejs
```
* Yarn
```
npm install -g yarn
```
* Install JDK
 
 Option 1: OpenJDK [here](https://jdk.java.net/)
 
 Option 2: Oracle's JDK [here](https://www.oracle.com/technetwork/java/javase/downloads/index.html)
 
 Option 3: or use script that comes with source code:
```
PS> ./eng/scripts/InstallJdk.ps1
```

### Step 3. Build the repo
This CLI command from the root directory will restore and build solutions.
```
.\build.cmd
```

### Step 4. Run sandbox application
To open Asp.Net Mvc project in the Visual Studio:
```
.\startvs.cmd .\src\Mvc\Mvc.sln
```
```startvs.cmd script will setup environment variables needed for the VS to work with the source code.```

Set MvcSandbox project as default project:
![vs sandbox project](https://media.publit.io/file/antonbaasanblog/vs-asp-net-mvc-sandbox.png)

This should be good to run the project in the Debug more and explore the source code.
