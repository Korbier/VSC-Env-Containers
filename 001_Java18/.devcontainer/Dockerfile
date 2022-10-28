FROM maven:3.8.6-openjdk-18

RUN apt-get update; \
    apt-get install -y  --no-install-recommends \
        git \
        zip \
        unzip \
        bash-completion \
        build-essential \
        htop \
        jq \
        less \
        locales \
        man-db \
        software-properties-common \
        sudo \
        time \
        vim \
        multitail \
        lsof \
        openssh-client iproute2 lsb-release; \
    mkdir /root/.m2; \
    mkdir /workspace; \
    chmod 777 /workspace; \
    apt-get autoremove -y; \
    apt-get clean -y; \
    rm -rf /var/lib/apt/lists/*; \
    git config --global user.name "Stephane"; \
    git config --global user.email stephane.charenton@gmail.com; \
    git config --global init.defaultBranch develop

ADD resources/.bashrc /root/
