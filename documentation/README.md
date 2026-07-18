# Documentation

Will use for larger change updates and timeline.

# Formulas & New Ideas
- D<sub>shoulder</sub> = D<sub>tubeID</sub> - 2C (where C is the clearance)

# Primary Timeline
(7/17/26) - Beginning the design on OpenRocket and mass/dimension estimation. Currently, the mass is ~300g with rudimentary dimensions. This mass is extremely high. According to Estes, the D12-3 motor can carry a mass of around 396g. I'd have to squeeze the chutes, avionics, fins, engine, and other random componenets in less than 100g. Redesign necessary.

With major redesigns, the current loaded mass of the rocket is 505g. At first, this seemed usable using a F15-4 engine, but it is apparent that the liftoff velocity is too low. Without a longer rod or a more powerful engine, it is likely that the rocket will be too unstable. A rule of thumb is to ensure your rocket is atleast 4x faster than the wind. In this case, the wind would need to be below 6mph since the vehicle would launch at ~8.8m/s.

At this point, I could either make the rocket light and buy an Estes F-class engine and longer launch rail, or buy a much more powerful engine and use a club's launch rail. Both options are expensive, and I don't know if either will work.

![The first iteration of the Advent 2](images/OpenRocket%201.png)
Above is the most effective design I could create without a majority of the physical components. I expect to slowly develop a more precise and effective design as the parts ship in and allow me to measure exact mass. Below is the full OpenRocket simulation data (assuming ~65g for the avionics, which is a guesstimate).
![OpenRocket Data](images/OpenRocket%202.png)

As I wait for each part to arrive, the next goal is to finish the coding and complete the avionics sled. This includes the physical components of the Arduino board and sled, along with the code to be fed into the board prior to the first launches. The Advent 2 will include an accelerometer, barometer, and an SD card for data storage. The goal of these instruments is to create functional data from the launch.
