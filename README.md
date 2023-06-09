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

# For task 2, I type in the other script provided that would bring up the user’s cookies if they visit Alice’s profile as seen below:
<img src="images\5.PNG">

# After saving the post, I let the page reload and get the cookies alert:
<img src="images\6.PNG">

# Telling me that my attempts have indeed ended in success. I then switch to Boby and see that it works logged in as another user as well:
<img src="images\7.PNG">

# With task 2 a success, I move on to task 3.

# To start it off, I type in the provided script including my attacker IP address that would send a GET HTTP request to the attacker’s machine instead of retrieving an image as specified:
<img src="images\8.PNG">

# With echoserv already running via ./echoserv 5555, I save my profile settings and immediately get it broadcasted to the attacker terminal as planned:
<img src="images\9.PNG">

# Trying the same thing but logged in as Boby, it does work fine:\
<img src="images\10.PNG">

# For task 4, I begin my logging in as Boby and visiting Alice’s profile, thus receiving the cookies needed and note it down in a text file:
<img src="images\11.PNG">

# I then head to the HTTPSimpleForge directory and open the java file with the command: “Sudo nano HTTPSimpleForge.java”
<img src="images\12.PNG">

# After grabbing the correct elgg_ts_value and elgg_token from checking the HTTP header, I assign those values in the java file:
<img src="images\13.PNG">

# As well as setting the cookie value that I got from the same session:
<img src="images\14.PNG">

# I also fixed some spacing issues that kept getting me an HTTP 400 code which means the request wasn’t going through. After this, I recompiled java app and running it gave me a code 200 as well as a huge amount of code so I guess it worked:
<img src="images\15.PNG">

# With task 4 a success, I move on to the countermeasures; task 5.
# To start it off, I login as Admin, go to plugins and enable the HTMLawed 1.8 security plugin as shown:
<img src="images\16.PNG">

# After turning on HTMLawed 1.8, I visit Alice’s profile and get absolutely no popups:
<img src="images\17.PNG">

# Since that plugin works, I decide to try the other other. After navigating to the /output folder for elgg, I open up the first file called text.php and uncomment the htmlspecialchars function to show as an example:
<img src="images\18.PNG">
<img src="images\19.PNG">

# After editing the files, I visit a victim’s profile as Boby and no alerts pop up. Looks like it works.
<img src="images\20.PNG">

# Some Q&A

# Q: What are the goals of the techniques and tools used in this lab? How are they relevant to real-world security?
# A: The goals of this lab are to acquaint users with cross site scripting techniques and learn some ways of how-to implement countermeasures against them.

# Q: How effective are these techniques and tools, in your opinion?
# A: XSS attacks can be quite dangerous when injected into high traffic user pages that could spread malware so these techniques can be quite effective.
