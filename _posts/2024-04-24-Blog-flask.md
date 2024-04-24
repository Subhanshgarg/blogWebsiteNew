---
title: "Making a Flask Webapplication"
date: 2024-04-24 19:24:00 +0800
categories: [Blogging, Tutorial]
tags: [Blogging,WebApplication,Flask]
---

# Introduction

In this tutorial we will make a simple web application using the Python framework Flask. Follow the following steps to achieve the same:

# Steps:

## 1. Setup Environment
First, make sure you have Python installed on your system. Then, install Flask and MySQL connector using pip: pip install Flask pip install mysql-connector-python

## 2: Setup MySQL Database
Create a MySQL database and a table to store the user information. You can do this using a MySQL client like phpMyAdmin or via command line: 
CREATE DATABASE flask_demo; 
USE flask_demo; 
CREATE TABLE users ( id INT AUTO_INCREMENT PRIMARY KEY, name VARCHAR(100) NOT NULL, email VARCHAR(100) NOT NULL );

## 3: Create Flask Application
Create a new directory for your Flask application and create a file named app.py: 
from flask import Flask, render_template, request import mysql.connector
app = Flask(name)

: MySQL Configuration
db = mysql.connector.connect( host=”localhost”, user=”your_username”, password=”your_password”, database=”flask_demo” ) cursor = db.cursor()

@app.route(‘/’) def index(): return render_template(‘index.html’)

@app.route(‘/submit’, methods=[‘POST’]) def submit(): if request.method == ‘POST’: name = request.form[‘name’] email = request.form[‘email’]

:   Insert data into the database
    sql = "INSERT INTO users (name, email) VALUES (%s, %s)"
    val = (name, email)
    cursor.execute(sql, val)
    db.commit()

    return 'Data Submitted Successfully!'

if name == ‘main’: app.run(debug=True)

## 4: Create HTML Template
Create a folder named templates inside your project directory, and inside it, create a file named index.html(Given below is the output of the html file):
![alt text](https://github.com/ManavRaval/myImages/blob/main/cloud_img4.png?raw=true)

## 5: Run the Application
Navigate to your project directory in the terminal and run the Flask application: python app.py

## 6: Visit the localhost
Visit http://localhost:5000 in your web browser, fill out the form, and submit. The data should be stored in the MySQL database.

## 7: Done
Your webapplication is created and ready for the local use!

        -- Thanks for reading. Feel free to reach me with any suggestions! 