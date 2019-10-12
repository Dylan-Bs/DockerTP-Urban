FROM ubuntu:16.04
LABEL maintainer="dylan.bersans@eisti.eu"
# Updates and installation of some libraries
RUN apt update && apt upgrade -y && apt install -y libxml2-utils
# Creation of new user for more security
RUN useradd -m urt
# Login with the new user
RUN su - urt
# Make a new directory
RUN mkdir /home/urt/urbanterror43
# Change directory
WORKDIR /home/urt/urbanterror43
# Copy of script for installation and configuration
COPY UrTUpdater_Ded.sh /home/urt/urbanterror43
COPY server.cfg /home/urt/urbanterror43/q3ut4/
COPY mapcycle.txt /home/urt/urbanterror43/q3ut4/
COPY start.sh /root
# Update of permission
RUN chown -R urt:urt /home/urt/urbanterror43
RUN chmod a+x UrTUpdater_Ded.sh
# Installation of the server
RUN ./UrTUpdater_Ded.sh
# Open the port 27960 for connections
EXPOSE 27960
# When the container start, the server start too
CMD ["/root/start.sh"]