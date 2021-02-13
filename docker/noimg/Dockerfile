# Filename: Dockerfile 
FROM python:3.8-alpine3.12

RUN apk --no-cache add curl
RUN apk add unzip

RUN mkdir /data

WORKDIR /data

RUN curl --output 5etools.zip https://get.5e.tools/release/ && unzip 5etools.zip && rm -Rf 5etools.zip

RUN cp 5etools.html index.html

VOLUME /data/homebrew

EXPOSE 7775

CMD ["python3","-m","http.server","7775"]