# Use the base App Engine Docker image, based on debian jessie.
FROM launcher.gcr.io/google/debian8

# Install updates and dependencies
RUN apt-get update -y && apt-get install --no-install-recommends -y -q curl python build-essential git ca-certificates libkrb5-dev imagemagick && \
    apt-get clean && rm /var/lib/apt/lists/*_*

# Install the latest LTS release of nodejs
RUN mkdir /nodejs && curl https://nodejs.org/dist/v8.9.3/node-v8.9.3-linux-x64.tar.gz | tar xvzf - -C /nodejs --strip-components=1
ENV PATH $PATH:/nodejs/bin

# Install the latest stable release of Yarn
RUN mkdir /yarn && curl -L https://github.com/yarnpkg/yarn/releases/download/v1.3.2/yarn-v1.3.2.tar.gz | tar xvzf - -C /yarn --strip-components=1
ENV PATH $PATH:/yarn/bin

ENTRYPOINT ["yarn"]
