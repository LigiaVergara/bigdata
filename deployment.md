# Deployment with CapRover

## Apply for GitHub Student Developer Pack

Apply for the free GitHub Student Developer Pack at https://education.github.com/pack

## Register a Domain Name

Use either https://www.name.com/ or https://www.namecheap.com/ for registering a domain name (you might want to use the GitHub Student Developer Pack discount)

## Register at a Cloud Provider and create a Virtual Private Server (VPS)

Register at DigitalOcean https://www.digitalocean.com/ via your GitHub Student Developer Pack to get $100 in platform credit for new users. Alternatively you can use also any other cloud provider that is offering a VPS, like Hetzner https://www.hetzner.com/cloud 

## Add a Wild Card entry at your Domain Name register

Add a wildcard DNS entry for your VPS at your Domain Name register (e.g. name.com or namecheap.com)
- Go to the domain name panel of your Domain Name register and add a A Record:
1. Host should be a wild card for a subdomain, e.g. `*.dev`
2. Value should be the IP Address of your VPS

## Install CapRover on your VPS

Instructions:
- https://www.youtube.com/watch?v=VPHEXPfsvyQ 
- https://caprover.com/docs/get-started.html 

On DigitalOcean you can select a Droplet with CapRover preinstalled. 
Alternativly you have to install on the server a) Docker (also available as a Droplet or manual installation) and b) CapRover.

## Install CapRover CLI (Command Line Interface) on your laptop

- https://caprover.com/docs/get-started.html#step-3-install-caprover-cli 


## Create a CapRover captain-definition file

CapRover has different ways to define how to deploy an application through a Captain Definition File `captain-definition`, see https://caprover.com/docs/captain-definition-file.html for more details.

We will use a Dockerfile for the deployment: https://caprover.com/docs/captain-definition-file.html#use-dockerfile-in-captain-definition 

- Go into your Streamlit application folder from the last exercise
- Create a new file with the name `captain-definition`

put in the `captain-definition` file the following content:
```json
 {
  "schemaVersion": 2,
  "dockerfilePath": "./Dockerfile"
 }
```

## On the Server, create an App

Go to your the CapRover server web dashboard and create an app

## On the Laptop, your App

In the folder of your Streamlit app, execute in the Terminal:

```bash
caprover deploy
```

Check if you can reach your Streamlit app on the web

## Add additional URL to your Streamlit app

We want to reach your Streamlit website via the subdomain `gapminder` so that if you would have the domain name `example.com`, the URL of your app would be `gapminder.example.com`

For that, you have to do two things:
1. Add at your Domain register (e.g. namecheap.com) a new A record with the host `gapminder` and the value the IP address of your VPS.
2. In the CapRover Dashboard, go to your app, enter next to "Connect New Domain" your URL and click "Connect New Domain". 

Test if the new URL works

## Enable HTTPS

On the server, enable HTTPS for your main CapRover Dashboard and your Streamlit app. Check "Force HTTPS by redirecting all HTTP traffic to HTTPS" 

Test that the redirect works.

## Deliverable

Copy the URL of your deployed Streamlit App to Moodle

