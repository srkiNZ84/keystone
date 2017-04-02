# keystone

## Introduction
My attempt to make a secure and upgradable "base" image for use with all the things in clouds and otherwise.

## What does that actually mean?
So, latest stable Ubuntu base image with:
* auto-upgrades turned on
* SSH brute force protection (probably fail2ban)
* data integrity and filesystem monitoring (probably Tripwire)
* per process capability restrictions (AppArmor)
* ingress and egress firewall on by default
* SSH 2FA
* kernel hot-patch turned on
* SSH FP records
* System logging/auditing turned on
* potentially other things...

## How are you going to test this and keep it up to date?
That's a damned good question. Will probably go for an initial setup with some infrastructure tests to verify that
things are working the way they're supposed to be (sunny scenario) and eventually move on to actually running tests to
make sure we are detecting attempted break in's etc...

## What about Docker?
So, that raises a good question. Basically, the way you're meant to use Docker is that you're meant to use something
with a "minimized" attack surface (e.g. Alpine). However, very few places I've worked actually do this (most just use
Ubuntu). The Docker image won't run SSH or any other background processes, so most of the stuff is not applicable
anyway, with perhaps the auto-upgrades.
