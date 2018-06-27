# cognitive-rehab-pepper

The aim of this project is to design a program for Softbank Robotic's Pepper to deliver a cognitive therapy program. It includes multiple cognitive games as Pepper gives encouragement and feedback to the user, and a connection with an external MySQL database and Django webpage to keep track of patient data. Recognition of yes/no head gestures and the pointing gesture is also possible with the Intel Euclid Developer Kit. The repository includes the following files:

-CognitiveRehabilitation: it contains the Choregraphe program of the full cognitive rehabilitation program. Requires downloading Choregraphe Suit from: https://community.ald.softbankrobotics.com
-GestureProcessingCodes: it contains the Python codes for processing head pose data for yes/no detection, processing of arm pointing gesture, and code for acquiring yes/no thresholds. Necessary to have realsense camera -the one used was the Intel Euclid Developer Kit- and the Librealsense and its samples installed within the Euclid ( https://github.com/IntelRealSense/librealsense and https://github.com/IntelRealSense/realsense_samples) 
-Django webpage: it contains the whole Django project for the design of the webpage. Requires to install all Django dependencies first: https://www.djangoproject.com/download/
-MySQL+nodeJS: the MySQL+nodeJS API to enable database access from Choregraphe. Download nodeJS first: https://nodejs.org/en/download/

