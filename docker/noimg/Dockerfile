# Filename: Dockerfile 
FROM python:3.8-alpine3.12

RUN apk --no-cache add curl wget

RUN mkdir /data

WORKDIR /data

RUN curl -s https://api.github.com/repos/5etools-mirror-1/5etools-mirror-1.github.io/tags | grep tarball_url | grep v. | cut -d '"' -f 4 | head -n 1 | wget -O 5etools.tar.gz -qi - && tar xzf 5etool>
#RUN cp 5etools.html index.html

VOLUME /data/homebrew

EXPOSE 7775

CMD ["python3","-m","http.server","7775"]
