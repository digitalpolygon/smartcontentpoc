# Smart Content

[![Github Actions](https://github.com/digitalpolygon/smartcontentpoc/actions/workflows/build_deploy_and_test.yml/badge.svg)](https://github.com/digitalpolygon/smartcontentpoc/actions/workflows/build_deploy_and_test.yml)
[![Dashboard smartcontentpoc](https://img.shields.io/badge/dashboard-smartcontentpoc-yellow.svg)](https://dashboard.pantheon.io/sites/81d0d72f-3257-43f2-a7fe-333c0b2bee9f#dev/code)
[![Dev Site smartcontentpoc](https://img.shields.io/badge/site-smartcontentpoc-blue.svg)](http://dev-smartcontentpoc.pantheonsite.io/)

## Local Development Setup
The team will utilize Docker for local development to help streamline the process and reduce any environment-specific issues that may arise.
### Project Dependencies

* [PHP 7.4](http://php.net/manual/en/install.php)
* [Docker](https://www.docker.com/products/docker-desktop)
* [DDev](https://ddev.readthedocs.io/en/stable/#installation)
### Installing Docker
We are using Ddev for local development.

You will need the following:
* [Docker](https://www.docker.com/products/docker-desktop)
* [DDev](https://ddev.readthedocs.io/en/stable/#installation)

Add your public SSH key to Github and Pantheon account.

Once you have the project dependencies setup on your local environment, you should be able to setup your local environment with the sites.

1. Clone the latest version of the main branch from GitHub.
    - `git clone git@github.com:digitalpolygon/smartcontentpoc.git`
2. Move into the project folder - `cd smartcontentpoc`
    - Add your identity to github configuration by running the below commands
      - git config user.email "your-emailid@digitalpolygon.com"
      - git config user.name "Your Name"
3. Run composer install to download all project dependencies.
  - `composer install`
4. Obtain and configure Pantheon.io machine token
Get your Pantheon machine token: a. Log in to your Pantheon Dashboard and Generate a Machine Token for DDEV to use. b. Add the API token to the web_environment section in your global DDEV configuration at ~/.ddev/global_config.yaml

```sh
  web_environment:
  - TERMINUS_MACHINE_TOKEN=abcdeyourtoken
  ```
5. Run ```ddev config``` and follow onscreen instructions and keep press enter, It will auto select everything.
6. Run ```ddev start```
   - This will setup the site in local and can be accessed at https://smartcontentpoc.ddev.site
   - Click on this link, and finish the new site setup for first time.
7. Sync your local db and files from Pantheon dev environment
   - Run ```ddev pull pantheon``` This command will download the Pantheon database and files and bring them into the local DDEV environment. You should now be able to access the project locally.
   ```sh
    ddev pull pantheon
   ```