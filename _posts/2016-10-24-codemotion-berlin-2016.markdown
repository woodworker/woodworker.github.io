---
layout: post
title: "Codemotion Berlin 2016 - Day 1"
date: 2016-10-24 22:12
comments: true
categories: conferences
---

## Araival
I got my Namebadge pretty fast, but they did not have any lanyards left, as if they did not know how many people would be there. I should get one tomorrow or just use of of the 40+ i have hanging arround hat home.

## Food / Drinks
The Lunch was meh - just a Sandwich. I was at anytime during the day fully Matedrated thanks to free Flora Mate, there was also free cola, water and tee. Coffeetime was also Chocolate Cake time - yummy.

## The Keynote ★★★☆☆
The Keynote was by Fred George on how to solve complex problems not just by using microservices but also all the other stuff like devops, eventbus, agile agile(as he called it). Wasn't really a fan of this talk but he had some nice points on how every microservice should have its own persitance, if needed. And every persitance is derived from the global eventbus (Kafka).

## The Talks

### "Code Reviews: Techniques and Tips" by Rabea Gransberger ★★★★☆
I really liked her Talk about core reviews. As i was involved in the Code Review workflow creation at Researchgate this topic was also close to my daily work and got me also a big "How could i have forgot about this" Point to my todo list. And its a bit ashaming but i often forget about the social aspects of these workflows. For me a code review is about code, but as people could also see this as critisim about thier person. So i learned, and also need to incooperate this into my workflow for code reviews, to not only highlight bad stuff but also appriciate gode code and also highlight personal growth of other developers.
Also a big point was code review finds so mouch more errors then just having Tests and/or Q&A.
The tool side of this talks was a bit underrepresentated for my taste as it was "advertised" in the intro of her talk as there would be an overview of different review tools and then there was only "There are Github PR" and "We write issues for Reviews". But still a great talk and i leanred something.

### "Pure functional programming in Excel" by Felienne Hermans ★★★★☆
Yes, a talk about Excel. And yes i liked it. I leanred about Array functions in Excel and about Named Datasets and how they work. So much more cool stuff. Also that there are actual testing tool and code smells detectors for Excel spreadsheets.

### "HTTP/2 and Asynchronous APIs" by Davey Shafik ★★★☆☆
HTTP/2, or h2 as i learned today, is a cool tool even for writing APIs and in the way it was presented, maybe intentional, APIs that fully use the features of h2, like server push and multiplexing, will make the use of GraphQL obsolete.
Because Why using GraphQL to fetch everything in one call when your REST api can also push each an every api call allready to you that you would need to get an overall view of something (Example was: a GET for a news article also pushes the author entity, the comment list, each and every comment and every author enity of the comments)

### "TRANSISTOR ZERO: Reconstructing the brain of a computer" by Denis Defreyne ★★★★☆
A nice talk about how computer work deep deep down below this layer of nice C APIs that we are used to, even below this thing we call assembler code. Registers, what are they made of. How does and ALU work. Waht is and AND-Gate and how we can build one with just 2 transitors.

### "Hyperledger: towards enterprise grade Blockchain applications" by Louis De Bruin ★★★☆☆
You need to have a talk about the Blockchain or you just not a cool conference. Nice talk about Hyperledger a "Build your own Blockchain" Toolkit. Lousi shows some nice examples from the Netherland where they do a Proof of Concept for a eBike registration based on Hyperledger, whith involvment of the goverment, insurances, the police and cities. I think i will try to create small test blockchain, maybe for c-base. Because every hackerspaces needs its own blockchain.

### "The Rust community" by Florian Gilcher ★★★★☆
Not a talka bout the Language Rust, but about the community and all the people that help make the Rust community, what i hears from the interwebs, other people and also this speaker, a very awesome community. If just a third of what i leanred about ther rust community today is true, i would say the best developer community worldwide.

### "Knowledge is Power: Getting out of trouble by understanding Git" by Steve Smith ★★★★☆
Git is not a Version Controll System, its just a directed acyclic graph that implements a content addressable file system or something like that. And now you know why you hate Git so much. Steve hade a pretty nice talk about how git reflog is helping you everytime you fuck somehting up in git. Maybe i try something of that the next time i fuck git up before i would do a rm -Rf ./; git clone $url.

## Overall
I had a pretty good first day at Codemotion Berlin 2016, talks where all really good but i missed a "WOW" Talk, but thats not bad considering there was not a single bad talk i attended, not even a meh one. That been said, i completly left out one Timeslot.

