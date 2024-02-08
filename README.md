# How to make a module for your python programs

* First create a Repl like this one with the name of your future module
* Create a .gitignore file that will filter all useless files to be sent to github
* Then create the folder in which you will put the module files, here : mymodule
* In this folder, create a \_\_init\_\_.py file, empty, to say that it's a module folder
* Then create a file in which you will put your module functions : mymodule_misc.py
* Create some functions in it. I have added tqo functions.

In the main.py you can test using this module by importing it
It's ok the module works, I'm happy.

Now you have to make small changes to pyproject.toml and change the tool.poetry informations to these ones :

```
[tool.poetry]
name = "mymodule"
version = "0.0.1"
description = "small module to test things"
authors = ["FV <fv@fv.com>"]
```

The name is important and the version will have to be updated after each new version to allow people to upgrade.

Now let's configure a github project.
* open git in replit
* initialize git repository
* go to settings tab then Create Repository on Github (Private or Public)
* The Remote will be updated to : https://github.com/fvillemin/mymodule
* Go back to your git files and commit with a comment.
* Then click "Push branch as origin/main"
* It is now published on github

You can now create a new Repl and you can import your nice module by doing :
```
pip install -U git+https://github.com/fvillemin/mymodule
```
(replace nameofthemodule by the name of your module)
(this github is public but if it was private you would have to validate your credentials)

And it should automatically add your module to .pythonlibs
You won't see it but the module will be available

```
from mymodule import mymodule_misc
mymodule_misc.mymodule_works()
```

Everytime you change interesting things in your module, change the version number and push to Github and go to your main project and redo the pip install -U and it will upgrade the module.