FROM ubuntu:20.04

COPY . /root/install
RUN DEBIAN_FRONTEND=noninteractive apt-get update && \
    apt-get install -y gnupg2 python3-pip sshpass git openssh-client && \
    rm -rf /var/lib/apt/lists/* && \
    apt-get clean

RUN python3 -m pip install --upgrade pip cffi && \
    pip --quiet install -r /root/install/req.txt \
    ansible-galaxy install -r /root/install/req.yml
    rm -rf /root/.cache/pip
WORKDIR /root/install

CMD [ "/bin/bash" ]