FROM debian:latest

RUN apt update -y && apt install -y \
	wget \
	unzip \
	git

RUN mkdir /app

WORKDIR /app

RUN wget https://github.com/giwty/switch-library-manager/releases/latest/download/switch-library-manager.Console.linux.zip -O switch-library-manager.zip

RUN unzip switch-library-manager.zip || true
RUN rm switch-library-manager.zip
RUN chmod +x ./switch-library-manager
# need to run once to download the latest games list
RUN ./switch-library-manager

COPY ./settings.json ./settings.json
COPY ./prod.keys ./prod.keys

ENTRYPOINT ["./switch-library-manager"]