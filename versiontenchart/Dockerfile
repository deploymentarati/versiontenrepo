FROM tomcat:10.1.18
# Example Dockerfile snippet

RUN apt-get update && apt-get install -y curl docker.io


RUN mkdir -p /var/lib/jenkins/workspace/repo1
# Install Helm
RUN curl -fsSL -o /tmp/get_helm.sh https://raw.githubusercontent.com/helm/helm/master/scripts/get-helm-3 \
    && chmod +x /tmp/get_helm.sh \
    && /tmp/get_helm.sh \
    && rm /tmp/get_helm.sh

# Copy the Helm chart into the container
COPY . /var/lib/jenkins/workspace/repo1

# Set the working directory to the location of the Helm chart
WORKDIR /var/lib/jenkins/workspace/repo1

# Define default command to run when the container starts
CMD ["catalina.sh", "run"]
