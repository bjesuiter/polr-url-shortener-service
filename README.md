# polr-url-shortener-service
A docker-compose setup for polr url shortnener

## Prerequisites

- A running instance of https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion  
  with the network being 'webproxy'
- The domain which should be used to access your polr instance, for example `polr.yourdomain.com`. 
  This domain must point to the IP address of your server. 

## Usage

1. Clone this repo on the server you want to run the service 
2. Copy .env.sample to .env & replace all env values with the settings you need (see comments in .env file for help)
3. Run `npm start`
4. Optional: Look at the other npm scripts for other useful commands for status and service maintenance.
