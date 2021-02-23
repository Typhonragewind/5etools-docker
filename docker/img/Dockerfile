# Filename: Dockerfile 
FROM python:3.8-alpine3.12

RUN apk --no-cache add curl unzip

RUN mkdir /data

WORKDIR /data

RUN curl --output 5etools.zip https://get.5e.tools/src/ && unzip 5etools.zip && rm 5etools.zip

RUN curl --output 5etools_img.zip https://get.5e.tools/img/ && unzip 5etools_img.zip && mv tmp/5et/img . && rm -r tmp && rm 5etools_img.zip

RUN cp 5etools.html index.html

VOLUME /data/homebrew

EXPOSE 7775

CMD ["python3","-m","http.server","7775"]
