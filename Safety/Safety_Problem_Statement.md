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

The dataset could be downloaded from the link: 
https://1drv.ms/u/s!AlAZTiEu2oI4gXxuDXofUxNfjVNw?e=F0qZ5l

# Problem Statements:

1. Which feature has a high impact on indicating dangerous trips?
2. How does the driving behaviour change over time (second) for normal trips and dangerous trips? What are the behaviour difference?
3. Given the telematics data for new trips,  derive a model to detect if the trip is a dangerous trip.
