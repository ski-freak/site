---
title: Cheapskate MTGO Format
enableToc: 
date: 2025-05-12
tags:
  - posts
---
# Cheapskate Format
Aka PD with randomized set based rotation, using [Goatbots](https://www.goatbots.com/) pricing.

To be clear, this is expected to be played by a handful of players at most, and mostly created for the sake of seeing how it goes and maybe having a bit of fun trying it with a few other people.

Current legal card list can be found here: https://moxfield.com/binders/oE-TpllCHU6LtnLPpjk2-A/
Yes, it allows for Scryfall searches, however, you cannot sort, only filter, which is a bit unfortunate.
## Card legality and rotation
All cards at or below 2 cents on Goatbots have a chance to be legal.
To determine legal cards:
1. Select 60% of magic sets at random, most recent set guaranteed to be legal.
2. Select 70% of the cards from each selected set at random.
3. Cut out all cards above 2 cents on Goatbots.
- This is now the card pool.

Notes:
- With these numbers, any given card <=2 cent card has a 42% chance to be legal in a given season, and 17% chance to be legal 2 seasons in a row. These numbers can be adjusted / we can try different ones for a few seasons to see what works.
- There are roughly 22,500 <=2 cent cards on Goatbots, 27,000 cards on mtgo, and 14,500 legal in PD.

## The format uses the Vintage ban list in addition to the following cards:
Channel
Mental Misstep
Sol Ring
High Tide
Balance
Flash
Library of Alexandria

Banned cards are persistent across rotations and not updated during a season. The ban list is only be updated during rotation.

### Changing the ban list & rules
For a given card to be banned or unbanned, the change is made by a majority vote among players. This will take place between seasons. Any player who has played during the previous season can add cards (limit of 2) to the ban vote and vote on all proposed format changes. Changes to these format rules are also decided by majority vote.


---
### Extra notes:
Legal cards list is calculated with a python script (which I got chatgpt to make because im too bad at programming lol). I can throw the files up on discord or smth.

Files used:
- Goatbots pricing data downloaded from their site as a text file
- Goatbots also provides a card definitions text file which is used with the pricing data.
- A python script that checks those two and does the following stuff:
	1. Output a text file listing all cards which are <= 2 cents
	2. Determine legal and illegal sets and spits that out as a text file (60% of sets legal 40% illegal)
	3. For each set, select 70% of cards by name to be eligible and spit it out as a text file
	4. Compare the cheap cards and eligible cards text files, and any cards which are listed in both of those get put into the new text file legal-cards.txt
	- Sets containing only reprints are blacklisted in the script.

So some quirks I am aware of or at least believe to be the case given the methodology:
- Cards which appear in multiple sets are more likely to be legal.
- All sets appearing on goatbots cards are included in the calculation, idk if we want to exclude reprint sets and have them not influence the legality. Just have a list of blacklisted sets maybe.
- The calculation of legal cards is done before the determining of which cards are cheap, which may affect the percentage of legal cards from the expected 42% (this prediction derived from 60% * 70% = 42%).
- In practice about 52% of cards are legal instead of the expected 42%. I have no idea why this is, I'm probably just not understanding/missing some consequence of the methodology, I'd guess that is more likely than the script calculating things wrong. Maybe it's because of the cards appearing in multiple sets thing not being calculated into the simple probability multiplication I did for the prediction.
- The exact number of cards which are legal each season even with the same pool of sets is slightly random, for example I ran it twice and once i got 12242 legal cards and another time I got 11973. This due to some sets containing more cards than other but it is possible there are other causes as well.