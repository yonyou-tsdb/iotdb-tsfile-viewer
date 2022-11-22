<!--

    Licensed to the Apache Software Foundation (ASF) under one
    or more contributor license agreements.  See the NOTICE file
    distributed with this work for additional information
    regarding copyright ownership.  The ASF licenses this file
    to you under the Apache License, Version 2.0 (the
    "License"); you may not use this file except in compliance
    with the License.  You may obtain a copy of the License at

        http://www.apache.org/licenses/LICENSE-2.0

    Unless required by applicable law or agreed to in writing,
    software distributed under the License is distributed on an
    "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY
    KIND, either express or implied.  See the License for the
    specific language governing permissions and limitations
    under the License.

-->

# iotdb-tsfile-viewer
[![Main Mac and Linux](https://github.com/apache/iotdb/actions/workflows/main-unix.yml/badge.svg)](https://github.com/apache/iotdb/actions/workflows/main-unix.yml)
[![Main Win](https://github.com/apache/iotdb/actions/workflows/main-win.yml/badge.svg)](https://github.com/apache/iotdb/actions/workflows/main-win.yml)
# Outline
- [Introduction](#Introduction)
- [Quick Start](#quick-start)
    - [Prerequisites](#Prerequisites)
    - [Compile](#Compile)
- [Maintainers](#Maintainers)
- [Contributing](#Contributing)
- [Contributors](#Contributors)
# Introduction
tsfile-viewer is a tool to view TSFILE. Currently, we support bit granularity parsing of TsFile and provide visual display.  
we have three modules in the project
- tsfile-viewer-core: core jar package project
- tsfile-viewer-web: web viewer backend,When you execute the mvn install command in the parent project, it will package the front-end project code together
- tsfile-viewer-web-frontend: web viewer frontend

1. overview: This tool can Clearly display information of each part of TsFile, details are as follows:
    1. The versionNumber.
    2. The data layer: contains details of each level and statistic information.

       i. ChunkGroup

       ii. Chunk

       iii. Page

       iv. Point
    3. The index layer: displayed in a tree like structure then you can easily view the overall structure of the secondary
       index(entity and measurement granularity).

2. Timeseries and measurement search: In addition to displaying data, we also provide the function of querying TimeSeries by keyword. There is a linkage
   between the index layer and the data layer, it can quickly locate the desired TimeSeries with details.

<!-- 3. The encoding and compression type of a timeseries analysis: tsfile-mt provide the analysis of the current timeseries encoding and compression. In addition, tsfile-mt also provide the analysis
   of the combination of various encoding and compression types of the timeseries. -->

# Quick Start
## Prerequisites
To use the tool, you need to have:
1. Java >= 1.8 
2. Maven >= 3.6  

Of course, you will also notice that there is a front-end project in the project. When you execute the mvn install command, the project will download its corresponding environment, and you don't have to configure the environment separately for it.
## Compile
You can download the source code from:
```
git@github.com:apache/iotdb-tsfile-viewer.git
https://github.com/apache/iotdb-tsfile-viewer.git
```
Under the root path of iotdb-tsfile-viewer:
```
mvn clean install
```
then you can start this tool in the tsfile-viewer-web project 

```
java -jar iotdb-tsfile-viewer-web-0.13.2-SNAPSHOT.jar
```

The default url is
```
http://localhost:8080/
```
You can modify the port through the file
```
iotdb-tsfile-viewer\tsfile-viewer-web-frontend\config\config.js
tsfile-viewer-web\src\main\resources\application.yml
```
# Maintainers

# Contributing
Feel free to dive in! Open an issue or submit PRs.
# Contributors
This project exists thanks to all the people who contribute.
