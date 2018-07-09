#!/bin/bash
FROM ubuntu:16.04
RUN apt-get update && apt-get install -y unzip

# Install IBM Installation Manager
COPY agent.installer.linux.gtk.x86_64_*.zip /tmp/
RUN unzip -qd /tmp/im /tmp/agent.installer.linux.gtk.x86_64_*.zip \
  && /tmp/im/installc -acceptLicense -accessRights nonAdmin \
    -installationDirectory "/opt/IBM/InstallationManager"  \
    -dataLocation "/var/ibm/InstallationManager" -showProgress \
  && rm -rf /tmp/agent.installer.linux.gtk.x86_65_*.zip /tmp/im

ENV PATH /opt/IBM/InstallationManager/eclipse/tools:$PATH
