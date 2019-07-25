# Configuration of VSC for Python
Today I made decision to learn the python and visual studio code systematically in the next following 2 days. For in the before, I just learned it by bit and pieces when I want to in my work. But during the process, maybe some haddle comes then I switch to other methods or to the original vims and then I never use vsc and python. Then I have to make a decision and use 2 days to learn systematicly.

1. Multiple interpreters in the interface.

When you open a project in the explorer, and click the left bottom to apply different interpreter for your project. A folder with the name `.vscode` will appear in the explorer. which indicate which interpreter you have choosen for your project.

2. Default and user setting, workplace setting
```
{
   "window.zoomLevel": 2,
    "workbench.colorTheme": "Predawn",
    "workbench.settings.editor": "json",
    "workbench.settings.openDefaultSettings": true,
    "workbench.settings.useSplitJSON": true,
    "editor.fontSize":14,
    "editor.fontWeight": "500",
    "editor.fontFamily": "Source Code Pro",
    "debug.console.fontSize": 14,
    "terminal.integrated.fontSize": 14,
    "terminal.integrated.fontWeight": "500",

    "[python]": {
        
    },
    "git.autofetch": false,
    "workbench.iconTheme": "ayu",
    "python.pythonPath": "/usr/local/bin/python3"
    "code-runner.saveFileBeforeRun": true
}
```
+ Tips
  + shift+command+P, then input `default setting`,  can open the default setting pannel.
  + you don't have to copy/paste between default setting and user setting, just click the pencil icon besides the default setting, it will copy/past to the user setting pannel.
  + some commands
    + `which python`
    + `type python`
    + `touch ***`

3. Using virtual environment

+ `python3 -m venv nameofyouvirtualenvironment`, then you can have a virtual envionrenment for you work place; 
  + if you want to use the envirenment, you can use the tips in "1. multiple interpreters".
  + if you want to activate teh virtual environment in command line, just use `source thepathofthe Venv/bin/activate` to make it activate;
  + if you want to deactivate it, just use `deactivate`
  + make a virtual environment with system packages
    + `python3 -m venv youvirtualenvironment --system-site-packages`
+ work in different environment
  + `pip install -r requirements.txt`
  + `pip freeze > requirements.txt`

4. format the python codes automatically
* `shift+option+f`

5. with github
* using `.gitignore` file to ignore the file you don't want to synthesize with github.
