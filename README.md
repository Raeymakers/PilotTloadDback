# PilotTloadDback
This is a pilot TloadDback task. The goal is to make a shorter and faster version of the TloadDback made by Borrogan et al. (2017) that lasts no longer than 10 minutes. To test if it works, we will conduct a psychomotor vigilance tesk.

Programmed with Jspsych, javascript, on Visual Studio Code. 

The experiment goes as follows: after asking for some age, nationality etc. participants will see a series of images. 
The images can be found in the 'img' folder. there are 8 differently colored balls, and 8 pictograms. there are also 8 pictures of 4 small object (comb, key, pear and glass)
and 4 big objects (plane, elephant, house, truck). 
the colored balls and objects follow after each other: ball- object - ball - object.
Whenever a ball is the same color as the last ball, participants need to press the SPACE bar; 
whenever the object is small, they press J
When the object is big, they press F. 
When they make a mistake, they get an error message: 'WRONG!'
these error messages only start after the first 4 trials. 

The current finished version of the code is called 'code'


participants will randomly get a different 'ideal accuracy percentage', called accuracy_percentage. 
when the accuracy of participants gets higher than this percentage, their Stimulus Time Duration (STD) will get 100 ms shorter.
So when they are more accurate, the trials will speed up. 
after exp_duration minutes, the experiment will end. 

Borrogan et al first had a round to determine ideal STD per participant which is the shortest STD duration where participants still score higher than 85% accuracy. 
In their pre-test session there was a part where participants practiced separately the odd/even judgement and 1-back task, using right hand for parity judgement and left hand for 1-back task. STD here was 1500 ms. The training was interrupted once accuracy reached 85%.

During the actual test, the STD was fixed at 1400 ms. If performance was higher than 85%, the STD got 100 ms shorter. This was repeated until accuracy was below 85%. Their last successful STD was then assigned to the HCL condition. 
the LCL (low cognitive load) condition then had a STD that was STD HCL + ½ STD HCL

In this experiment, each condition will last equally long: 5 minutes. (plus a few seconds for the block to finish)
The difference between the control and CF (cogn fatigue) condition is the STD .
STD at the start will be 1500 ms. 
How accuracy_level works: 
Similarly to Borrogan et al (2017), this is computed by a weighted formula where accuracy for letters and digit represented 65 and 35 percent of the total score respectively 
Here it is: color 65% objects 35%
This was done to emphasize information-retrieval component of the task, based on existing literature showing that this has a higher attentional cost (borrogan et al 2017, Fougnie 2008)

How this was done: 65% = x + x*0.3,    35%= y – y* 0.3
x+y / n_trials

when the accuracy of the participant is higher than the accuracy_level (e.g. 50%), then the STD will get 100 ms shorter, and thus the task will get higher, making the accuracy drop until it is below the accuracy_level. 
This means that the lower accuracy_level, the harder the task will be. E.g. if it is set at 50% this means that if you get more than half of the trials correct, it will get lower
if the accuracy_level would be 90%, the STD would only get shorter if your accuracy is nearly perfect. 
So if you start with a trial_duration of 1500 ms, (which is pretty slow), you will first not get a lot of them right because you are still learning, meaning you will probably be below the accuracy_level. As you get better, your accuracy starts reaching the accuracy_level. The lower the accuracy_level, the faster you reach it and thus the more likely for the STD to drop. 
Keep in mind that the STD is what we are manipulating! Since the theory is that it is the available time to process information which determines the cognitive load (Barrouillet et al, 2004). 
For this reason, the control condition will have an accuracy_level set at 100 %, which means that each trial will last 1500 ms for the participants.  
in the CF condition, accuracy_level will be set at (? This to be determined in pilot study). 

Also different from Borrogan et al (2017) is the addition of an ERROR message. This was done because there is no training phase, and to make sure the task is engaging throughout.


The applicable Javascript code can be found under 'code.html'. 
The applicable Gorilla compatible code can be found as 'Gorilla_PilotTloadDback'
The Gorilla compatible practice rounds for Colours and Pictures can be found as 'Gorilla_Colors_training' and 'Gorilla_Pics_Training'.

