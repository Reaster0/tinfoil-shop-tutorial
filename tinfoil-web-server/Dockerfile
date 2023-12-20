FROM debian:latest

# install dependencies
RUN apt update -y && apt install -y \
	curl \
	unzip \
	libicu-dev

# download the latest release of the app, extract it and remove the zip etc
RUN latest_release_url=$(curl -s https://api.github.com/repos/Myster-Tee/TinfoilWebServer/releases/latest | grep "browser_download_url" | grep "Independent-linux-x64.zip" | cut -d '"' -f 4) \
    && curl -L -o release.zip $latest_release_url \
    && unzip release.zip || true \
    && rm release.zip \
	&& mv /TinfoilWebServer* /TinfoilWebServer \
	&& chmod +x /TinfoilWebServer/TinfoilWebServer

# copy the settings file from the host
COPY ./settings.json /TinfoilWebServer.config.json

# run the app
ENTRYPOINT ["/TinfoilWebServer/TinfoilWebServer"]