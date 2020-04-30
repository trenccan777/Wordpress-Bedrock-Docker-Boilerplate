# WordPress Bedrock Docker Setup

## Installation

- clone this repository into your PC
- `cd` into the root folder and edit `.env.bedrock` and `.env` or leave it as it is 
- download bedrock with composer:

```
composer create-project roots/bedrock
```

- copy `env.bedrock` file from rott folder to `bedrock` and rewrite to rename to `.env`. 

- from the root folder run:
```
docker-compose up -d
```
- WordPress is ready for installation on the localholst IP you have inserted in `.env` file.