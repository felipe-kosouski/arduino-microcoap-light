# Arduino CoAP Smart Lighting Application

This project is part of my Undergraduate Thesis of the Federal Technological University of Paraná (UTFPR - Brasil), from the Technology in Internet Systems course.
The objective of this project consists in develop and implement a solution for Smart Lighting utilizing concepts and technologies of Internet of Things, by making use of a physical circuit and a Web Service that talk to each other via Internet, making it possible that we retrieve the actual state of a lamp, as well as light it or turn ir off.

Este projeto faz parte do meu Trabalho de Conclusão de Curso da Universidade Federal Tecnológica do Paraná (UTFPR), do curso de Tecnologia em Sistemas para Internet.
O objetivo do projeto consiste em desenvolver e implementar uma solução para Smart Lighting utilizando tecnologias e conceitos da IoT, fazendo uso de um circuito físico e um Web Service que se comuniquem entre si por meio da rede e façam com que seja possível obter o estado atual de uma lâmpada, bem como acendê-la ou apagá-la remotamente.

## Requirements

- Arduino Mega 2560
- Shield Ethernet
- Relay Module (relé)
- Lamp and socket
- Gcc
- Arduino IDE

### Used for this project
- All tecnologies from Requirements
- MacOS High Sierra
- CoAP Protocol

#### Instalation
- Clone repository
- Open project in Arduino IDE
- Connect an Arduino board
- Map the pin to where the relay is
- Compile the code
- Flash to board
- Open serial monitor in IDE to retrieve IP Address

##### Running the project
- The API from https://github.com/felipe-kosouski/smart-light-coap-api must be configured to connect to the IP Address retrieved from the serial monitor

==========================================================================================================

The microcoap server project is forked from https://github.com/1248/microcoap

microcoap
=========

A tiny CoAP server for microcontrollers.
See http://tools.ietf.org/html/rfc7252

Endpoint handlers are defined in endpoints.c

 * Arduino demo (Mega + Ethernet shield, LED + 220R on pin 6, PUT "0" or "1" to /light)
 * POSIX (OS X/Linux) demo
 * GET/PUT/POST
 * No retries
 * Piggybacked ACK only


For linux/OSX

    make
    ./coap

For Arduino

    open microcoap.ino

To test, use libcoap

    ./coap-client -v 100 -m get coap://127.0.0.1/.well-known/core
    ./coap-client -v 100 -m get coap://127.0.0.1/light
    ./coap-client -e "1" -m put coap://127.0.0.1/light
    ./coap-client -e "0" -m put coap://127.0.0.1/light

Or use copper (Firefox plugin)

    coap://127.0.0.1

Arduino problem
===============

Arduino, by default, has a UDP transmit buffer of 24 bytes. This is too small
for some endpoints and will result in an error.

