# Tricks here,

### Pycharm Remote Dev
Pycharm remote dev opens a new window. Interpreter is interpreter on the server. Having better server resources is better for running Pycharm workers on the node. 
Make ssh configurations on Pycharm. Creating a new pycharm user is more secure and a better practise. After starting the project, click remote dev, 
go to ssh then find your project if it is running on the server. When pycharm workers run, it means pycharm can find your project and you can see your prject as running on ssh.

<br>
Here it comes to packaging. Python package system gives error and it can't find packages. If you developed your project using Pycharm and packages and you want to run your
scripts on the server, you face an error. You can easily start your scripts using pycharm run button but not in the ssh session. You may want to run some scripts at the background
and then you are not able to start the script. Solution is exporting an environmental variable that declares your project directory: 
<br>
```
export PYTHONPATH=path_to_your_project:$PYTHONPATH 
export PYTHONPATH=/home/ubuntu/pycharm_project:$PYTHONPATH # an example
```
