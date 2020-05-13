# The Telematics Dataset

The telematics data collected during driving trips are useful to detect if the trip is dangerous and has high crash / accident probability.

Data Schema (Field & Description):

	- bookingID: trip 
    - accuracy: accuracy inferred by GPS in meters
    - bearing: GPS bearing in degree
    - acceleration_x: accelerometer reading at x axis (m/s2)
    - acceleration_y: accelerometer reading at y axis (m/s2)
    - acceleration_z: accelerometer reading at z axis (m/s2)
    (Acceleration determines the acceleration / vibration of the device in motion. Each of the axis can be thought of as a different sensor even though they reside on the same physical chip)
    - gyro_x: gyroscope reading in x axis (rad/s)
    - gyro_y: gyroscope reading in y axis (rad/s)
    - gyro_z: gyroscope reading in z axis (rad/s)
    (Gyroscope data determine the orientation of the device relative to earth's gravity)
    - second: time of the record by number of seconds
    - speed: speed measured by GPS in m/s
    - label: tags to indicate dangerous driving trip (0: Normal trip / 1: Dangerous trip)  

The dataset can be downloaded here: [labels (300KB CVS file)](https://msftgrab.z23.web.core.windows.net/safety/labels/part-00000-e9445087-aa0a-433b-a7f6-7f4c19d78ad6-c000.csv) and [features (ten 190MB CSV files)](https://msftgrab.z23.web.core.windows.net/safety/features/index.html)

# Problem Statements:

1. Which feature has a high impact on indicating dangerous trips?
2. How does the driving behaviour change over time (second) for normal trips and dangerous trips? What are the behaviour difference?
3. Given the telematics data for new trips,  derive a model to detect if the trip is a dangerous trip.
