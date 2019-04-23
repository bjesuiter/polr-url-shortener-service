# polr-url-shortener-service
A docker-compose setup for polr url shortnener

## Local 

You can run this docker-compose setup locally by using `npm run local`.   
This uses the slightly changed file `docker-compose.local.yml` to serve the polr and the db container.  
You can access the instance by using `http://localhost:8080/setup`.   
> Note that calling `http://localhost:8080` redirects to `http://localhost/setup`, 
> which does not work because the port is 8080. 
> The image mackmoe/polr_docker:latest does assume it's running on Port 80.

If you want another local port, change the `ports` directive in `docker-compose.local.yml` 
for the `polr` service to a port you like.

## Production
### Prerequisites

- A running instance of https://github.com/evertramos/docker-compose-letsencrypt-nginx-proxy-companion  
  with the network being 'webproxy'
- The domain which should be used to access your polr instance, for example `polr.yourdomain.com`. 
  This domain must point to the IP address of your server. 

### Usage

1. Clone this repo on the server you want to run the service 
2. Copy .env.sample to .env & replace all env values with the settings you need (see comments in .env file for help)
3. Run `npm start`
4. Optional: Look at the other npm scripts for other useful commands for status and service maintenance.

### First Time Setup 

1. Go to 'https://polr.yourdomain.com/setup'
2. Insert all db details you defined in `.env` file


## TODO

- Make polr container use mysql config vars 

- Make Polr container accept an env var for the service domain (does currently redirect to localhost)

## Docs 

- [Polr, Pronto with Docker](https://github.com/mackmoe/polr_pronto#polr-pronto---with-docker)
- [Polr Docs User Installation](https://docs.polrproject.org/en/latest/user-guide/installation/)
- [Polr Project Website](https://polrproject.org/)
- [Polr Demo](https://demo.polr.me/)
- [Possible alternative: Kutt.it](https://github.com/thedevs-network/kutt)