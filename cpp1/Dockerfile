FROM ubuntu:latest

RUN apt-get update && apt-get install -y \
    python3 \
    python3-pip \
    python3-venv \
    git \
    wget \
    curl \
    vim \
    zip \
    unzip \
    nano \
    jq \
    cron

    # Create a non-root user
    RUN useradd -m myuser

    # Switch to the new user
    USER myuser

    WORKDIR /home/myuser

    # Create a Python virtual environment
    RUN python3 -m venv venv

    # Activate the virtual environment
    RUN . venv/bin/activate

    # Install Python packages
    COPY requirements.txt .
    RUN pip install -r requirements.txt

    # Clean up
    RUN rm requirements.txt 

    # Deactivate the virtual environment
    RUN deactivate

    # Set the default command
    CMD ["/bin/bash"]


