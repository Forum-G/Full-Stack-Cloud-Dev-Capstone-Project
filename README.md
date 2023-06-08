# Full Stack Django Cloud Development Project

This repository contains the code for a full stack Django web application hosted in the IBM Cloud. The application serves as a car dealership's car review platform.

## Background
This project was developed as the final Capstone Project for the IBM Full Stack Cloud Developer Professional Certificate on Coursera. The initial version of the Django application provided was basic, lacking central functionality or templates. The overall architecture and idea for the application were provided by Coursera, along with most of the design and layout. Due to the peer-review process and strict requirements, the focus was primarily on implementing the specified functionality and back-end services, rather than improving the front-end design or user experience.

## Project Requirements
The goal of this project is to build a website that allows users to select one of *Best Car*'s dealerships (a fictional company) in the US and view reviews of the dealership's cars submitted by other users. Users can also submit their own reviews. The website is built using the Python-Django full stack web development framework and is deployed with Red Hat OpenShift/Kubernetes on the IBM Cloud.

## Architecture


The dealership and review data are stored in an IBM Cloudant database, while data about users and cars is stored in a simple SQLite database. To access data from IBM Cloudant, three IBM Cloud Functions were created, which are accessible through an API. Each review is analyzed by IBM Watson to determine its general sentiment (negative, neutral, positive).

## Setup
To run the project locally, follow these steps:

1. Clone the project:
   - ```cd Full\ Stack\ Cloud\ Dev\ Capstone\ Project/server```

2. Install the required Python packages:
   - ```python -m pip install -r requirements.txt```

3. Create a [new Django Secret Key](https://humberto.io/blog/tldr-generate-django-secret-key/).

4. Run the development server:
   - ```python manage.py createmigrations```
   - ```python manage.py migrate```
   - ```python manage.py runserver```

5. Create a new superuser:
   - ```python manage.py createsuperuser```
   - Log in via the admin site (add `/admin` to the URL)

6. Push to IBM Cloud Foundry:
   - Install the IBM Cloud CLI and the Cloud Foundry plugin.
   - Configure the `manifest.yml` file.
   - ```ìbmcloud cf push```

