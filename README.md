# iTheon-PDA-Taskboard v0.1.7

This mod changes the Contacts tab of PDA into a taskboard where you can accept all the dynamic tasks remotely
I've performed a lot of tests (mainly in Rostok and DV), but I can never be sure whether I didn't miss some edge cases, so I'm releasing it for public testing for the players now.

How to use it? <br>
On Contacts tab there's a Refresh tasks button - click it once and wait for the tasks to be processed (time depends on the population density in radius, but is pretty fast). <br>
You'll get a list of tasks split into categories. Next to the task description you will see two buttons - these require double click for some reason (I'll work on changing that). Accept task - self-explanatory - accepting a task automatically refreshes the board, as some tasks automatically remove others from the available list (vanilla Anomaly stuff). Next task - tells PDA to prepare info about the next task in category.

To dos: <br>
fix double click required for Accept task and Next task buttons - no idea where it comes from for now


Possible questions: <br>
Q: My mutant part delivery mission has weird description. Why? <br>
A: Some "get mutant parts" tasks have messed up descriptions in PDA - this is not caused by the remote PDA taskboard. I've investigated it and it seems like the game is loading the .ltx files from the disabled mods, causing some task info to be overwritten (e.g. compare tm_warfare.ltx line 1308 in Warfare Overhaul and Vanilla Anomaly). The game fetches the info from Warfare Overhaul instead of vanilla one. Task effect is not passing the required info to the function that builds the description.

Q: Why you didn't make one full board of tasks? <br>
A: Engine limitation. I've tried doing it in several different ways, but there needs to be a delay between fetching detailed info about tasks of similar type. With no delay, specific info about the task (e. g. target name and location) will not load properly. You could accept such a task, but you wouldn't know who exactly you have to kill and where he is before you accept it. With full list - even when I've set certain delays to 10 seconds - it sometimes happened anyway. With split list, there doesn't need to be any delay.

Credits:
Mr. Demonized - optimized time events script

Changelog:

v0.1.7

- Speculative fix for rare bug with messed up details pairing (as a side effect the task categories will now always be rendered in a sorted order)

v0.1.6

- Fix accepting quests that assign you a temporary companion

v0.1.5

- Increase maximum number of simultaneously rendered task categories
- Expose normalizer table for other mods

v0.1.4

- Add conditional shortening of the task description and details

v0.1.3

- Fix weird bugs caused by refreshing board when there was a task without details on it

v0.1.2a

- Fix task giver override not getting cleared after processing fetch tasks

v0.1.2

- Add Mr. Demonized's "optimized time events" script as an integral part of the addon (required for vanilla Anomaly)

v0.1.1

- Fix Sidor and Forester distance evaluation<br>
- Introduce delay for refreshing the tasks<br>
- Visual tweaks<br>
- Add mcm config
