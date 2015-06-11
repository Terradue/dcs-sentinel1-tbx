## Developer Cloud Sandbox template for InSAR with Sentinel-1 Toolbox



## Quick link
 
* [Getting Started](#getting-started)
* [Installation](#installation)
* [Submitting the workflow](#submit)
* [Authors](#authors)
* [Questions, bugs, and suggestions](#questions)
* [License](#license)

### <a name="getting-started"></a>Getting Started 

To run this application you will need a Developer Cloud Sandbox, that can be either requested from:
* ESA [Geohazards Exploitation Platform](https://geohazards-tep.eo.esa.int) for GEP early adopters;
* ESA [Research & Service Support Portal](http://eogrid.esrin.esa.int/cloudtoolbox/) for ESA G-POD related projects and ESA registered user accounts
* From [Terradue's Portal](http://www.terradue.com/partners), provided user registration approval. 

A Developer Cloud Sandbox provides Earth Sciences data access services, and helper tools for a user to implement, test and validate a scalable data processing application. It offers a dedicated virtual machine and a Cloud Computing environment.
The virtual machine runs in two different lifecycle modes: Sandbox mode and Cluster mode. 
Used in Sandbox mode (single virtual machine), it supports cluster simulation and user assistance functions in building the distributed application.
Used in Cluster mode (a set of master and slave nodes), it supports the deployment and execution of the application with the power of distributed computing for data processing over large datasets (leveraging the Hadoop Streaming MapReduce technology). 
### <a name="installation"></a>Installation

##### Using the releases

Log on the developer cloud sandbox. Download the rpm package from https://github.com/Terradue/dcs-sentinel1-tbx/releases (please replace \<version\> with the actual current version)

```bash
curl -L -O https://github.com/Terradue/dcs-sentinel1-tbx/releases/download/v<version>/dcs-sentinel1-tbx-<version>-ciop.x86_64.rpm
```
Install the dowanloaded package by running these commands in a shell:

```bash
sudo yum -y install dcs-sentinel1-tbx-<version>-ciop.x86_64.rpm
```

##### Using the development version

Log on the developer sandbox and run these commands in a shell:

```bash
sudo yum -y install sentinel1-tbx
cd
git clone git@github.com:Terradue/dcs-sentinel1-tbx.git
cd dcs-sentinel1-tbx
mvn install
```

### <a name="submit"></a>Submitting the workflow

Run this command in a shell:

```bash
ciop-run
```
Or invoke the Web Processing Service via the Sandbox dashboard.

#### Input description

This template application uses as input pairs (Master;Slave;Swath) of Sentinel 1 products. 

If you run this template application using local file URLs stored on a shared folder like /tmp, pass each input e.g.:

```
file:///tmp/S1A_IW_SLC__1SSV_20141103T195043_20141103T195057_003122_00395A_F396.zip;file:///tmp/S1A_IW_SLC__1SSV_20141127T195042_20141127T195056_003472_004117_2B48.zip;IW3
```
as a set of comma ( , ) separated pairs.


To discover and download master/slave Sentinel-1 products, use either the [ESA Sentinel-1 Scientific Data Hub](https://scihub.esa.int/dhus/) or the [Geohazards Thematic Exploitation platform](https://geohazards-tep.eo.esa.int).

You can also run this template application using catalogue URLs for input references, as provided by the [Geohazards Thematic Exploitation platform](https://geohazards-tep.eo.esa.int) e.g:

```
https://data.terradue.com/gs/catalogue/tepqw/gtfeature/search?uid=S1A_IW_SLC__1SSV_20141103T195043_20141103T195057_003122_00395A_F396;https://data.terradue.com/gs/catalogue/tepqw/gtfeature/search?uid=S1A_IW_SLC__1SSV_20141127T195042_20141127T195056_003472_004117_2B48;IW3
```
and then let the application download them from the Data Hub. 

Please contact the Operational Support team at Terradue in order to set your ESA Sentinel-1 Scientific Data Hub credentials on your Development Cloud Sandbox.

### <a name="authors"></a>Authors (alphabetically)

* Brito Fabrice
* D'Andria Fabio

### <a name="questions"></a>Questions, bugs, and suggestions

Please file any bugs or questions as [issues](https://github.com/geohazards-tep/dcs-template-insar-sentinel1/issues/new) or send in a pull request.

### <a name="license"></a>License

Copyright 2015 Terradue Srl

Licensed under the Apache License, Version 2.0: http://www.apache.org/licenses/LICENSE-2.0


