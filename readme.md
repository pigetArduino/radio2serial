Radio 2 Serial
----
This arduino can send and receive multiples 433Mhz types of radio communications.   
Protocols managed: RemoteTransmitter (old)/NewRemoteTransmitter (new)/RadioHead (text)

* Control Cheap Power Outlets
* Send text between arduino/raspberry pi

![radio2serial](https://github.com/pigetArduino/radio2serial/blob/master/doc/radio2serial.jpg)
![radio2serial_internal](https://github.com/pigetArduino/radio2serial/blob/master/doc/radio2serial_internal.jpg)

This technology (433Mhz) isn't really reliable but this is pretty useful if you want to turn on/off power outlets remotely and cheaply (use rfm69/95 if you want secure communication)   

# Instructions
* Download radio2serial.madnerd.org
* Copy radio2serial / libraires into arduino sketchbooks (Documents/Arduino)
* Upload code

# Test
Red led should be turned off at startup
* Red led blink fast : RX error
* Red led blink slow : TX error

# Usage
* Open serial monitor : 115200bauds

## Startup
At startup, the arduino will check all components, and identify itself, and display components status
{"file":"radio2serial.ino","url":"github.com/pigetArduino/radio2serial","ver":"0.71","pins":"tx:10;rx:2","state":"tx:1;rx:1"}

## Receive radio
Data are received in JSON (ex: "{"data" : "/radio/text/Hello World"}")

## Send radio
send RadioHead code "Hello world"
```
//radio/text/Hello World
```
turn on new radio "address:1234 unit:1" 
```
/radio/new/1234/1/on
```
turn off new radio "address:1234 unit:0"
```
/radio/new/1234/0/off
```
dim new radio to 8/16 "address:1234 unit:2"
```
/radio/new/1234/2/8
```

```
// /radio/old/123456 : send old radio code "123456"
```

# Components
* Receiver : ASK Receiver Super-heterodyne  OOK RF - 4€
* Transmitter : ASK transmitter - 2€
* Arduino nano ch340g - 3€
Cost: 10€

# Wiring
![Pinout](https://raw.githubusercontent.com/pigetArduino/radio2serial/master/doc/schema_radio2serial.png)


# 3D models
[Show Models](https://raw.githubusercontent.com/pigetArduino/radio2serial/master/3D/)

# Additional License

RadioHead Library

|Author                 | Ayrspace                                         |
|:---------------------:|:------------------------------------------------:|
|License                | MIT                                              |
|Donation               | http://www.airspayce.com                         |
|Documentation (ENGLISH)| http://www.airspayce.com/mikem/arduino/RadioHead/|


433MhzForArduino Library

|Author                 | Randy Simons                                                |
|:---------------------:|:-----------------------------------------------------------:|
|License                | MIT                                                         |
|Donation               | Bitcoin: 1Ar433MfHWV7a4yGj3avg3dpTRzHGvT4PP                 |
|Documentation (ENGLISH)| https://bitbucket.org/fuzzillogic/433mhzforarduino/wiki/Home|

