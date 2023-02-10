# iTheon-PDA-Taskboard v0.1.0

This mod changes the Contacts tab of PDA into a taskboard where you can accept all the dynamic tasks remotely
I've performed a lot of tests (mainly in Rostok and DV), but I can never be sure whether I didn't miss some edge cases, so I'm releasing it for public testing for the players now.

How to use it?
On Contacts tab there's a Refresh tasks button - click it once and wait for the tasks to be processed (time depends on the population density in radius, but is pretty fast). Don't spam it for now, as you'll break the scripts (will add a refire delay). 
You'll get a list of tasks split into categories. Next to the task description you will see two buttons - these require double click for some reason (I'll work on changing that). Accept task - self-explanatory - accepting a task automatically refreshes the board, as some tasks automatically remove others from the available list (vanilla Anomaly stuff). Next task - tells PDA to prepare info about the next task in category.

To dos:
make scanning radius configurable (it's 100m right now)
visual lifting (maybe)
fix double click required for Accept task and Next task buttons - no idea where it comes from for now


Possible questions:
Q: My mutant part delivery mission has weird description. Why?
A: Some "get mutant parts" tasks have messed up descriptions in PDA - this is not caused by the remote PDA taskboard. I've investigated it and it seems like the game is loading the .ltx files from the disabled mods, causing some task info to be overwritten (e.g. compare tm_warfare.ltx line 1308 in Warfare Overhaul and Vanilla Anomaly). The game fetches the info from Warfare Overhaul instead of vanilla one. Task effect is not passing the required info to the function that builds the description.

Q: Why you didn't make a one full board of tasks?
A: Engine limitation. I've tried doing it in several different ways, but there needs to be a delay between fetching detailed info about tasks of similar type. With no delay, specific info about the task (e. g. target name and location) will not load properly. You could accept such a task, but you wouldn't know who exactly you have to kill and where he is before you accept it. With full list - even when I've set certain delays to 10 seconds - it sometimes happened anyway. With split list, there doesn't need to be any delay.
