FROM jetbrains/teamcity-minimal-agent:latest

USER root
RUN apt-get update && \
    apt-get -y --no-install-recommends install \
	dirmngr \
	curl \
	gpg-agent \
	ca-certificates \
	software-properties-common \
	apt-transport-https \
	wget \
	zip \
	git \
	locales

RUN apt-get update && \
	apt-get install -y build-essential && \
	curl -sL https://deb.nodesource.com/setup_16.x | bash - && \
	apt-get install -y nodejs && \
	apt-get install -y man && \
	apt-get clean all

RUN wget https://packages.microsoft.com/config/ubuntu/20.04/packages-microsoft-prod.deb -O packages-microsoft-prod.deb && dpkg -i packages-microsoft-prod.deb
RUN apt-get update && apt-get install -y dotnet-sdk-6.0