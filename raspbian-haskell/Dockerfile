# Raspbian (arm7) + haskell ssh accessible server

FROM      quid2/raspbian-haskell

# sshd port
EXPOSE 22

# sshd dir
RUN mkdir -p /var/run/sshd

# copy all files
ADD . .

# Make VM accessible with my SSH key
RUN ["chown","-R","root:root","/root"]

CMD /DockerStart
