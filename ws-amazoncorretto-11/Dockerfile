FROM maven:3.6-amazoncorretto-11

RUN yum install -y git \
  && yum install -y wget \
  && yum install -y unzip \
  && wget https://github.com/protocolbuffers/protobuf/releases/download/v3.11.4/protoc-3.11.4-linux-x86_64.zip \
  && mkdir -p /opt/protocolbuffers/protobuf-compiler \
  && unzip protoc-3.11.4-linux-x86_64.zip -d /opt/protocolbuffers/protobuf-compiler \
  && ln -sf /opt/protocolbuffers/protobuf-compiler/bin/protoc /usr/local/bin/protoc
  
RUN git config --global user.email "wonderstorm.teamcity@gmail.com" \
  && git config --global user.name "wonderstorm-teamcity"

ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
CMD ["mvn"]
