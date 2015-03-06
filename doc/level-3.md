# Level 3 #
##### *Programming a robot in Java* #####
**At this point, it is going to be assumed that you are comfortable with programming in java. If you are not comfortable, see the [level two](level-2.md) handbook.**

Congratulations! You are now ready to program the robot! Let’s dive in, shall we?

====

##### Table of Contents: #####
* [Setup](#setup)
* [Git](#git)
* [Using Git](#using-git)
* [Programming the Robot](#programming-the-robot)



# Setup: #
*Note: This guide has been written during 2015, so some of the steps outlined might differ from what you see.*

The first thing we need to take care of is the setup of our environment. Luckily for us, FIRST posts a step by step guide for this each year.

(You will want to make sure that you follow these instructions while on a deployment platform such as a Classmate or other laptop.)

##### To access the guide, follow these steps: #####

1.	Navigate to www.usfirst.org/roboticsprograms/frc
2.	Locate “Technical Resources” in the left sidebar
3.	Hover over the button, and select “Programming” when a sub menu pops out

This should bring you to the 2016 FRC Control System page.

If you are concerned with this year’s robot setup, you should read through *Getting Started With the 2016 Control System*, if not, we can simply jump to setting up the environment.

##### Following instructions: #####
1.	Click on the hyperlink that suggests setting up Java. For 2015 this was [FRC Java Programming](http://wpilib.screenstepslive.com/s/4485/m/13809)
2.	Follow all of the steps under Setting up the Development Environment from top to bottom. *(This is important as we skipped a bunch of this and ended up a little behind in 2015.)*

After following all of the instructions, you should now have either a configured Netbeans or Eclipse IDE installed on the deployment platform as well as an imaged robot.



# Git: #
> Now that we can program and deploy code to our robot, why aren’t we?

The answer to that, is because we don’t have a reliable revision repository setup. Yeah, we could just program and deploy directly to the robot, but this prevents collaboration and makes the possibility of terrible mistakes something other than fantasy.

What we need to do, is setup Git.

([What?](http://hoth.entp.com/output/git_for_designers.html))

#### Setting up Git: ####

1.	Check to see if you already have Git installed. Look for a desktop icon that looks like this: ![](http://git-scm.com/images/logos/downloads/Git-Icon-1788C.png) If you have it, ignore the next step.
2.	If you are on a Windows machine, head to [msysgit.github.io](http://msysgit.github.io/) to download Git.
3.	While you are downloading and installing, [read about Git here](http://git-scm.com/about).

Once Git is installed on your deployment platform, have all of the programming members who would like to participate create a GitHub account.

* To create an account, simply head to [github.com](https://github.com/) and make one.

After people have created GitHub accounts, have them navigate to [try.github.io](https://try.github.io/levels/1/challenges/1) to practice or get a refresher of the bash terminal and Git.

You can also use these resources to help with the setup:
* https://help.github.com/articles/set-up-git/

Now it’s time to create a repository.

##### Creating a Git repo: #####

1.	Create a new repo in GitHub on the main page. Name it something identifiable like [FRCRobotCode2015](https://github.com/owatonnarobotics/2015RobotCode)
2.	On the repo page, copy the *`HTTPS clone URL`* text on the lower right
3.	Open up bash and navigate to the directory you want to work in. Use `cd ..` to go up a level, `ls` to list files, and `cd <directory>` to navigate to a directory.
4.	In bash, type `git clone` and then press the **Insert** key to paste the location of the repository. The end text should look like this: `git clone https://github.com/owatonnarobotics/2015RobotCode.git`
5.	Press enter to clone the online repo into your deployment machine.
6.	If you did not include a `.gitignore` in creating your online repo, you will need to create it
  * In bash, run the command `touch .gitignore` while in the main part of your local repository. This should create an empty `.gitignore` file
7.	Head to [github.com/owatonnarobotics/2015RobotCode/blob/master/.gitignore](https://github.com/owatonnarobotics/2015RobotCode/blob/master/.gitignore) and copy the text into your `.gitignore` file. *(The `.gitignore` basically tells Git to never commit the listed files which is good for keeping the repo clean.)*

Great! We now have a repository setup!



# Using Git: #
Now we can manage our project with Git. This would be wonderful news if we all knew how to take advantage of it, but some of my readers might not. This section is here to focus on how to perform the operations you should expect to have to do at one point or another.

If you would like help using any command, the `-h` or `--help` flags on any command will reveal help options.

For example: `git push --help` will open up the local documentation of the push command

##### The usual workflow of Git is as follows: #####
1. Pull from a remote repository
2. Work on the project
3. Stage and commit changed files
4. Pull from the remote repository to make sure you are up to date
5. Push to the remote repository

It gets a little more complicated when working on other peoples projects, but that should all be covered within this section.

### Standard workflow: ###
1. `git pull <remote-name>`
2. *Work on changes*
3. `git status` (To see what has changed)
3. `git add --all` OR `git add <file-name>`
4. `git status` (To see what will be in the commit)
4. `git commit -m "<what-you-changed>"`
5. *At the end of a coding session*
6. `git pull <remote-name>` (To make sure that you are up to date)
7. `git push --prune --all <remote-name>` *(This makes the remote repo look the same as your local repo by deleting branches you no longer have and pushing all of your existing branches to the remote)*

### Using Branches: ###
You use branches to split up the project into logical chunks to be merged later on.
![](http://git-scm.com/images/about/branches@2x.png)

1. Make a branch with either `git branch <name>` or `git checkout -b <name>`
2. View branches with `git branch`
3. Checkout a branch with `checkout <branch-name>`
4. Merge two branches by checking out one, and then running `git merge <other-branch-name>`
5. Delete old branches you no longer need with `git branch -d <name>`

I would recommend one branch for working code (`master`), one branch for developing the next version (`dev`), and one branch for every major part of a project.

### Working on someone else’s project: ###
1. `git push --prune --all <your-remote>`
2. Login to [github.com](https://github.com/)
3. Head to the repo you would like to push your changes to
4. Click on *"Pull Requests"* on the right side
5. Submit a pull request
  * `base` is where the code is going
  * `head` is where the code is coming from


### Merging: ###
1. `git pull` or `git merge`
2. *Message about "Automatic merge failed"*
3. Edit the files listed to merge. `<<<<<<< HEAD` to `=======` is what you have, `=======` to `>>>>>>> *gibberish*` is what the remote has.
4. `git add --all` OR `git add <file-name>`
5. `git commit -m "Merge resolution: Merged <remote-name> into local"`


# Programming the Robot: #
Now that all of our basics are setup, we can begin to program the robot.

Again, follow the steps from the 2016 FRC Control System page for creating the program. It should look something like this:

1. Open eclipse
2. Navigate to `File` > `New` > `Other...`
3. Select `WPILib Robot Java Development`
4. Select `Robot java Project`
5. If prompted, select `Command Based Robot` or something of the like.

Once you have a project created, it would be a good idea to open up Git to make an initial commit.

## What does this do? ##
There are going to be three files that came with the project.

* `OI.java`
* `Robot.java`
* `RobotMap.java`


### OI.java ###
This is the **O**perator **I**nput file. This is where all of the buttons and stuff will be created.

The code in the OI.java file is usually something like `<Button>.whenPressed( new MyCommandToDoStuff() );`

If you are using an Xbox 360 controller, you might want to include [this](https://github.com/owatonnarobotics/XboxController) file to make things easier.


## Robot.java ##
This is where all of the magic happens.

Usually in java, the start of everything is in a main method, but not in this case. If you take a peek into the `Robot.java` file, you will find that there are already some methods included in it. Here's what each method does:

* `robotInit()` - Called once when the robot is started up.
* `disabledInit()` - Called once when the robot enters a disabled mode. *NOTE: This is called when the robot has finished starting up.*
* `disabledPeriodic()` - Called about every 20ms while the robot is disabled.
* `autonomousInit()` - Called once when the robot enters autonomous mode.
* `autonomousPeriodic()` - Called about every 20ms while the robot is in autonomous.
* `teleopInit()` - Called once at the end of autonomous when teleop begins.
* `teleopPeriodic()` - Called about every 20ms while the robot is in teleop.
* `testPeriodic()` - I don't know. I've never used it.

There is also a weird method that gets called named `Scheduler.getInstance().run()`. This method calls other stuff in the background so you don’t have to. It checks the buttons when called and executes the tied commands if they are pressed. It also manages the execution of the commands. You can find more about it [here](http://first.wpi.edu/FRC/roborio/release/docs/java/classedu_1_1wpi_1_1first_1_1wpilibj_1_1command_1_1Scheduler.html#details) (also found somewhere on the 2016 FRC Control System page)


## RobotMap.java ##
This is a file used for global variables.

What you would want to put here is any constant that you might end up changing later on. This includes:

* PWM ports
* DIO ports
* Any other port
* Variables for certain robot functions (max speed, flash lights, etc.)

You should make them with the modifiers `public static final`



If you are still confused about how exactly everything works, you should feel free to look at our [2015 code](https://github.com/owatonnarobotics/2015RobotCode). It has a working autonomous and teleop modes, and also provides examples of working with WPILib and the XboxController Class.
