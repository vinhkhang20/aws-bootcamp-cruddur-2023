FROM python:3.10-slim-buster

# Inside Container - make a new folder inside the container
WORKDIR /backend-flask

# Outside Container --> Inside Container - This file contains the libraries 
COPY requirements.txt requirements.txt
# Inside Container - Install the python libraries used for the app
RUN pip3 install -r requirements.txt

# Outside Container --> Inside Container
# . means everything in the current directory

COPY . .

# Inside Container - Set environment Vars 
ENV FLASK_ENV=development

EXPOSE ${PORT}

# python3 -m flask run --host=0.0.0.0 --port=4567
# change the link to https://4567-vinhkhang20-awsbootcamp-0qwcgtnftvp.ws-us87.gitpod.io/api/activities/home
CMD ["python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]


# # Stage 1: Build the application
# FROM python:3.10-slim-buster AS build
# WORKDIR /backend-flask
# COPY requirements.txt .
# RUN pip install --user -r requirements.txt
# COPY . .

# # Stage 2: Build the final image
# FROM python:3.10-slim-buster
# WORKDIR /backend-flask
# COPY --from=build /root/.local /root/.local
# COPY --from=build /app .
# ENV PATH=/root/.local/bin:$PATH
# ENV FLASK_ENV=development
# EXPOSE ${PORT}
# CMD [ "python3", "-m" , "flask", "run", "--host=0.0.0.0", "--port=4567"]
