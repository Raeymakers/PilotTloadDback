# PilotTloadDback
This is a pilot TloadDback task. The goal is to make a shorter and faster version of the TloadDback task that lasts no longer than 10 minutes. To test if it works, we will conduct a psychomotor vigilance tesk.

Programmed with Jspsych, javascript, on Visual Studio Code. 

The experiment goes as follows: after asking for some ID age, nationality etc. participants will see a series of images. 
The images can be found in the 'img' folder. there are 8 differently colored balls, and 8 pictograms. 
The images will follow each other, and the participant needs to press 'J' when the picture matches the picture of n_back. 
The match-nonmatch trials are weighted 2 to 1. 
participants will randomly get a different 'ideal accuracy percentage'. 
when participants are less accurate than this percentage, the trials will get slower (to make things easier). 
when they are more accurate, the trials will speed up. 
after exp_duration minutes, the experiment will end. 

A psychomotor vigilance task is yet to be added to this experiment. 

In the 'tryout code' there is a smaller, simpler version that runs on your local computer (not a server). 

To make this code work, you need to download JsPsych 6.3.0 and save it in this map as 'jspsych'
