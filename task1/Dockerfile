# Use the latest version of Ubuntu as a parent image
FROM ubuntu:latest

# Update the package lists for upgrades for packages that need upgrading
RUN apt-get update -y

# Upgrade all the installed packages
RUN apt-get upgrade -y

# Install Python3 and pip3
RUN apt-get install -y python3 python3-pip

# If you get a This environment is externally managed error when trying to install Python packages, add the following line before calling pip on your Dockerfile
RUN rm /usr/lib/python*/EXTERNALLY-MANAGED || true

# Install Flask using pip3
RUN pip3 install flask

# Set the working directory to /app
WORKDIR /app

# Copy the current directory contents into the container at /app
COPY ./api.py /app/api.py

# Make port 5252 available to the world outside this container
EXPOSE 5252

# Run api.py when the container launches
CMD ["python3", "api.py"]
