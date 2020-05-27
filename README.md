<div>
  <img src="https://raw.githubusercontent.com/feednext/feednext/master/server/public/logo-wide.png" alt="Brand Logo"/>

  <p align="center">
    <a href="https://github.com/feednext/feednext/commits/master">
      <img src="https://img.shields.io/github/commit-activity/m/feednext/feednext?style=flat-square" alt="Commit Activity" />
    <a/>
    <a href="https://github.com/feednext/feednext/issues?q=is%3Aissue+is%3Aclosed">
      <img src="https://img.shields.io/github/issues-closed-raw/feednext/feednext?style=flat-square&colorB=blue" alt="Closed Issues" />
    <a/>
    <a href="https://github.com/feednext/feednext/blob/master/COPYING">
      <img src="https://img.shields.io/github/license/feednext/feednext?style=flat-square&colorB=black" alt="License"/>
    </a>
    <a href="#">
      <img src="https://img.shields.io/badge/PRs-welcome-brightgreen?style=flat-square" alt="Extra Info"/>
    <a/>
  </p>

  ## What is this all About ?
  feednext.io is an open source social media platform of the Feednext organization, founded by Software Engineer [Onur Ozkan](https://github.com/ozkanonur). The main purpose of the project is to inform people around the world about any physical or a virtual object from a single central source. Like a phone model, TV, Computer components or a Song even. By doing that with the best way, this platform will turn into a central system of information distribution about product reviewing around the world.

  - [Installation](https://github.com/feednext/feednext#installation)
  - [Contributing](https://github.com/feednext/feednext#contributing)
  - [Issue Tracking](https://github.com/feednext/feednext/issues)
  - [Support](https://github.com/feednext/feednext#support)

  ## Installation
  #### Requirements
  | Technology | Version |
  | ------ | ------ |
  | Docker | * |
  | Docker Compose | * |
  | Node | 12 |

  ### RUNNING API
  After you have cloned this repository to your machine, cd into project folder and then create .env files from .env.example ones with following command:

  ```bash
  cp .env.example .env && cp ./server/.env.example ./server/.env
  ```
  Once .env files are created successfully, now you can run the api on your local by running following command:

  ```bash
  make dev
  ```
  With the command above, api will start running on http://localhost

  #### WARNING (For Osx & Windows Users)
  The way of Docker (Linux containers) works on non-linux machines are pretty messy. With feednext, we have whole project folder passed into linux containers synchronously which works crystal clear on Linux machines. But, on non-linux machines it enforces your machine's drive pretty hard. For non-linux users, we have an alternative development way, instead of passing project folder, we will only use mongo and redis as containers and then will start api manually below the server directory.

  Start mongo and redis containers:
  ```bash
  make dev2
  ```
  cd into server directory, and update the following values in .env file:
  ```
  DB_HOST=localhost:27017
  REDIS_HOST=localhost
  ```

  Install dependencies:
  ```bash
  npm ci
  ```

  Run API:
  ```bash
  npm run start:dev
  ```

  Right after the command above, api will start running on http://localhost:3000

  ### RUNNING FRONTEND
  cd into client directory and then:
  ```bash
  npm run start:dev
  ```

  If you follow the Osx & Windows way for running API, then apply following changes on /config/constants.ts:
  ```ts
  export const API_URL = 'http://localhost:3000/api'
  export const SOCKET_URL = 'http://localhost:3000'
  ```

  ## Contributing
  Technically, feednext.io is developed with Software Patterns & Design Principles all around it. PRs are welcome as long as they are fits in the principles, structure of the feednext.io.

  Please do not directly PR to 'master' branch, instead go for 'dev' branch.

  ### Styleguilde
  #### Commit Messages
  - If you have changed things below the server or client directories, commit messages must have [server] or [client] prefix.
  - Commit messages should never include emojies
  - Commit messages must be imperative like "Add stuff" not "Added stuff"

  #### Coding
  - Do not break the eslint rules.

</div>
