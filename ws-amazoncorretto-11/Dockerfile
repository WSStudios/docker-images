FROM maven:3.6-amazoncorretto-11

RUN yum install -y git
  
RUN git config --global user.email "wonderstorm.teamcity@gmail.com" \
  && git config --global user.name "wonderstorm-teamcity"

ENTRYPOINT ["/usr/local/bin/mvn-entrypoint.sh"]
CMD ["mvn"]
