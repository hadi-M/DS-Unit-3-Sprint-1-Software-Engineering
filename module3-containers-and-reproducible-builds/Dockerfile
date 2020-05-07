# Dockerfile

FROM debian

### So logging/io works reliably w/Docker
ENV PYTHONUNBUFFERED=1
### UTF Python issue for Click package (pipenv dependency)
ENV LC_ALL=C.UTF-8
ENV LANG=C.UTF-8
### Need to explicitly set this so `pipenv shell` works
ENV SHELL=/bin/bash

### Basic Python dev dependencies
RUN apt-get update && \
  apt-get upgrade -y && \
  apt-get install python3-pip curl -y && \
  pip3 install pipenv

### Install via pip or pipenv:
RUN pip3 install pandas
RUN pip3 install tabulate
RUN pip3 install sklearn
RUN pip3 install --index-url https://test.pypi.org/simple/ lambdata-hadi-M==1.0.4
RUN python3 -c "from lambdata_hadi_M.my_mod_1 import *"
#RUN pipenv install pandas
