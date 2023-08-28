FROM debian:latest

# install dependencies
RUN apt update -y && apt install -y \
	wget \
	unzip \
	git

# the directory (in the container) where the app will be installed
RUN mkdir /app
WORKDIR /app

# download the latest release of the app, extract it and remove the zip etc
RUN wget https://github.com/giwty/switch-library-manager/releases/latest/download/switch-library-manager.Console.linux.zip -O switch-library-manager.zip \
	&& unzip switch-library-manager.zip || true \
	&& rm switch-library-manager.zip \
	&& chmod +x ./switch-library-manager

# need to run once to download the latest games list
RUN ./switch-library-manager

# copy the settings file and the prod.keys file from the host
COPY ./settings.json ./settings.json
COPY ./prod.keys ./prod.keys

# run the app
ENTRYPOINT ["./switch-library-manager"]