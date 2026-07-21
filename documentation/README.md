# Documentation

Will use for larger change updates and timeline.

# Formulas
- D<sub>shoulder</sub> = D<sub>tubeID</sub> - 2C (where C is the clearance)

# Primary Timeline

(7/21/26) - I've reached the biggest milestone so far, battery-powered data collection. Now the entire circuit (pre-soldered) will collect data as soon as the battery is turned on, completely seperate from the computer. I've decided the next step is to get the circuit working with a perfboard, which I can then build around for the sled.

The perfboard is now fully soldered and connects the barometer and accelerometer to the Nano. Now I need to design the avionics sled (with plenty of holes and connection points) and finish the soldering of the microSD adapter and battery.

#

(7/20/26) - So far, I've hooked up the barometer and accelerometer to a breadboard and have gotten data. The format output by the serial monitor should be easily feed into the SD card which I am now working on setting up. After hooking up all three parts, the Nano now outputs data from the accelerometer and barometer, along with verifying the microSD's installation. Now when I input the sensor code, pause, and switch it to the read code, it'll dispense data from the microSD. This includes time, pressure, temperature, degrees/s, and average G-force. I will publish the final design with soldering on the perfboard once that is completed (it's a mess of wires right now).

Now for the avionics sled. The main issue is balancing it's weight and the stability of  the rocket itself. I have purposefully waited to print the bottom of the body tube because I'll need to change the shape of the fins. I'm starting the nose cone print now.

The nose cone came out well, but sanding will be needed as usual. To finish up today, I'm starting some sketches for the avionics bay and messing with some of the 3D models to fit the OpenRocket design. The perfboard comes over night, so I should be able to finish the entire avionics bay and have (hopefully) most of the rocket printed by tomorrow night.


#

(7/19/26) - I soldered both the BMP280 (barometer) and MPU6050 and began running tests on Arduino IDE. The barometer successfully output data, specifically on temperature, altitude, and pressure, taking an average of all. I'll have to buy perfboard to solder all the components together, but it seems like that is the last material I'll need.

#

(7/18/26) - Before I begin soldering, I need to think about how I'm going to design the avionics sled. This is my first time designing an avionics system, so I'll need to be careful as to not make it too big or small, for example. It needs to be lightweight and easy to take in and out, since I'll likely be tinkering for a bit longer than experienced rocketeers. 

I've began modeling the prototype rocket, starting with the nose cone. Since this rocket will contain a designated avionics bay, a bulkhead will need to be placed to seperate the hot gases from the delicate electronics and also provide a place for force to push the upper part of the rocket off. I spent a while thinking about the connection for the nylon/kevlar to both the upper and lower stages of the rocket. To ensure the parachute ejects cleanly, it seems like the best solution is to design the top centering ring to be thicker and include two holes for the kevlar to attach to, then connect the linked nylon into a crossbar without holes right below the top bulkhead. This setup ensures almost nothing is in the way of the gas and makes it a bit easier for me to secure the shock cord.

As I switch between coding, modeling, and OpenRocket simulations, I notice my diameter being too small for a comfortably fitting avionics sled. It's probable that the completed sled would fit, but I want some extra room since this is my first time making an avionics-fitted rocket. The diameter is now 50mm, which adds mass but also forces the optimum delay to be closer to the E30-7T's charge delay, and slows down the chute deployment speed.

The Rocket has now been mostly modeled. It is currently missing the avionics sled and rail system and centering rings. I've also settled on a design for the paint scheme. Tommorow, I'll solder and start coding. I had originally intended to code today, but it looks like I need to solder to start doing that. As the components come in, I'll start making my first attempts at designing the avionics sled and merge that into my prototype design for the Advent 2. Looking back at the previous design, the 45mm design was much better for flying, but I still have worries about fitting the avionics. For now, I'll wait to design the sled, then fit the rocket around it. if I can go back to the 45mm design, that's great, but it won't be the end of the world to use the 50mm one.

![Onshape Prototype](images/Prototype%201.png)
![KSP Model](images/KSP%20Advent)



#

(7/17/26) - Beginning the design on OpenRocket and mass/dimension estimation. Currently, the mass is ~300g with rudimentary dimensions. This mass is extremely high. According to Estes, the D12-3 motor can carry a mass of around 396g. I'd have to squeeze the chutes, avionics, fins, engine, and other random componenets in less than 100g. Redesign necessary.

With major redesigns, the current loaded mass of the rocket is 505g. At first, this seemed usable using a F15-4 engine, but it is apparent that the liftoff velocity is too low. Without a longer rod or a more powerful engine, it is likely that the rocket will be too unstable. A rule of thumb is to ensure your rocket is atleast 4x faster than the wind. In this case, the wind would need to be below 6mph since the vehicle would launch at ~8.8m/s.

At this point, I could either make the rocket light and buy an Estes F-class engine and longer launch rail, or buy a much more powerful engine and use a club's launch rail. Both options are expensive, and I don't know if either will work.

![The first iteration of the Advent 2](images/OpenRocket%201.png)
Above is the most effective design I could create without a majority of the physical components. I expect to slowly develop a more precise and effective design as the parts ship in and allow me to measure exact mass. Below is the full OpenRocket simulation data (assuming ~65g for the avionics, which is a guesstimate).
![OpenRocket Data](images/OpenRocket%202.png)

As I wait for each part to arrive, the next goal is to finish the coding and complete the avionics sled. This includes the physical components of the Arduino board and sled, along with the code to be fed into the board prior to the first launches. The Advent 2 will include an accelerometer, barometer, and an SD card for data storage. The goal of these instruments is to create functional data from the launch.

My first issue is with the SD card adapter. It's maximum input is 5V, while my battery gives it 9V. I hadn't yet considered switching the battery, but it is beneficial to do so for reasons beyond the adapter itself. My specific 9V battery weights ~35g, which is the single heaviest component of my avionics bay. By purchasing a smaller battery (currently seems like a 3.7v 500mAh LiPo), I can save around 20g.

My final choice was a combination of all the things I need. A less massive battery pack with 5V and 3.3V ports, (at 2.4A) an on/off switch, and a USB-C charger. This surprised me, since it saved a massive amount of money. For the final product, it should be a lighter and more effective option, as it will likely create less clutter on the avionics sled. I'll need to wait a week or two for the AeroTech/Estes components to arrive, but I'll be launching within a month. Tomorrow, my main focus will be the coding. I am not sure if soldering will be required, but it'll be my main goal to create the backbone for the avionics either way.
