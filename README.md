# random-student-cli README
The random-student-cli repository contains Octave functions that allow me to call on, and keep track of, random students in my class. It allows me to track participation and encourages student engagement. It also removes instructor bias and forces me to call on shy, quiet, or unengaged students.

Furthermore, it is open source so the students can look at the source code and can not accuse me of bias! My intention is for my students to peruse this code. Although there are more powerful and arguably more useful ways to implement these same features, I am teaching courses that emphasize MATLAB and I want to show students that Octave (MATLAB really but same syntax) can be used for a host of different things. Hopefully this will motivate some of them to use Octave, git, and other open source tools in the future.

## GNU Octave Tested and Working! *Maybe MATLAB Compatible?*
While the .m files *should* be compatible with MATLAB, I have only tested the functions with GNU Octave, a free, open-source, alternative to MATLAB.

## Intended use
As the repository name implies, I intended to call these functions from a terminal running ```octave-cli```. This way I can have Octave and/or MATLAB open and call on a student at the same time while preserving my workspace variables for whatever I am currently working on in class.

## Initial Setup
If you clone / download the repository, it is reccomended to add the directory you store the functions in to your Octave path. You can do this in linux by adding the line ```addpath("~/place/to/your/clone/")``` to your ```~/.octaverc``` file.

That way it is super easy to call the functions from an ```octave-cli``` terminal.

## Semester Setup (Run at beginning of every semester)
These functions will work with any school system but since I am at Colorado State University, it is designed to work fairly easily with AiresWeb.

The following will help you get ready to start the semester using the random-student-cli.

**It is reccomended to wait until the day before (or even the day of) the start of classes to perform these steps.** Students tend to add/drop before classes start. There are ways to mitigate students adding and dropping the class (see ```dropStudent``` and ```addStudent``` below).

To setup the program for the semester perform the following steps:
* Open a web browser (preferrably Firefox) go to https://ariesweb.colostate.edu and login using your CSU credentials. **You must be logged into CSU wi-fi or VPN for this link to work**.
* Under "Instructor Tools" click the "Class Lists" link.
* In the window that opens, click the "Class List" next to the class you want to setup.
* You should now see a list of all the students in your class, scroll to the bottom and click the "Save Test (Comma Delimited)" button and save the file somewhere on your computer
* Open the file you just downloaded with your favorite spreadsheet app (for a free open-source alternative to Excel, try LibreOffice!). Copy the student names column (remove the header) and paste them in a new spreadsheet. Save this spreadsheet as a semi-colon delimited CSV file.
* Finally, you can open Octave. If you added the repository to your path, you should be able to type run the ```initializeRandomStudent()``` function to get started.

## Function Definitions
All that is necessary to run the program is to call the following functions when necessary. Each student is assigned a "student number" which is really just the vector row number that corresponds to their statistics.

### ```initializeRandomStudent(csvFileName,courseIdent)```
This function creates the .mat file that contains the workspace variables necessary to run the program. The .mat file will be saved as ```courseIdent.mat``` in the current working directory so it is reccomended to move to the cloned directory before running.

Inputs:
* ```csvFileName``` - this is a string that points to a semicolon delimited CSV file with the students names
* ```courseIdent``` - this is a string that the user provides to specify the course in the future. That way you can have multiple sections of the same course. i.e.) "mech105_2" for MECH105 section 2 

There are no Outputs available for this function.

### ```callStudent(courseIdent)```
This function allows the instructor to call on a random student. Currently the function will not call on a student again until all students have been called on. Future implementations will change this (don't want students thinking they can check out in big classess).

Inputs:
* ```courseIdent``` - this is the name of the .mat file that the user specified when running ```initializeRandomStudent()``` for the first time.

There are no Outputs available for this function.

### ```checkStudent.m```

### ```dropStudent.m```

### ```addStudent.m```
