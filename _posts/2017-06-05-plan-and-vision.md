---
layout: post
title: "GameDev - should I?"
date: 2017-06-05
excerpt: "I am passionate about games, I am passionate about game mechanics and I want to be a GameDev hobbist"
tags: [gameDev, unreal enginge]
comments: true
---

I've been watching a lot of GDC for the past few months, by a lot I mean a few videos a week, and the reason behind
it is that I want to know what other GameDevs have to say about the industry.

The most recent videos I've watch scared me, they promise long-term failure for only potential success. In a way I 
see it as trying to do art, people may not like what you do now but in 7 years (as in a particular scenario) they will.

But why do I want to do this to myself?

The main reason is that I am a gamer at heart, I've been playing games since I was 4 years old and being a gamer in 1999 
was not something that common for a youngling such as myself.

I've read a lot of LitRPG series and I've been impressed with the ideas they lay there and the universe they create within
these books. An example is "The Land" by Aleron Kong that describes an amazingly detailed world and it's mechanics to
the reader.

## Games

I played a few games, my favourite genere was RPG (or MMORPG) and in all these games I want to be a crafter, a blacksmith,
a tailor or simply play as a hunter that skins animals and sells those skins.

I always had an ideal and focused image and almost always picked a crafting profession.

The crafting in all games was... boring! I loved the idea of being a master smith and warrior or a mage and enchanter but 
the system itself was all GRIND nothing exciting, nothing to make you feel special about your own profession about the 
hours you spent clicking a button that is usually labeled "Craft"!

A few games offered you achievements (looking at you WoW) but all of them followed the same pattern:
- you are role playing as a crafter, a crafter is a creator and artist but you can only create a prepared items (nothing original)
- the preset of items were in a list with a name-requirements
- you click the button watch a repetitive animation of your character smashing an anvil (at least they could make that random)

So what I want to start off with is focusing on crafting games, on games where you can create, games that use normal
physics, geometry and material properties to dictate the strength of your creation or where enchanting is simillar to 
writing a book (or code) a game that allows the smart or creative users to actually CRAFT!

So my projects related to this hobby will be looking towards that

<img src="https://s-media-cache-ak0.pinimg.com/originals/de/07/4d/de074df27d1f9eeaf13f74430a708f2d.jpg">

What if you could draw this and then select the materials you want to use for each component?

What if you could then process it, sharpen it and have it as an in-game weapon?

### But, how do you want to do that?

I will start off with some simple exercises in level design and procedural generation, yes they are not related but I think
there is a lot to learn from fractals or grid procedural generation (eventually maybe genetic algorithm).

I could use this to generate some items and help create the system that will assign properties to these items.
(damage, weight, durability)

I know that giving a player this kind of freedom will result in knights going around with dick swords and female 
knights will end up wearing even less that what they do today, that's why I want to add a way to generate the properties
in accordance to the shape.

So the mighty Dick sword will never have an appropriate ballance and the damage will be affected because of this and if
our little elfa thinks to wear the Steel Bra of Submission in battle she will be surprised with how useless it will be, 
as it does not protect vital spots and it has very little space for enchantments (yes enchantments would take in consideration
the actual size of the item and the size affects the speed and strength requirements).

I want to use generic elements that are found in every day MMORPG and also not tie the system to these elements, this 
should allow anyone incorporating the crafter in their games to balance it how they want and map it to their own system.

### Ok do you expect people to use your project?

No, I expect people to take my idea and make it better. It is not original as it's stolen. Yes I stole the idea from a 
place most of us forgot it exists, reality! 

I want to set some bases to material/item manipulation in games.
I once used a WoW item creator that asked me a few simple questions:
What are the stats you want on the item? (the ones you read and game uses to calculate your damage)
How do you want the item to look?

And I answer like this:
I want to dictate the item's look by usage of different materials and dyes and based on my skill in the 
crafting profession and the item's geometry it should have realistic stats.

It should be easier to create this system than to randomly generate a full planet's ecosystem with realistic constraints!
(No man's sky!)

For the next post I will start with some procedural level generation or some fractal based shape evolution (use fractals to evolve a cube into a new shape)
This will help me understand the geometry better and within a few iteration I may devise something to procedurally 
generate small items (weapons, i mean a spear is a sharp stick, how hard can it be?)
