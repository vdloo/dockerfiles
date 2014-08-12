# Run Dwarf Fortress in a docker container and connect with VNC
# 
# Example
# Start with: docker run -p 5900:5900 -v /saves:/df_linux/data/saves -i -t df /bin/bash
# Then on desktop connect vnc with: vncviewer 192.168.x.x
#
# Based on https://github.com/pgrange/docker-dwarf_fortress_lnp

FROM tianon/debian:latest

RUN dpkg --add-architecture i386

RUN apt-get update && apt-get -y upgrade

RUN apt-get -y install default-jre libsdl1.2debian:i386 libsdl-image1.2:i386 libsdl-ttf2.0-0:i386 libglu1-mesa:i386 libgtk2.0-0:i386 libopenal1:i386 libjpeg62:i386 git mercurial libqt4-dev qt4-qmake wget coreutils tar unzip make g++ gcc patch xterm sed python bzip2 x11vnc xvfb

RUN wget http://www.bay12games.com/dwarves/df_40_06_linux.tar.bz2; tar xjf *.tar.bz2; cp -R df_linux /bin

RUN /bin/echo -e '#!/bin/bash\nXvfb -screen 0 1920x1080x16 -ac &\nDISPLAY=:0 x11vnc &\nDISPLAY=:0 /bin/df_linux/df' >> /bin/startdf; chmod u+x /bin/startdf

EXPOSE 5900

CMD startdf
