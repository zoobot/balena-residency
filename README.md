# Hi-Dolly
**Exploratorium Mini Science Lab 471**

![Hi-Dolly](https://raw.githubusercontent.com/zoobot/hidolly/main/logo.png)

## Status

#status 
I've decided to make a mini Exploratorium science lab for the street because those little libraries and art galleries are so cute. With a mini science lab, there can be a lot of neighborhood magnet and rocks sharing, which is great, plus small electronic science and robotic experiments. First round mini lab "exhibit" will be voice to text to image generator on the mini wall with pi TFT hooked up to pi. Next I'd like to have a mini iron sand zen garden with magnet "scholar stones" and a few hall switches to play with. 

### What I have working so far: 

[x] twilio sms /web speech to text -> node server to sqlite on pi zero fleet. (could this be a balena block?)
[x] motion sensor trigger using nodejs's onoff GPIO library (awesome and easy!)
[x] SQGAN-CLIP dockerized and generating images on the NUC
[x] a box for the mini lab

### Todo:

[-] Fix the fastapi server on the SQGAN docker(had issues with volumes in 2.1 docker so paths are wonky)
[-] dig a post hole and mount the lab outside
[-] gather documentation from notes, git wiki, turn into blog post
[-] add a microphone
[-] setup new 1.5" TFTs

### Nice to haves:

[-] solar panel on the mini roof for power, otherwise someone's going to be charging batteries constantly.

## Highlights

- **Chrome Speech to Text Web Api**: talk at your internet browser!
- **Twilio Node Api**: SMS to nodejs
- **Motion Sensor Magic** Wave hand in the air and stuff happens, magically
- **SQGAN-CLIP Art**: Generated Images

## Setup and configuration

1. Create a fleet of zeros. Nice to have one as primary and one as backup sms server
2. Create a fleet of GPUs ideally
4. clone the code
```git clone git@github.com:zoobot/twilio-block.git```
```git clone git@github.com:zoobot/vqgan-clip-docker.git```
5. push code to the fleets
```balena push username\fleetname```
OR local dev
```balena push ipaddress```

### Deploying

[![Deploy with balena](https://balena.io/deploy.svg)](https://dashboard.balena-cloud.com/deploy?repoUrl=https://github.com/zoobot/hidolly)

Or add the following service to your `docker-compose.yml`:

## Documentation

Head over to our [docs](https://github.com/zoobot/hidolly/wiki) for detailed installation and usage instructions, customization options and more!

## Motivation

I, like everyone, enjoy all things cute. I'd been tasked with finding someone to build a mini library for my kids school for earth day. I asked my friend Mariel's husband to build the library and Mariel promptly sent me down the rabbit hole of mini galleries and mini library designs. I'd already been thoroughly engrossed in researching image generation and speech to text tools for the balena residency and so a mind mashup occurred. Hazzah!


## Getting Help

If you're having any problem, please [raise an issue](https://github.com/balenablocks/template/issues/new) on GitHub and we will be happy to help.

## Contributing
