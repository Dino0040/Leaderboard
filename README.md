## About

This repo contains all that is needed to host and use a server providing leaderboards for games.

## Using the free leaderboard server

If all you want is a free leaderboard in your application download one of the client implementations for your game engine and log in using itch.io on [this page](https://exploitavoid.com/leaderboards/) to create and manage your leaderboards.

*DISCLAMER: I will use the public server myself for future jam games so have the intention to keep it up for as long as I can with as few outages as possible, but there are no guarantees. To prevent abuse the MAX_\* rate limits defined in the main.py of the repo are in place - be nice!*

The API is currently under heavy development and may change in drastic ways. Either host your own server or wait for the first stable release if you can not live with breaking changes.

## Hosting a leaderboard server yourself

**Install the required packages using your package manager:**

`apt install sqlite3 python3 python3-pip`

**Create the database file:**

`sqlite3 leaderboards.db '.read leaderboards.sql'`

**Install the python packages required for the server using pip:**

`pip install fastapi requests uvicorn`

(You can replace uvicorn with any other ASGI server)

**Start the server:**

`uvicorn main:app`

**Host the webinterface Clients/index.html using any webserver**

The itch OAuth link in the index.html has to be changed to one you generate yourself using [their site](https://itch.io/user/settings/oauth-apps).

Your webserver also has to redirect urls in the form of your.domain/api to the uvicorn server.


(Todo: Make hosting own webinterface and server easier - Docker?)
