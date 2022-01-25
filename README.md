# Mkdocs custom plugin example

This repository contains an example examples of adding additional functionality to a Mkdocs with Material project.

In this Mkdocs sample we've used the [klipse plug-in](https://github.com/viebel/klipse) to make some of the Python code examples editable - i.e. the Python examples on the page can be edited by the user in real-time, and the displayed output from the code will change. 

As outlined in the comments through the code, to do this we need to add some overrides for the HTML template, and add a few custom items to the mkdocs.yml file.