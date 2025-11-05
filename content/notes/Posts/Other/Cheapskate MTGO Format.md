---
title: Cheapskate MTGO Format
enableToc: 
date: 2025-05-12
tags:
  - posts
---
# Cheapskate Format
Aka PD with randomized set based rotation, using [Goatbots](https://www.goatbots.com/) pricing. All legal cards cost less than two cents.

To be clear, this is expected to be played by a handful of players at most, and mostly created for the sake of seeing how it goes and maybe having a bit of fun trying it with a few other people.

Current legal card list can be found [here](https://moxfield.com/binders/zAEl_n_QSkq9sMVK3CJ9PA). It allows for Scryfall searches, however, you cannot sort, only filter, which is a bit unfortunate but mostly workable.
## Card legality and rotation
All cards at or below 2 cents on Goatbots have a chance to be legal.
To determine legal cards:
1. Select 60% of 'regular'* magic sets at random, most recent set guaranteed to be legal.
2. Combine all cards from the selected set into a single list, and select 70% of them at random to be eligible.
3. Select 42% of all cards from non regular sets to be eligible.
4. Add whitelisted cards (land cycles).
5. Cut out all cards above 2 cents on Goatbots.
After following these steps, you have generated the cheapskate card pool.

Notes:
- 'Regular' set means it was printed into standard/modern at some point and is not just a reprint or commander set or something. Those sets tend to have a very small number of unique cards on mtgo, so including them in the set calculation screws with the numbers a lot (they represent a tiny fraction of the total legal cards).
- With these numbers, any given card <=2 cent card has a 42-65% (upper number is an estimate) chance to be legal in a given season, and 17-42% chance to be legal 2 seasons in a row. These numbers can be adjusted / we can try different ones for a few seasons to see what works. This was selected to 
- There are roughly 22,500 <=2 cent cards on Goatbots, 27,000 cards on mtgo, and 14,500 legal in PD. There are 10,158 cards legal in Cheapskate currently.
- The objective of the set based rotation and these particular numbers is to have a volatile rotation where sets being legal or illegal textures the format, while leaving some cards out of selected sets ensures that the same set being legal in multiple seasons does not feel like an exact repeat. The 60% number could go down or 70% could go up a little bit, and this idea would likely be retained or strengthened at the cost of a smaller card pool.

## Ban List
The format uses the Vintage ban list in addition to the following cards:

```
Channel
Mental Misstep
Sol Ring
High Tide
Balance
Flash
Library of Alexandria
```

Banned cards are persistent across rotations and not updated during a season. The ban list is only be updated during rotation.

## Land Whitelist
The following land cycles are guaranteed to be legal if they are <=2 cents:
- Basic lands
- Basic snow lands
- Checklands
- Painlands
- Ravnica Bouncelands
- Bridges
- Future Sight lands
- Filterlands (both Odyssey and Lorwyn)
- Tango lands
- Snarl / Reveal lands
- Snow Duals
- 2c cycling lands
- Mono color cycling lands (cycling for 1 pip)

Lands to consider adding:
- Vivid lands
- Landscapes
- Arcum's Astrolabe

## Changing the ban list & rules
For a given card to be banned or unbanned, the change is made by a majority vote among players. This will take place between seasons. Any player who has played during the previous season can add cards (limit of 2) to the ban vote and vote on all proposed format changes. Changes to these format rules are also decided by majority vote.

## Current Rotation's Sets:
```
1E
5DN
7E
9ED
AFR
AKH
ALA
ALL
ARB
AVR
BFZ
BLB
BOK
CHK
CON
CSP
DIS
DKA
DTK
EMN
FRF
FUT
GPT
GRN
GTC
HOU
ICE
IKO
ISD
JUD
KHM
KTK
LCI
LGN
LRW
M12
M13
M15
M20
M21
MH1
MH2
MH3
MID
MKM
MOM
NE
OGW
ONE
ONS
ORI
OTJ
PR
RAV
RTR
SHM
SOI
SOK
SOM
ST
TDM
TE
THS
TSP
UD
UL
VOW
WL
WOE
WWK
XLN
ZEN
```


---
## Extra notes:
Legal cards list is calculated with a python script. I can throw the files up on discord or smth.

So some quirks I am aware of or at least believe to be the case given the methodology:
- Cards which appear in multiple regular sets are more likely to be legal.
- The exact number of cards which are legal each season even with the same pool of sets is slightly random, for example I ran it twice and once i got 12242 legal cards and another time I got 11973. This due to some sets containing more cards than others.

To see other sample rotations to know how it may vary over time, [here](https://moxfield.com/binders/AYJb3TsxeUmrI2YmOQCxew/) and [here]() are additional ones I generated (to be clear this was done after the currently in use one was generated, they were not hand picked from).

test change