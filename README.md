# Android-nRF-Mesh

## About

An early alpha version of the Bluetooth Mesh specification, this library will allow you to provision and configure bluetooth Mesh compliant nodes.

This is a preview version that has missing features and capabilities that are going to be added in the near future. 

nRF Mesh for Android is supported on Android devices running Android 4.3 and onwards.

### Features
1. Supports provisioning with OOB Numeric
2. Adding App Key
3. Binding added app keys to Models
4. Setting publish address
5. Subscribing/Unsubscribing to and from group addresses


## Requirements

* Android Studio
* An Android device with BLE capabilities

## Optional

* nrf52832 based Development Kit(s) to test the sample firmwares on.

## Installation

* Open 'Example/nRf Mesh Provisioner'
* Connect an Android device.
* Build and run project.
* To be able to quickly start testing, use the bundled firmwares directory named `ExampleFirmwares` that includes a light server (Light source) and a light client (Switch) firmwares. those firmwares will work on a `nrf52832` DevKit.

## How to include it in your own project

#### Manual

Clone this project and add *ble* module as a dependency to your project:

1. In *settings.gradle* file add the following lines:
```groovy
include ':meshprovision'
project(':meshprovision').projectDir = file('../Android-Mesh-Library/meshprovision')
```
2. In *app/build.gradle* file add `implementation project(':meshprovision')` inside dependencies.
3. Sync project and build it.

See example projects in this repository.

#### Sample

```java
        MeshManagerApi mMeshManagerApi = MeshManagerApi.getInstance(this);
        mMeshManagerApi.setProvisionerManagerTransportCallbacks(this);
        mMeshManagerApi.setProvisioningStatusCallbacks(this);
        mMeshManagerApi.setConfigurationCallbacks(this);
```

## Author

Mobile Applications Team, Nordic Semiconductor ASA.

Contact: roshanrajaratnam <roshan.rajaratnam.@nordicsemi.no>

## License

The Scanner Compat library is available under BSD 3-Clause license. See the LICENSE file for more info.
