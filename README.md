# acord-robotics
The official ACORD Robotics Github/Gitlab Repository.

# What is this repo?

ACORD is a multi-national (started in Australia) corporation that aims to push the limits of technology, science, and robotics in ways never seen before. We're led by a team full of youngsters, including our Chairman, Liam Arbuckle (@IrisDroidology) who started this from the beginning way back in 2015. 

This repository (Github/acord-robotics/acord-robotics) is a directory, or a hub, for all the different projects that ACORD does, including:

* Stellarios (software suite)
* Star Sailors (Science fiction novella series)
* DroidOS (Archived, moved into Stellarios)
* ACORD Games
* ACORD Networking
* ACORD Code
* ACORD Members
* Other

## ACORD Repositories

- [Stellarios](http://github.com/acord-robotics/stellarios) --- All news to do with Droid Building, some Stellarios info, etc is here, as well as all Stellarios code (which is also on the Stellarios repo). View the [blog here View the [blog here](http://acord-robotics.github.io/stellarios)
- [ACORD News](http://acord-robotics.github.io/acordnews) --- Basically a public blog for ACORD
- [Mushlantis & ACORD Worlds](http://gitlab.com/acord-robotics)
- [Unity Games](https://gitlab.com/IrisDroidology/unityballs)
- [Star Sailors Draft](https://gitlab.com/IrisDroidology/star-sailors) - the draft of star sailors
- [ACORD Portal](http://allianceofdroids.org.au)
- ACORD Networking
- ACORD Code
- ACORD Members
- ACORD Games

### ACORD Games

ACORD is working on a number of cool games. All of these games are open-source and are included in the Stellarios Software Suite by ACORD. Currently Asteroid Dodgers, made in the Unity Game Engine, is under development. Another game, Manacaster, is under (right now, will be acord-wide soon) personal development by @IrisDroidology.

### ACORD Networking

We aim to push the limits of what's possible with networking devices for our research and innovation, including with routers and modems (for example). 

### ACORD Code

ACORD Code, part of the Orgzy family, is a system where we build apps, games, and websites for third parties. It also includes our tutorials on coding so that anyone can learn how to code.

## Future ACORD Repositories

- [App](http://github.com/acord-robotics/app) --- All code for the app
- [Website](http://github.com/acord-robotics/website) --- ACORD portal backup
- [Stellarios Learning](http://github.com/acord-robotics/sl) --- Our journey to learning how to develop
- Different types of droids (Companion, Scientific, etc). Each category will have a repository, as well as be in the Star Sailors Repo

Every repo will be copied into Star Sailors

# Other

An example of this would be stuff to do with members' personal journeys (for example, I'm going to be posting a lot of my computer science stuff here). While this stuff is beneficial for ACORD, it doesn't belong to any particular project.

If a part of this repo becomes a project (repository) in its own right, we will continue to update it on this repo as well, but the folder name will be changed to 'project_name_(archived)'.

This repository is also home to future ACORD posts, whether they go towards the portal, medium, our acord news blog, etc.



# Orgzy Design
Orgzy Design, founded by our chairman in 2019, is a website and software development company. Orgzy work closely with ACORD and a number of our games (for example the Star Sailors game) will be based on games created by Orgzy. Orgzy are currently working on a game called "Asteroid Dodger", created in the Unity Game Engine. 

Orgzy can be thought of as a separate company that employs many ACORD programmers to create programs for ACORD. The programs created for ACORD will not be sold to the public, however Asteroid Dodger (the non-Star Sailors version) will not be private.

The code created for Asteroid Dodger will be used to create different apps/games for ACORD.

## Repositories
* [Asteroid Dodger](http://github.com/irisdroidology/unityballs)

# Member Repositories

Our members have their own personal github accounts,  where they have repositories not related to ACORD but are still worth mentioning.

### Member Accounts

* [Liam Arbuckle](http://github.com/irisdroidology) --- Our Chairman & Co-Founder publishes content to do with his schooling as well as his computer science projects. These projects will help him when it comes to developing with ACORD (which he is also doing)
* [Farid](http://github.com/mfaridn03) --- Farid is a sort of fringe member of ACORD. He helps us with Python stuff

### Other companies

* [Orgzy Design](http://github.com/orgzy-design) --- Liam Arbuckle's web development company. 20% of the profits go towards ACORD

### Liam's Repositories

* [Games](http://github.com/irisdroidology/expert-goggles) --- A number of games created in numerous languages. One is a role playing game from the perspective of the Mars rover

## Stellarios Learning
* [Raspberry Pi](https://gitlab.com/acord-robotics/robodev/s2rd-raspberry-pi)
* [C++](https://gitlab.com/IrisDroidology/cpp-tutorial-vLnPwxZdW4Y)


# Project embeds
## Games
### Asteroid Dodgers
<div style="width: 640px; height: 480px; margin: 10px; position: relative;"><iframe allowfullscreen frameborder="0" style="width:640px; height:480px" src="https://www.lucidchart.com/documents/embeddedchart/ccededa2-2c8b-4354-a0ee-f1d9b6223a91" id="M.RDRu6C6a.y"></iframe></div>
# Our members

## Farid Nurrahman
Hi there! My name is Farid, and I am excited to join ACORD and become a pioneer of the future of robotics and artificial intelligence. I like to play games and program. I currently code a lot in Python and am working on a cool discord bot that will be part of Stellarios (the official OS of ACORD). I am not always able to be active at ACORD, but I will contribute where and when I can. Here's some of my code:

```py
import aiohttp
import random


class Url:
    def __init__(self):
        self.apiUrl = "https://xkcd.com/{}/info.0.json"
        self.comicUrl = "https://xkcd.com/{}"
        self.explainUrl = "https://explainxkcd.com/{}"
        self.infoUrl = "https://xkcd.com/info.0.json"


url = Url()


class Comic:
    def __init__(self, json_info: dict):
        self.info = json_info
        self.title = json_info["safe_title"]
        self.alt_text = json_info["alt"]
        self.image = json_info["img"]
        self.num = json_info["num"]
        self.explanation = url.explainUrl.format(self.num)
        self.url = url.comicUrl.format(self.num)


async def fetch_json(num: int):
    link = url.apiUrl.format(num)
    async with aiohttp.ClientSession() as session:
        async with session.get(link) as resp:
            assert resp.status == 200  # To make sure there are no errors
            return await resp.json()


async def comic_check(c_num):
    async with aiohttp.ClientSession() as ses:
        async with ses.get(url.infoUrl) as res:
            e = await res.json()
    latest_comic = e["num"]
    return int(latest_comic), int(c_num) <= int(latest_comic)


async def get_comic(num):
    num = int(num)

    try:
        assert (await comic_check(num))[1]
    except AssertionError:
        return None

    j = await fetch_json(num)  # returns a json object
    return Comic(j)


async def get_random_comic():
    lim, _ = await comic_check(1)  # Find the latest comic num
    return await get_comic(random.randint(1, lim))


async def get_latest_comic():
    latest_num, _ = await comic_check(1)
    return await get_comic(latest_num)

```

## RexOfSpoon17
https://www.tapatalk.com/groups/acordrobotics/hello-from-rexton-t6.html#p12 - link to intro of RexOfSpoon

## j-brkr
I might be a human...
