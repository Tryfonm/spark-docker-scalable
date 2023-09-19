FROM openjdk:11.0.11-jre-slim-buster

RUN apt update -y && apt upgrade -y 
RUN apt install -y curl wget nano iproute2 iputils-ping software-properties-common ssh net-tools ca-certificates 
RUN python3 python3-pip python3-numpy python3-matplotlib python3-scipy python3-pandas python3-simpy
RUN update-alternatives --install "/usr/bin/python" "python" "$(which python3)" 1

ENV SPARK_VERSION=3.0.2 \
    HADOOP_VERSION=3.2 \
    SPARK_HOME=/opt/spark \
    PATH="SPARK_HOME:${PATH}"

RUN wget --no-verbose -O apache-spark.tgz "https://archive.apache.org/dist/spark/spark-${SPARK_VERSION}/spark-${SPARK_VERSION}-bin-hadoop${HADOOP_VERSION}.tgz" \
    && mkdir -p /opt/spark \
    && tar -xf apache-spark.tgz -C /opt/spark --strip-components=1 \
    && rm apache-spark.tgz

EXPOSE 8080 7077

COPY spark-defaults.conf /opt/spark/conf/
WORKDIR /opt/spark/workspace

CMD ["/bin/bash"]
