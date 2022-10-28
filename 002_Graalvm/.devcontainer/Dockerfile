FROM ghcr.io/graalvm/graalvm-ce:22.3.0

RUN microdnf install maven-1:3.6.3-14.el9.noarch -y; \
    microdnf install git-2.31.1-2.el9.2.x86_64 -y; \
    rm /etc/alternatives/java; \
    rm /etc/alternatives/javac; \
    ln -s /opt/graalvm-ce-java17-22.3.0/bin/javac /etc/alternatives/javac; \
    ln -s /opt/graalvm-ce-java17-22.3.0/bin/java /etc/alternatives/java; \
    export JAVA_HOME=/opt/graalvm-ce-java17-22.3.0; \
    export GRAALVM_HOME=/opt/graalvm-ce-java17-22.3.0; \
    export PATH=${GRAALVM_HOME}/bin:$PATH; \
    echo 'JAVA_HOME=/opt/graalvm-ce-java17-22.3.0' > /etc/java/maven.conf; \
    gu install native-image

RUN mkdir /root/.m2; \
    mkdir /workspace; \
    chmod 777 /workspace

ADD resources/.bashrc /root/