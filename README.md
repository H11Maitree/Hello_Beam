# Flask Template Starter
This source code repository is made as a template (**ready-to-use**) for **Heroku** auto deployment for Flask App(s).

## Local Run-Build
To **preview the web on your local computer**, follow the instuctions below.
1. Enable Debugging Mode, This mode will not terminate your program in case of error, instead it will friendly display the error massage into the web browser [Example](https://flask.palletsprojects.com/en/2.2.x/quickstart/#debug-mode).
```
$ export FLASK_DEBUG=1
```

2. Run the web server on local environment:
```
$ python wsgi.py
```
After this command the web server will be host in your machine: eg. http://127.0.0.1:5000 (This local ip-address will be shown at the time of excuting this running command).


## Main code
The core code for the website maily located in a single file [app/main.py](app/main.py).
### Add new Page(route)
To add a new page (eg.page for "Contact Us"), add this following line into the [app/main.py](app/main.py).
```
@app.route('/ContactUs')
def contactus():
    return "Contact Us:<br>Tel: +1 (333) 333333" 
    # Alternately, You can return the string in the HTML+CSS+JS format.
```

## External Library
Since the Heroku instance is a fresh-new server, it need to install all those library that you have used in your code to run,
such as:
- flask*
- gunicorn*
- math
- numpy

\* Mandatory for deploying into Heroku.

To do this, Heroku support ```pipenv```.
Like ```pip install``` command for your local computer, you can ```pipenv install```:
```
$ pipenv install numpy
```
This example command will update [Pipfile](./Pipfile) and [Pipfile.lock](./Pipfile.lock) to let Heroku knows what need to be install (in this case install ```numpy```) before running your web.

## [Heroku](www.heroku.com) deployment
1. Create a new Dyno.
2. Connect your repository.

I recommend using the Github repo auto deploy fucntion, connecting your GitHub account to Heroku then you can select auto-deploy from your Github repo of your choice.

Every times you commit and upload your code into GitHub ([GitHub Desktop](https://desktop.github.com) works fine), it will **automatically update your website**.

This repo is connected by using Heroku auto-deploy: 
https://dec-30.herokuapp.com


