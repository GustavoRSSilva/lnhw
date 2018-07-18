# base image
FROM python:3.7-alpine

# set working directory
COPY ./rpc /usr/src/rpc
WORKDIR /usr/src/rpc

# build the requirements
ADD rpc/requirements.txt /usr/src/rpc
RUN pip3 install -r /usr/src/rpc/requirements.txt

RUN pip3 install virtualenv
RUN python3 -m virtualenv env

# TODO - Add the link to the ln container
RUN ln -s ~/.lightning/lightning-rpc ./lightning-rpc

# start app
CMD ["flask", "run"]
