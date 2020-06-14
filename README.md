# Team Plasma
We are Team Plasma. Our team is made up of 3 undergraduate Engineering students from the National University of Singapore who aim to help the community through technology. -Joshua Nathanael, Nathania Santoso, Philicia Marvella-

1. Problem tackled 
We will be solving the first problem relating to emergency medical services. Our target population will be elderly without next-of-kin who live alone. We will be focusing on the detection of two potentially fatal incidents which require emergency response, cardiac arrest and fall, when there is no witness around the elderly during the incident. We assume that our target population will be housed within the same area in the HDB and an external party will hold the master key to their flats. 

2. Pitch Video


3. Architecture implemented in prototype
Sensor --> Arduino --> (Serial) --> Node-Red and Tensorflor model --> Node-Red Dashboard

4. Detailed solution
We plan to make a compact wearable device that is placed in the chest area, fastened to the body using a strap. The device will be connected to the myResponder application through wifi. The device will contain personal information of the wearer (name and address), gps and two sensors. The first sensor is able to detect when a body is suffering from symptoms of cardiac arrest 10 minutes prior and the second sensor is able to detect when a body falls. When cardiac arrest symptoms are detected by the device, a notification will be released in the myResponder app, informing nearby Community First Responders (CFRs) about a potential cardiac arrest patient and requesting for their aid. Meanwhile, when the device detects a fall, the device will first vibrate and sound an alarm for 20 seconds, in which the wearer has to respond by pressing a button on the device. If no response is given, a notification will then be released in the myResponder app, informing nearby CFRs about the fall incident. 

We use ECG recordings dataset from patients suffering from cardiac arrest to train our machine learning model in IBM Watson Machine Learning using AutoAI experiment, which will then be used to detect whether the device wearer’s body is suffering from cardiac arrest symptoms. The model will be used in Node-Red to be fed with ECG data. Our device will also use IBM Watson IoT to connect the device and the myResponder app. 

5. Getting Started
Arduino: 
a. Install Arduino IDE
b. Prepare the Arduino Uno and a breadboard
c. Connect the ECG module to arduino. The module will need 5V, Ground and Analog Output.
d. Connect the MPU6050 to the arduino. The module will need 3.3V, Ground, SDA, and SCL.
e. Before connecting power, attach the electrode in the appropriate place. Note: the L and R (yellow and red color probe) must be near the heart to detect the heartbeat. Illustration:

We should have used the ESP8266 to communicate using Wifi but due to the lack of a logic level converter, we are unable to use the module for communication. Therefore we used a normal UART peripheral from arduino to communicate directly with the computer (IBM cloud).

Node-Red:
a. Install Node-Red locally in computer or in IBM Cloud
b. For Node-Red installed in local computer, add Node-Red to Path (environment variables) for it to be accessed from any file directories
c. Install the needed palette using “npm install” command.
d. When you are going to run Node-Red, type “node-red” in Command Prompt. 
e. The access to your Node-Red will be given in the console.
f. Build the flow.
g. Deploy and open the dashboard. You will be able to view ECG data and get an alert if falling is detected.
