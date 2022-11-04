---
uid: "contribution/rc-radio-reciver-to-vvvv"
uid-meta: "contribution/rc-radio-reciver-to-vvvv-meta"
uid-files: "contribution/rc-radio-reciver-to-vvvv-files"
title: "RC Radio reciver to VVVV"
image: "futaba01.jpg"
contribution: "true"
---

I was looking a way to implement a rc radio ( like futaba ones ) into VVVV by using the training port, but that kills the "wireless" of the system, the easy way of doing it is reading each channel PWM of the standar RC reciver by using an arduino, that is a Little bit complex, but I found a quick arduino sketch that solves it using interrupt, so the only electronics involve its 10 jumper wires, positive, negative, and 8 for each chanel.

Advantages over a joystick, resolution. PWM values have 2048 steps of resolution!
disadvange of the current system, its slow because i am sending ascci string, maybe using binary can improve it...

Arduino Code its inside the patch
Steer patch is from cote