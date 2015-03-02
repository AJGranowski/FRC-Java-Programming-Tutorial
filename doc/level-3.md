# Level 3 #
##### *Programming a robot in Java* #####
**At this point, it is going to be assumed that you are comfortable with programming in java. If you are not comfortable, see the [level two](level-2.md) handbook.**

Congratulations! You are now ready to program the robot! Let’s dive in, shall we?

====

##### Table of Contents: #####
* [Setup](#setup)
* [Git](#git)



## Setup: ##
*Note: This guide has been written during 2015, so some of the steps outlined might differ from what you see.*

The first thing we need to take care of is the setup of our environment. Luckily for us, FIRST posts a step by step guide for this each year.

(You will want to make sure that you follow these instructions while on a deployment platform such as a Classmate or other laptop.)

#### To access the guide, follow these steps: ####

1.	Navigate to www.usfirst.org/roboticsprograms/frc
2.	Locate “Technical Resources” in the left sidebar
3.	Hover over the button, and select “Programming” when a sub menu pops out

This should bring you to the 2016 FRC Control System page.

If you are concerned with this year’s robot setup, you should read through *Getting Started With the 2016 Control System*, if not, we can simply jump to setting up the environment.

#### Following instructions: ####
1.	Click on the hyperlink that suggests setting up Java. For 2015 this was [FRC Java Programming](http://wpilib.screenstepslive.com/s/4485/m/13809)
2.	Follow all of the steps under Setting up the Development Environment from top to bottom. *(This is important as we skipped a bunch of this and ended up a little behind in 2015.)*

After following all of the instructions, you should now have either a configured Netbeans or Eclipse IDE installed on the deployment platform as well as an imaged robot.



## Git: ##
Now that we can program and deploy code to our robot, why aren’t we? The answer to that, is because we don’t have a reliable revision repository setup. Yeah, we could just program and deploy directly to the robot, but this prevents collaboration and makes the possibility of terrible mistakes something other than fantasy.

What we need to do, is setup Git.

1.	Check to see if you already have Git installed. Look for a desktop icon that looks like this: ![](http://git-scm.com/images/logos/downloads/Git-Icon-1788C.png) If you have it, ignore the next step.
2.	If you are on a Windows machine, head to [msysgit.github.io](http://msysgit.github.io/) to download Git.
3.	While you are downloading and installing, [read about Git here](http://git-scm.com/about).

Once Git is installed on your deployment platform, have all of the programming members who would like to participate create a GitHub account.

* To create an account, simply head to [github.com](https://github.com/) and make one.

After people have created GitHub accounts, have them navigate to [try.github.io](https://try.github.io/levels/1/challenges/1) to practice or get a refresher of the bash terminal and Git.

Now it’s time to create a repository.

#### Creating a Git repo: ####
1.	Create a new repo in GitHub on the main page. Name it something identifiable like [FRCRobotCode2015](https://github.com/owatonnarobotics/2015RobotCode)
2.	On the repo page, copy the *"HTTPS clone URL"* text on the lower right
3.	Open up bash and navigate to the directory you want to work in. Use `cd ..` to go up a level, and `cd <directory name>` to navigate to a directory.
4.	In bash, type git clone and then press the Insert key to paste the location of the repository, the end text should look like `git clone https://github.com/owatonnarobotics/2015RobotCode.git`
5.	Press enter to clone the online repo into your deployment machine.
6.	If you did not include a `.gitignore` in creating your online repo, you will need to create it
a.	In bash, run the command `touch .gitignore` while in the main part of your local repository. This should create an empty `.gitignore` file
7.	Head to [github.com/owatonnarobotics/2015RobotCode/blob/master/.gitignore](https://github.com/owatonnarobotics/2015RobotCode/blob/master/.gitignore) and copy the text into your `.gitignore` file. *(The `.gitignore` basically tells Git to never commit the listed files which is good for keeping the repo clean.)*
