FROM codenvy/angular-yeoman

ADD $app$/package.json /tmp/application/package.json

RUN cd /tmp/application && npm install

VOLUME ["/home/user/application"]

# 1. Update permissions
# 2. Copy nodejs modules to the application folder
# 3. Update permissions recursively
# 4. Makes newly created files accessible for anyone
# 5. Start application
CMD sudo chmod a+rw /home/user/application/ && \
    cp -a /tmp/application/node_modules /home/user/application/ && \
    sudo chmod a+rw -R /home/user/application/ && \
    umask 0 && \
    grunt $taskName:-server$
    
