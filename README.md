# GPS Location Mapper

This MATLAB script reads GPS data from a serial port connected to a GPS dongle, retrieves the nearest address using the OpenStreetMap Nominatim API, and creates a map centered on the GPS coordinates with the nearest address as the title.

## Requirements

- MATLAB (version R2016a or later)
- Mapping Toolbox
- Active internet connection

## Setup

1. Connect your GPS dongle to your computer's serial port.

2. Open the script in MATLAB.

3. Modify the following variables in the script according to your setup:
   - `serialPortName`: Set it to the name of the serial port connected to your GPS dongle (e.g., "/dev/tty.usbmodem1101").
   - `baudRate`: Set it to the baud rate of your GPS dongle (default is 9600).

4. Save the script.

## Usage

1. Run the script in MATLAB.

2. The script will start reading GPS data from the specified serial port.

3. Once a valid $GPRMC sentence is received, the script will:
   - Parse the GPS coordinates (latitude and longitude) from the sentence.
   - Make a request to the OpenStreetMap Nominatim API to reverse geocode the coordinates and obtain the nearest address.
   - Create a new figure window and display a map centered on the GPS coordinates.
   - Plot the GPS coordinates as a red filled marker on the map.
   - Set the title of the map to the nearest address.

4. After creating the map, the script will close the serial port and end.

## Notes

- The script requires an active internet connection to make requests to the OpenStreetMap Nominatim API.

- The script uses the Mapping Toolbox to create the map. Make sure you have the Mapping Toolbox installed in your MATLAB environment.

- The script is set to read GPS data until it receives a valid $GPRMC sentence. If you want to continuously update the map with new GPS coordinates, you can modify the script accordingly.

- The script assumes that the GPS dongle sends data in the NMEA format. If your GPS dongle uses a different format, you may need to modify the parsing logic in the script.

## Troubleshooting

- If the script fails to read data from the serial port, check the following:
  - Make sure the GPS dongle is properly connected to the specified serial port.
  - Verify that the baud rate in the script matches the baud rate of your GPS dongle.
  - Ensure that the GPS dongle is powered on and receiving a valid GPS signal.

- If the script encounters an error while making a request to the OpenStreetMap Nominatim API, check your internet connection and make sure you have access to the API.

- If the map is not displayed correctly, ensure that you have the Mapping Toolbox installed and properly configured in your MATLAB environment.

## License

This script is provided under the [MIT License](LICENSE).

Feel free to modify and adapt the script according to your needs.