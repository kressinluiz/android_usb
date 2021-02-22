# USB - Android

- Android support USB through two modes:
  - USB Accessory: connects to hardware that implements the Android Acessory Protocol. The external hardware act as the USB Host. This gives Android-powered devices that do not have host capabilities the ability to interact with USB Hardware. USB Acessories must be designed to work with android-powered devices and must adhere to the Android accessory communication protocol.
  - USB Devices ( Host Mode ): Android-powered devices acts as the host and powers the bus.

# USB Host

USB Host Mode: powers the bus and enumerates connected USB devices.

## USB Host APIs (inside ANDROID.HARDWARE.USB package)

Classes:
  - UsbManager: Allows to enumerate and communicate with connected USB devices.
  - UsbDevice: Represents a connected USB device and contains methods to access its identifying information, interfaces and endpoints.
  - UsbInterface: Represents an interface of a USB Device, which defines a set of functionality for the device. A device can have one or more interfaces on which to communicate.
  - UsbEndpoint: Represents an interface endpoint, which is a communication channel for this interface. An interface can have one or more endpoints, and usually has input and output endpoints for two-way communication with the device.
  - UsbDeviceConnection: Represents a connection to the device, which transfer data on endpoints. This class allows to send data back and forth sync or async.
  - UsbRequest:  Represents an **asynchronous** request to communicate with a device through a UsbDeviceConnection.

Usage:
  1) **UsbManager** to retrive the desired **UsbDevice**.
  2) Find the appropriate **UsbInterface**.
  3) Find the **UsbEndpoint** of that **UsbInterface** to communicate on.
  4) Open a **UsbDeviceConnection** to communicate with the **UsbDevice**.

