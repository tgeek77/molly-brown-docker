# Introduction

This is a container for a Project Gemini server (aka capsule) using the [molly-brown](https://tildegit.org/solderpunk/molly-brown) server software. All credit for the actual service goes to [solderpunk](https://tildegit.org/solderpunk).

Gemini capsules work differently than web servers. You can create a web servers and point it to localhost and then add a hostname and security secondly. When working with Gemini, know the FQDN before you start the service.

## Requirements
You're going to need to follow the following 2 steps in order to get your new Gemini capsule

# Preparation Steps
1. Configure the molly.conf with the hostname of the new Gemini Capsule.
2. Create TLS keys for the Gemini capsule. 

## molly.conf

Edit `molly-brown/gemini_build/molly.conf` with the onion service hostname that will be used. The default hostname is "localhost".

## Certificates:
Create the certificates for the Gemini capsules.  Replace example.com with your FQDN.
```
openssl req -x509 -newkey rsa:4096 -sha256 -days 3650 -nodes \
  -keyout key.pem -out cert.pem -subj "/CN=example.com"
```
If you already have certificates from Let's Encrypt or another source, use those instead.
