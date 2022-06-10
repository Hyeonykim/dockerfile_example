from jenkins/jenkins:lts

ENV JENKINS_USER admin
ENV JENKINS_PASS admin

USER root

# Skip jenkins setup wizard
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

# Change timezone
RUN ln -sf /usr/share/zoneinfo/Asia/Seoul /etc/localtime
RUN dpkg-reconfigure --frontend noninteractive tzdata

ENTRYPOINT ["/bin/sh", "-c", "/usr/local/bin/jenkins.sh"]
