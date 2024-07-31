My version : Shubham Github Repo: https://github.com/LondheShubham153/django-todo-cicd

STEP 1: Connect your Jenkins and Github:
1] open jenkins http://65.2.9.17:8080
2] Manage jenkins => click Systems => GitHub => credendial =>clcik add => select "Secret Text" from drop down, enter the passtoken which u have created in github
  save=> from drop down slect the the key u created 

  Now ur GITHUB IS LINKED TO YOUR JENKINS

STEP 2: 
Install python and Django to run this application

1. sudo apt update
2. Next, check which version of Python you have installed. 22.04 ships with Python 3.10 by default, which you can verify by typing:
   sudo apt install python3
   python3 -V OR python3 --version
3.Next, install Django: 
   sudo apt install python3-django
4. You can test that the installation was successful by typing:
    django-admin --version

STEP 3:

1] git clone https://github.com/LondheShubham153/django-todo-cicd.git => on AWS ubuntu machine
2] git commit
git push -u origin feature =>pushing the code to the (branch name here)

3] Open jenkins on port 8080 => http://65.2.9.17:8080
4] create job => freestyle project => click ok => configure system => select Git => enter Github Repo URL => scroll down => slect execute shell =>
sudo docker build . -t django-app
sudo docker run -p 8000:8000 django-app -d 

Save the changes
5] build job => if successful then try to access the application on given port 8000 => http://65.2.9.17:8000














=========================================================================================================================
# django-todo
A simple todo app built with django

![todo App](https://raw.githubusercontent.com/shreys7/django-todo/develop/staticfiles/todoApp.png)
### Setup
To get this repository, run the following command inside your git enabled terminal
```bash
$ git clone https://github.com/shreys7/django-todo.git
```
You will need django to be installed in you computer to run this app. Head over to https://www.djangoproject.com/download/ for the download guide

Once you have downloaded django, go to the cloned repo directory and run the following command

```bash
$ python manage.py makemigrations
```

This will create all the migrations file (database migrations) required to run this App.

Now, to apply this migrations run the following command
```bash
$ python manage.py migrate
```

One last step and then our todo App will be live. We need to create an admin user to run this App. On the terminal, type the following command and provide username, password and email for the admin user
```bash
$ python manage.py createsuperuser
```

That was pretty simple, right? Now let's make the App live. We just need to start the server now and then we can start using our simple todo App. Start the server by following command

```bash
$ python manage.py runserver
```

Once the server is hosted, head over to http://127.0.0.1:8000/todos for the App.

Cheers and Happy Coding :)
