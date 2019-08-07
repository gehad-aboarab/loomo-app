# Loomo Robot Application
Android application to run on Segway's robot Loomo to enable navigation through a indoor map fed to the application by a server.

This system aims to achieve semi-autonomous robot movements by using BLE beacons to localize the user, and visual odometry, using a grid-based map, to localize the robot within its surroundings. A user within the indoor environment can request the robot’s assistance, whose location would be determined by collecting signals received from the surrounding beacons. Upon construction of the grid-based map, the robot in turn pinpoints and localizes the user on the map and navigates towards their location. The user can further request guidance to certain destinations defined within the map, and the robot similarly builds a route to that destination and navigate through it with additional obstacle detection and avoidance techniques.

The application running on the Loomo is an Android application that handles the robot's decisions such as routing, navigation, speech, recognition and constructing the array that contains the map. This application communicates with a server built using Node.js that handles communication between the sub-systems. All communications is carried out over Message Queuing Telemetry Transport (MQTT) protocol. The server also communicates with an Android mobile application that allows the user to request assistance. Additionally, a Raspberry Pi is used to connect external ultrasonic sensors to the robot to detect more obstacles along its route. The Raspberry Pi also communicates with the server and the server sends the instructions to the robot accordingly.

Works alongside: https://github.com/gehad-aboarab/loomo-mobile-app