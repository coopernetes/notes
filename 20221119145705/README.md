# Customizable devhints clone
_Original note written at 11/17/2022, 9:09AM_

Most docs I write include code snippets or scripts or commands to run. It's hard to provide 
a set of instructions that are universal. I'm envisioning a method for authoring instructional
material where parameters such as "I run Linux or Mac OS or Windows" act as a decision tree
(kind of like how a CI system works), which traverses until you reach an "output" (snippet,
step-by-step). Also thinking it should be flexible enough to set "I'm on Windows, don't prompt
me again and let me get to the docs I need with this parameter set" (like remembered search
filters). 

This should be flexible enough to also take into account less technical docs ("what perspective
of information do you need ie. front end dev vs deisgner vs business analyst vs backend dev vs SRE/ops vs security analysts vs risk mmanager"?). This information normally has to be duplicated
to fulfill each persona.
