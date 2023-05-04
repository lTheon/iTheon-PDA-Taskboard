# iTheon-PDA-Taskboard v1.0.0

This mod adds a new taskboard tab to the PDA where you can accept all the dynamic tasks remotely

How to use it? <br>
On Taskboard tab there's a Refresh tasks button - click it once and wait for the tasks to be processed (time depends on the population density in radius, but is pretty fast). <br>
You'll get a list of tasks split into categories. Next to the task description you will see two buttons. Accept task - self-explanatory - accepting a task automatically refreshes the board, as some tasks automatically remove others from the available list (vanilla Anomaly stuff). Next task - tells PDA to prepare info about the next task in category.


Possible questions: <br>
Q: Why there's no `Previous task` button?
A: In short - engine limitation. It's because of problems with getting additional info about the task (middle column). To add such a button, I'd need to modify a lot of base game files and this would lead to many compatibility issues with other mods.

Q: Why I can take delivery and measure tasks remotely? They give me some items
A: I wanted to add a screen blackout for those tasks, but it's annoying. I think it's better without it. You can omit those tasks if it hurts your realism

Q: Some task details are messed up and are showing next to the wrong task. Why?
A: This bug should be eradicated by now. If you still encounter it, please report to me.

Q: One of my tasks has no image. Why?
A: Some tasks don't have image - no worries.

Q: Does it work with WTF?
A: Technically yes, but some people report random issues. You should report those problems either to me or to Igi.

Q: Some `Search stash` or `Drug runner` tasks appear in `Bounty tasks` category. Is that a bug?
A: Yes - but it's a bug in vanilla Anomaly files. These tasks need to be categorized as `Bounty tasks` because their setup function dispatches a delayed function to a wrong queue (the bounty task queue). This causes some task details to be lost if a bugged task like this is processed simultaneously with a normal bounty task.

Q: Why you didn't make one full board of tasks? <br>
A: Engine limitation. I've tried doing it in several different ways, but there needs to be a delay between fetching detailed info about tasks of similar type. With no delay, specific info about the task (e. g. target name and location) will not load properly. You could accept such a task, but you wouldn't know who exactly you have to kill and where he is before you accept it. With full list - even when I've set certain delays to 10 seconds - it sometimes happened anyway. With split list, there doesn't need to be any delay.

Credits:<br>
Mr. Demonized - optimized time events script<br>
https://github.com/IIJTypmaH - Russian translation<br>
https://github.com/Igigog - WTF support

Changelog:

v1.0.0
- Refreshed view with custom icons
      - Task category captions
      - Dynamic category row heights - no more weird shit with MCM configs for row height and text trimming
      - Fixed bug with double-click required for `Next task` and `Accept task` buttons to work - now one click is enough
- Massive code improvements
- Potential fix for messed up task details
- Exclude Reefer's task from the scanning

v0.1.15
- Fix CTD when trying to fetch Next Task and the taskgiver has been deleted by the engine

v0.1.14
- Add taskboard keybinding
- Change order of the tabs (place taskboard next to map)

v0.1.13
- Exclude Gavrilenko from the list of processed npcs

v0.1.12a
- Add missing xml file

v0.1.12
- Add a separate PDA tab for taskboard

v0.1.11
- Exclude Outskirts merc mechanic tools task from the list of available tasks (it's impossible to take normally and can't be finished)
- Adjust the task description fetching code - now the descriptions of the fetch tasks look exactly like they do in the dialog window

v0.1.10
- Exclude Yar's CoC task from the list of available tasks

v0.1.9
- Add WTF support by Igi

v0.1.8
- Add options to disable text trimming and increase the task row height

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
