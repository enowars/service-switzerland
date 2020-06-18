FROM python:3.7

# Install uswgi
RUN pip3 install gunicorn[eventlet]

WORKDIR /checker

# install requirements
COPY ./requirements.txt /checker/requirements.txt
RUN pip3 install -r requirements.txt
COPY ./gunicorn.conf.py /checker/gunicorn.conf.py

# here you might need to add more stuff
COPY ./checker.py checker.py

ENTRYPOINT ["gunicorn", "-c", "gunicorn.conf.py", "checker:app"]
