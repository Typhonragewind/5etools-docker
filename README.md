# 5etools-docker

## About
This is my implementation of the awesome 5etools website, for offline use, on a docker image.

## Disclaimer

This image is targeted towards self-hosting and small environments, for the purpose of offline access.
I have no affiliation with 5etools developers and take absolutely no credit for the content of the website.

This image is a result of me wanting to improve my docker skills, and is my first ever image. Any comments or suggestions are greatly appreciated.


## Installation and updating

### Installation
The preferred method to get this image up and running is through the use of *docker-compose* (examples below).

There are two available tags, **img** and **noimg**, which include and exclude image files, respectively. The **noimg** is of course much lighter.

docker-compose.yml example:
```yaml
version: '3'
services:
    5etools:
        restart: always
        container_name: 5etools
        image: typhonragewind/5etools:img
        ports:
            - 7775:7775
        volumes:
            - ./5etools/homebrew:/data/homebrew
            # - ./5etools/data:/data   #uncomment this line and comment the homebrew line only if you want to use the second updating option
```

### Updating

There are 2 ways to update the container to the newer version of 5etools:

1. Simply pull the latest image from dockerhub and make sure that the entire /data folder is **not** persisted. The /data/homebrew folder can be persisted safely.
2. While having the /data foler persisted, simply delete it's contents (excluding homebrew) and replace them with the newly downloaded files from the 5etools website source.

Option 1 is simple and easy, but consumes more bandwidth and space. 
Option 2 is a tad more complicated, but not overly so, and is advantageous if you have have limited bandwidth/space. This is also the option to take if you want to implement the automatic updating script found in the 5etools wiki. (Thanks **ryanvito** for the suggestion)

## Final words

A big thank you for the 5etools developers and PR and their amazing work. They are great people!
