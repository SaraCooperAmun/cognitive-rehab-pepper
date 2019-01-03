# cognitive-rehab-pepper

The aim of this project is to design a program for Softbank Robotic's Pepper to deliver a cognitive therapy program. It includes multiple cognitive games as Pepper gives encouragement and feedback to the user, and a connection with an external MySQL database and Django webpage to keep track of patient data. Recognition of yes/no head gestures and the pointing gesture is also possible with the Intel Euclid Developer Kit. The repository includes the following files:

-Choregraphe: it contains the Choregraphe program of the full cognitive rehabilitation program. 

-GestureProcessingCodes: it contains the Python codes for processing head pose data for yes/no detection, processing of arm pointing gesture, and code for acquiring yes/no thresholds. Necessary to have realsense camera -the one used was the Intel Euclid Developer Kit.

-Django webpage: it contains the whole Django project for the design of the webpage. 

-MySQL+nodeJS: the MySQL+nodeJS API to enable database access from Choregraphe.

## Pre-requisites

The following installations are requird to make use of this project.

- Download Choregraphe Suite from: https://community.ald.softbankrobotics.com

To use the Intel Euclid Developer Kit and gesture detection

-Install VNC Viewer to access Intel Euclid PC https://www.realvnc.com/en/connect/download/viewer/

-Install Librealsense package within the Euclid PC: https://github.com/IntelRealSense/librealsense

-Install realsense samples on Euclid PC https://github.com/IntelRealSense/realsense_samples

-On computer, make sure to have a Python IDLE that has:
	
	-Paramiko, to establish SSH connection to the Euclid: http://www.paramiko.org/installing.html
	
	-MySQLdb, to input gesture detections from the Python script to the MySQL database
https://mysqlclient.readthedocs.io/user_guide.html


To enable the use of Django webpage:

-Install Django for Python https://www.djangoproject.com/download/

-To plot charts install FusionCharts: https://www.fusioncharts.com/django-charts


To enable MySQL+NodeJS

-NodeJS https://nodejs.org/en/download/

-MySQL: https://dev.mysql.com/downloads/installer/

-HeidiSQL to easily visualise MySQL data: https://www.heidisql.com/download.php

## Running the demos

There are two main demos: the cognitive rehabilitation programme and the cognitive training app.

### Cognitive rehabilitation programme

1. To establish connection between Choregraphe and MySQL, open two separate command windows. 

            -cd to \myproject, within the “Django webpage” folder and run
	                 python manage.py runserver
			 
            -cd to \myapp, where app.js is stored, and run
	                  npm start
			  
     This will begin the nodeJS application that will enable connection between Choregraphe and the MySQL database

2. Open a web browser and go to 127.0.0.1:8000, which opens the webpage “Cognitive Rehabilitation with Pepper” to make sure the webpage is running

If the Intel Euclid Developer Kit is available and to test the game “ArmPositions” or the yes/no gesture detection for games “Mood”, “Q&A” or “Mem Machines” follow the following steps, otherwise skip to step 6.

3. Access Intel Euclid PC from an application such as VNC Viewer (address 10:42.0.1:5900)

4. On a command window, run the corresponding realsense_samples tutorial, and specify the txt file where the output will be printed.
	        
		-To run the head gesture detection script: 
	                        rs_pt_tutorial_2 >> test.txt
				
                -To run the arm gesture detection script:
                                rs_pt_tutorial_3 >> test.txt

5. Open the Python IDLE on PC.

                 -To run the head gesture detection script run:
                                HeadGestureProcessing.py 
				
                 -To run the arm gesture detection script run:
                                 ArmGestureDetection.py
				 
Note: it is important to notice that currently it is NOT possible to launch both gesture detections at the same time
6. Run the CognitiveRehabilitation app in Choregraphe


### Cognitive training app

It does not require the MySQL+nodeJS app therefore it is sufficient to
1. Open Choregraphe and run “CognitiveTrainingApp”
