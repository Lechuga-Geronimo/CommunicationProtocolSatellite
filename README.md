# Simulation of Communication Protocol between a Satellite and Ground Station for Telemetry and Command.
This is a software project that emulates the communication between a Ground Station and a satellite in orbit in order to recreate the conditions under which they exchange data for processing.

## Description. 

In this project, a project was developed that emulates the communication between a Ground Station and a satellite in orbit in order to recreate the conditions under which they exchange data for processing.

### Data Package Structure. 

The data package includes:

*4 bytes of satellite identification, indicating the start of data transmission to ground.

*1 temperature byte, indicating the current temperature of the satellite.

*1 byte reserved for future protocol expansion.

*2 bytes of payload, which includes data such as atmospheric pressure.

*1 validation byte, where it is verified that the data received is consistent with that sent by the satellite.

## Operation. 

The previous structure can be presented at any time on the Rx FIFO port, however, it can only take one byte at a time, so it is necessary to create a buffer of dynamic size consistent with the size of the packet. Packages may or may not have the established size; and may be preceded or followed by bytes with incongruent or erratic information.

Once the information is validated, the payload and temperature bytes are downloaded and stored for later processing and conversion to other units.

The program must be build completely in C++ and using only standard libraries. A set of unit test must be made for the most common situations (incorrect package, incorrect dimension, null bytes, etc.).
