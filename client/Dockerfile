FROM ubuntu:16.04
LABEL maintainer="dylan.bersans@eisti.eu"
# Updates and installation of some graphicals libraries
RUN apt update && apt upgrade -y && apt install -y unzip && apt-get install -y --reinstall libsdl1.2debian libxxf86vm1 libgl1-mesa-glx
# Changing of directory
WORKDIR /root
# Downloading of the game, ~1,4GB
ADD http://cdn.urbanterror.info/urt/43/releases/zips/UrbanTerror434_full.zip /root/
# Extract the zip
RUN unzip UrbanTerror434_full.zip
# Removing the archive
RUN rm -rf UrbanTerror434_full.zip
WORKDIR /root/UrbanTerror43/
# let's play!
CMD ./Quake3-UrT.x86_64

