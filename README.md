# What's this repo?

I'm a big fan of VSCode's devcontainers. I also know that it's kinda hard to get started with them. This repository will contain various configurations for devcontainers that is meant to be used as starting point for my own work, or for you to reference as you build your own development environment that you're familiar with. To find a configuration that's good for you, look at all the
branches that are available - the name of the branch and the README file in that would give you a good idea of what it's supposed to be ideal for.

## How do I use this?

TL;DR: you can start using it simply by opening the repository folder within VSCode, and you'll get a pop-up asking if you want to work inside the container. And it'll work on almost anybody else's system (with significantly low effort). Find more setups in the branches of this repository.

If you somehow stumbled upon this by accident, and have no idea what you're looking at, I've attempted a gist below.

If you work closely in Data Science, or in Machine Learning, you'll eventually come to a point of frustration with package or environment management - meaning, there'll be some random package which, when installed into your environment, with either `pip` or `conda` or any other tool under the sun, will break your entire environment if you aren't careful. I wasn't, and I've been so annoyed when suddenly out of the blue nothing works, and you've got to rebuild your environment from scratch.

I've often found that there are two solutions to this - meticulously learning a particular package manager and sticking to it on your own local system, or using a container system like Docker. `pip` isn't very good at managing dependencies, `conda` is agonizingly slow, and anything that builds on top of these tools isn't something I've found to be my cup of tea. Docker, on the other hand, effectively allows me to "magically" recreate an environment such that everything just works. Almost always.

VSCode has a layer on top of Docker, called devcontainer (the specification is open source, but it's not really that popular among other IDEs). If you happen to use it, then it is capable of automatically detecting when there is a container configuration available to it, and then make its interface accessible as if it were running *within* that container. This means that if I set the container's working directory to the repository's directory, I effectively can manipulate the file-system as if I were in the container, but also access it freely on my computer!

This configuration is stored in the `.devcontainer` folder, and uses a combination of a `Dockerfile` a Docker Compose configuration, and a `devcontainer.json` configuration on top of that. That's of course three different mini-languages and styles of storing configurations, but it's relatively standard, so it works.

## What's to beware?

MacOS, specifically starting from the M series of chips do have problems with Docker on VPNs, but if you can handle that occasional hiccup, you should be just fine.