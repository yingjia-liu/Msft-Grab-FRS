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

# Feature Engineering Ideas
The acceleration and gyroscope features are representative of the driver's behaviour (Z - vehicle bouncing, X - braking/ acceleration, Y - turning speed) with correction process, lateral, longitudinal and vertical movements of vehicle could be derived with these features. 

Here lists some ideas for feature engineering processes:
1. Consider feature distance with speed & second
2. Consider feature speed for each axis with acceleration (xyz) with second
3. Consider feature radian for each axis with gyroscope (xyz) with second
4. Consider making axis interaction variables for both acceleration and gyroscope
5. Transform the accelerometer data: Vehicles move in one direction, only one of the axes will show large variation while others axes will typically have small fluctuation only. Therefore, you may summarise all three axes by finding the magnitude of acceleration using the formula: $\sqrt{ (acceleration_x)^{2} +  (acceleration_y)^{2} +  (acceleration_x)^{2}}$
6. Transform the gyroscope data: The distribution of gyroscope in all three axes are somewhat similar. Therefore, one idea is to use principal component analysis (PCA) to represent the triaxial gyroscope data in a lower dimension [What is PCA: https://towardsdatascience.com/a-complete-guide-to-principal-component-analysis-pca-in-machine-learning-664f34fc3e5a]

Reference links from previous challenge participants:
- https://github.com/FransdanaNadeak/GRAB-Data-Science/blob/master/GRAB%20-%20DATA%20SCIENCE%20(Safety).ipynb
- https://github.com/kfengtee/grab-aiforsea-safety/blob/master/documentation.ipynb
- https://github.com/Toukenize/grab_aiforsea_safety

# Problem Statements:

1. Which feature has a high impact on indicating dangerous trips?
2. How does the driving behaviour change over time (second) for normal trips and dangerous trips? What are the behaviour difference?
3. Given the telematics data for new trips,  derive a model to detect if the trip is a dangerous trip.
