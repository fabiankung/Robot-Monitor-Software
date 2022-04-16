# Robot-Monitor-Software
1. This is a Windows based software that is used to communicate with a mobile robot and display the real-time telemetry information from the robot in x-y plots, bar graphs and other formats. 

2. The software is written in Visual Basic .NET, with Visual Studio 2019 community edition or newer version being used.

3. The codes and related resources are archived as Visual Studio project template, thus you can use Visual Studio to unarchive the ZIP file and rebuild the software.

4. The software uses Windows serial port library to access and external serial device (which is the robot in this case). The baud rate is set to 115200 bps and each data packet consists of 64 bytes in the following format:

Byte 0 = ID of machine.

Byte 1 = Identification of data packet, binary data in this case.

Byte 2 = 8-bits positive integer.

Byte 3 = 8-bits positive integer.

Byte 4 = 8-bits positive integer.

Byte 5 = 8-bits positive integer.

Byte 6 = 8-bits positive integer.

Byte 7 = 8-bits positive integer.

Byte 8 = 8-bits positive integer.

Byte 9 = 8-bits positive integer.

Byte 10 = 8-bits positive integer.

Byte 11 = 8-bits positive integer.

Byte 12 = 8-bits positive integer.

Byte 13 = 8-bits positive integer.

Byte 14-15 = 16 bits positive integer in [high byte][low byte] format.

Byte 16-17 = 16 bits positive integer in [high byte][low byte] format.

Byte 18-19 = 16 bits positive integer in [high byte][low byte] format.

Byte 20-21 = 16 bits positive integer in [high byte][low byte] format.

Byte 22 = Robot status flags.

Byte 23 = Change in distance from previous time-step, Delta_distance travelled in ticks. 
The delta_distance is between -127 to 128 ticks, add with +127 before being transmitted.

Byte 24-25 = 16 bits positive integer indicating current robot heading, in degree 0-360, 
in [high byte][low byte] format.

Byte 26 = Not used.

Byte 27-34 = 8-bits positive integer corresponding to on-board FFT output.

Bytes 35-63 = Not used (reserved for future).

6. See https://www.youtube.com/watch?v=5212JX8CQ5g for a demonstration of the software with a mobile robot.


