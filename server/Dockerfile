FROM ubuntu:16.04
RUN apt update && apt upgrade -y && apt install -y libxml2-utils curl screen
LABEL maintainer="dylan.bersans@eisti.eu"
RUN useradd -m urt
RUN su - urt
RUN mkdir /home/urt/urbanterror43
WORKDIR /home/urt/urbanterror43
COPY UrTUpdater_Ded.sh /home/urt/urbanterror43
RUN chown -R urt:urt /home/urt/urbanterror43
RUN chmod a+x UrTUpdater_Ded.sh
RUN ./UrTUpdater_Ded.sh
COPY server.cfg /home/urt/urbanterror43/q3ut4/
COPY mapcycle.txt /home/urt/urbanterror43/q3ut4/
COPY start.sh /root
EXPOSE 27960
CMD ["/root/start.sh"]
