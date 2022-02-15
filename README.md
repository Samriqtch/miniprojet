# miniprojet
PROJET IAI
Getting Started
Installing Dependencies
Python 3.9.7
pip 20.0.2 from /usr/lib/python3/dist-packages/pip (python 3.9)

Follow instructions to install the latest version of python for your platform in the python docs
Virtual Enviornment

We recommend working within a virtual environment whenever using Python for projects. This keeps your dependencies for each project separate and organaized. Instructions for setting up a virual enviornment for your platform can be found in the python docs
PIP Dependencies

Once you have your virtual environment setup and running, install dependencies by naviging to the /plants_api directory and running:

pip install -r requirements.txt
or
pip3 install -r requirements.txt

This will install all of the required packages we selected within the requirements.txt file.
Key Dependencies

    Flask is a lightweight backend microservices framework. Flask is required to handle requests and responses.

    SQLAlchemy is the Python SQL toolkit and ORM we'll use handle the lightweight sqlite database. You'll primarily work in app.py and can reference models.py.

    Flask-CORS is the extension we'll use to handle cross origin requests from our frontend server.

Running the server

From within the plants_api directory first ensure you are working using your created virtual environment.

To run the server on Linux or Mac, execute:

export FLASK_APP=flaskr
export FLASK_ENV=development
flask run

To run the server on Windows, execute:

set FLASK_APP=flaskr
set FLASK_ENV=development
flask run

Setting the FLASK_ENV variable to development will detect file changes and restart the server automatically.

Setting the FLASK_APP variable to flaskr directs flask to use the flaskr directory and the __init__.py file to find the application.

import of libraries:

import os
from dotenv import load_dotenv
from urllib.parse import quote_plus
from flask import Flask, redirect,abort, render_template, request, url_for,jsonify
from flask_sqlalchemy import SQLAlchemy

database connection:

app=Flask(__name__)
app.config['SQLALCHEMY_DATABASE_URI']='postgresql://postgres:{}@{}:5432/bibliotheque'.format(password,host)
app.config['SQLALCHEMY_TRACK_MODIFICATIONS']=True
db=SQLAlchemy(app)


Route to interact with the API:

@app.route("/livres",methods=["GET"])

@app.route("/categories",methods=["GET"])

@app.route("/livres/<int:id>",methods=["GET"])

@app.route("/categories/<int:id>",methods=["GET"])

@app.route("/livres/<int:id>",methods=["DELETE"])

@app.route("/categories/<int:id>",methods=["DELETE"])

@app.route("/livres/<int:id>",methods=["PATCH"])

@app.route("/categories/<int:id>",methods=["PATCH"])

@app.route("/categories/<int:id>/livres",methods=["GET"])
