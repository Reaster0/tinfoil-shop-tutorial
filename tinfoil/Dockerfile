FROM debian:latest

RUN apt update -y && apt install -y \
	curl \
	unzip \
	libicu-dev

RUN latest_release_url=$(curl -s https://api.github.com/repos/Myster-Tee/TinfoilWebServer/releases/latest | grep "browser_download_url" | grep "Independent-linux-x64.zip" | cut -d '"' -f 4) \
    && curl -L -o release.zip $latest_release_url \
    && unzip release.zip || true \
    && rm release.zip

RUN mv /TinfoilWebServer* /TinfoilWebServer

RUN chmod +x /TinfoilWebServer/TinfoilWebServer

COPY ./TinfoilWebServer.config.json /TinfoilWebServer/TinfoilWebServer.config.json

ENTRYPOINT ["/TinfoilWebServer/TinfoilWebServer"]