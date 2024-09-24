# 23 Sept 2024

## Short-term goal
Combine together the static turpslib and the Django project vmzhoard into the same website, and deploy.

## Challenges and Attempts
The apps of vmzhoard cannot be imported properly, because
1. the package is not recognized in the same way as the independent vmzhoard, making the reference invalid.
The conflict seems to be solved by adding the content roots into the system path (inspired by PyCharm console settings), but introduced the 2nd problem:
2. they are not registered in INSTALLED_APPS of this Django turpslib, again making reference invalid on the level of Django project.
Further, it is not desired that the apps of vmzhoard should be registered on the same level of this Django turpslib, due to the potential conflicts with other Django projects that will be introduced in the future.

## Tentative Solution
The conflicts above seem to be impossible to solve within the framework of Django, and Django does not really seem to be designed in a way to contain complete independent Django projects as sub-apps.
Therefore, the temptive solution is to discard the idea of combining two project into one, but rather deploy 2 projects in the same domain, implemented on the server level.