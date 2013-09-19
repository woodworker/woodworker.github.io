---
layout: post
title: "NodeCopter + NoFlo = FlowCopter"
date: 2013-09-18 14:01
comments: true
categories: noflo 
---

I had an awesome friday the 13th at the NodeCopter Hackathon. The event was the 1st
Birthday for NodeCopter.

On the After Party event of the Reject.js me and [Henri Bergius](https://github.com/bergie) played with the idea
to use [noflo](http://noflojs.org/), the __awesome__ Flow Based Programming environment and
a Gamepad to play arround with 3 cool technologies at once (noflow, gamepad api and mother f***ing DRONES!!!).

So the project idea was born: [flowcopter](https://github.com/bergie/flowcopter)

Thanks to the help of [Robin Mehner](https://github.com/rmehner), one of the organiser, who brought his XBox Gamepad, we where able
play around with the [Browser Gamepad API](http://www.html5rocks.com/en/tutorials/doodles/gamepad/)
and i wrote a very small component for noflo to read out the Gamepad status from the Browser.

It turned out that the hardest part in that mountain of new technology was installing grunt and
some other npm packages in a Vagrant VM.
After half an hour of fiddling around i recognized that the `/vagrant` folder does not support symlinks *facepalm*.

So i learned just a few steps are needed for first tests with noflo.

* checkout noflo
* `npm install`
* `grunt build`

After this steps your are done for the first tests.

Then most of the time [@bergie](https://github.com/bergie) was developing a websockets component for noflo so that
we can talk from the browser who has the gamepad api to the nodejs instance which can controll the drone.

I just wrote the Gamepad API reading component and after that i learned how to write noflo graphs in the FBP DSL
invented back in the 70s. And it turned out that the only thing that was not there in the noflo environment was a
component that could translate a value from the gamepad status object to a command to steer the drone.

And the rest was just creating the graph. New command where just connecting buttons output ports to the
input ports of the drone controlling component.

So all in all. It was amazing day. Drones, flow based programming, a lot of cool people and everyone did
a cool project with their drones.

For example:

* object/color following
* tag recognition
* crash prevention aka. do not fly into people
* multi drone control
* complete new AR.Drone firmware written in go
