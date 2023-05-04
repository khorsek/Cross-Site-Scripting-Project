# Cross-Site-Scripting-Project

# The purpose of this lab is to try to demonstrate what attackers can do by exploiting XSS vulnerabilities. In order to do this, we will set up a web application named Elgg and make it intentionally vulnerable to XSS attacks, allowing users to post any message, including JavaScript programs, to user profiles.

# In order to do this project, I am using the Labtainers provided by the Naval Postgraduate School.
# Link here: <a href="https://nps.edu/web/c3o/labtainers">Labtainers</a>

# To start off the lab, I first launch up the Labtainer VM, log in, and start up the xsite lab.
# With all three of the VM’s needed ready, I proceed:
<img src="images\1.PNG">

# After starting up Firefox and heading toward the Elgg website, I log in as User Alice and head to the user profile, where I type in the script to make an alert pop up when another user visits their profile:
<img src="images\2.PNG">

# After saving the description, I let the page reload and get the following alert. Telling me that my initial XSS script is a success:
<img src="images\3.PNG">

# To test it again, I log in as user Boby and visit Alice’s profile, which does indeed bring up the alert. I then move on to the next step.
<img src="images\4.PNG">