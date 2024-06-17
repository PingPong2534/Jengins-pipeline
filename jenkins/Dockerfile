# Use the official Jenkins LTS image as the base
FROM jenkins/jenkins:2.462-jdk21

# Skip the initial setup wizard
ENV JAVA_OPTS -Djenkins.install.runSetupWizard=false

# Define volume for Jenkins data
VOLUME /var/jenkins_home

# Install plugins
COPY backup/plugins /var/jenkins_home/plugins

# Expose necessary ports
EXPOSE 8080
EXPOSE 50000

# Set correct permissions for plugins
USER root
RUN chown -R jenkins:jenkins /var/jenkins_home/plugins
USER jenkins