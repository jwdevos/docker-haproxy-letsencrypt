# docker-haproxy-letsencrypt

This repo contains a bash script named "installcert" that can be used to request and install new certificates from Let's Encrypt. This script is good for use in combination with Docker, HAProxy and Let's Encrypt, specifically the Certbot implementation. In summary, the script runs a temporary Docker container for Certbot, requesting new certificates for each domain in the array of domain names. The script displays output on the screen, but also logs it to a file. At the top of the script there are some variables:  
* LOG_PATH: sets the directory where the script places its logs  
* LE_DIR: sets the local directory containing the bind mount for the Certbot Docker container  
* LE_PORT: sets the local port the Certbot container will listen on  
* LE_EMAIL: sets the e-mail address Let's Encrypt will send mail to  
* LE_NAME: sets the name the Certbot container will get  
* CERT_DIR: sets the name of the directory where certificates will be installed  
* CONTAINER_NAME: sets the name the HAProxy container has  
* DOMAINS: contains the list of domains to keep up to date certs for  
  
You can see example values in the installcert script in this repository. A basic HAProxy config file that will work with this setup is also included.  
