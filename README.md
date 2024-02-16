# Unofficial Passbolt CLI for Testing

## What it is / What it does



## Quickstart

### Linux and MacOS

#### Download Once No Updates - Version

Decide for a path where to put the frontend cli `pb`.

(of yourse replace `/your/pb` in both commands!!)

Download

    curl -L -o /your/pb 'https://raw.githubusercontent.com/robertconnect/pb/main/docker/pb/src/pb'

and make it executable

    chmod a+x /your/pb

#### Git checkout and symlink

Decide for a path where to put the frontend cli `pb`.

Also decide for a path where to checkout the repo.

Assumed you checkout https://github.com/robertconnect/pb to `~/src/github/pb`.

Assumed you have a `~/bin` folder already added to your `PATH`.

    cd ~/bin && ln -s ~/src/github/pb/main/docker/pb/src/pb

will create a symlink so you can always use the latest `pb` script in your `PATH` after pulling the repo.
