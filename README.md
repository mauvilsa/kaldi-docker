# NAME

kaldi-docker - [Kaldi](https://github.com/kaldi-asr/kaldi) installed in a docker image and accessible through a command line interface.

# INSTALLATION AND USAGE

The docker image is available in docker hub, see the respective [docker hub page](https://hub.docker.com/r/mauvilsa/kaldi/).

To install first pull the docker image tag of your choosing, using a command such as:

    docker pull mauvilsa/kaldi:TAG

The image could be used for extending it but it also provides a command line interface so that the Kaldi tools can be used from the host system like any other command.

## Command line interface

First you need to copy the command line interface script to some directory in your path.

    docker run --rm -it -u $(id -u):$(id -g) -v $HOME:$HOME mauvilsa/kaldi:TAG bash -c "cp /usr/local/bin/kaldi-docker $HOME/bin"

Then the docker image needs to be tagged as kaldi:active to indicate to the command line interface which is the image tag to use.

    docker tag mauvilsa/kaldi:TAG kaldi:active

After this, the tool can be used like any other command, i.e.

    kaldi-docker --help
    kaldi-docker COMMAND [ARGUMENTS]

The MIT License (MIT)

Copyright (c) 2018-present, Mauricio Villegas <mauricio_ville@yahoo.com>
