# Python configuration management #

When building applications with python, you will often have to deal with where to place configuration.

Especially, if you have secret values like Database username/password strings, API keys, AWS Credentials, etc it is very important to manage the placement of these values on open VCS (Version Control Systems) such as Github, Bitbucket. In fact, in some cases, due to careless configuration management, web applications and secrets are often exposed.

The 4 main methods for seperating config from code include;

- Using built-in data structure
- Using external configuration file
- Using environment variables
- Using dynamic loading

## Store config in the environment ##

An app’s config is everything that is likely to vary between deploys (staging, production, developer environments, etc). This includes:

- Resource handles to the database, Memcached, and other backing services
- Credentials to external services such as Amazon S3 or Twitter
- Per-deploy values such as the canonical hostname for the deploy
- Apps sometimes store config as constants in the code. This is a violation of twelve-factor, which requires strict separation of config from code. Config varies substantially across deploys, code does not.

A litmus test for whether an app has all config correctly factored out of the code is whether the codebase could be made open source at any moment, without compromising any credentials.

**The twelve-factor app** stores config in environment variables (often shortened to env vars or env). Env vars are easy to change between deploys without changing any code; unlike config files, there is little chance of them being checked into the code repo accidentally; and unlike custom config files, or other config mechanisms.

<https://12factor.net>
