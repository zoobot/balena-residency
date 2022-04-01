# Hi-Dolly
**Exploratorium Mini Science Lab 471**

![Hi-Dolly](https://raw.githubusercontent.com/zoobot/hidolly/main/logo.png)

## Status
 
I've decided to make a mini Exploratorium science lab for the street because those little libraries and art galleries are so cute. With a mini science lab, there can be a lot of neighborhood magnet and rocks sharing, which is great, plus small electronic science and robotic experiments. First round mini lab "exhibit" will be sms and web speech to text to image generator to pi TFT. Thanks to [@nucleardreamer](https://github.com/nucleardreamer) for all the great ideas and for working on this with me!

## Highlights

- **Chrome Speech to Text Web Api**: talk at your internet browser!
- **Twilio Node Api**: SMS to Nodejs to SQLite, save your texts for eternity on a pi
- **Motion Sensor Magic** Wave hand in the air and stuff happens, magically
- **SQGAN-CLIP Art**: Generated Images

### What I have working so far: 

1) [x] [twilio-block](https://github.com/zoobot/twilio-block) sms /web speech to text -> node server to sqlite on pi zero fleet. (Could this be a balena block?)
2) [x] SQGAN-CLIP dockerized and generating images on the NUC
3) [x] motion sensor trigger to turn on an off web microphone
4) [x] a box for the mini lab
5) [x] randomized display for images

### Todo:

1) [ ] Fix the fastapi server on the SQGAN docker(had issues with volumes in 2.1 docker so paths are wonky)
4) [ ] add a micro usb pi microphone
5) [ ] setup new 1.5" TFT instead of big 9" TFT
2) [ ] dig a post hole and mount the lab outside
6) [ ] Steel sheet roof for mini lab box
3) [ ] gather documentation from notes, git wiki, turn into blog post

### Nice to haves:

1) [ ] solar panel on the mini roof for power, otherwise someone's going to be charging batteries constantly.
2) [ ] GPU renderfarm type situation with the image generation so make it faster
3) [ ] MQQT block for intercommunication

## Setup and configuration

1. Create a fleet of zeros. Nice to have one as primary and one as backup sms server
2. Create a fleet of GPUs ideally ( I am trying on the NUC which is slow )
4. clone the code
```git clone git@github.com:zoobot/twilio-block.git```
```git clone git@github.com:zoobot/vqgan-clip-docker.git```
5. cd to each repo
6. push code to the fleets (Nuc for vqgan-clip-docker and pizero for twilio)
```balena push username\fleetname```
OR local dev
```balena push 644b374.local```
```balena push UUID.local```
```balena push internal-ip-address```
7. Setup Twilio account and get a phone number and setup balena public urls on the twiml and phone api messaging

### Deploying
 
Need to figure out multiarchitecture/multifleet deployment!
Currently just run balena push with the twilio-block and sqgan-clip-docker separtely. Both repos have separate docker-compose.yml.

## Documentation

Check the [wiki](https://github.com/zoobot/hidolly/wiki) for not quite organized yet docs.

## Motivation

I, like everyone, enjoy all things cute. I'd been tasked with finding someone to build a mini library for my kid's school's Oak grove for earth day. I asked my friend Mariel's husband to build school mini library so Mariel promptly sent me down the rabbit hole of mini gallery and library design perusal. I'd already been thoroughly engrossed in researching  SQGAN-CLIP image generation and speech to text tools for the balena residency and thankfully a mind mashup occurred. Hazzah! Exploratorium Mini Science LAb 471 is coming to fruition.


## Getting Help

If you're having any problem, please [raise an issue](https://github.com/balenablocks/template/issues/new) on GitHub and we will be happy to help.

## Contributing

Have at it!