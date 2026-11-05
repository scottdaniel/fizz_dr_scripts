# fizz_dr_scripts
Ruby scripts for Lich5 for the game known as DragonRealms

This is the `scripts/custom` folder of a Lich5 DragonRealms install, for Fizzlestiks. Run any of them as `;name`.

## Stashing at home

Fizzlestiks's house is reached with `;go2 14665` then `MOVE ARCH`. Both scripts go there on their own (or start right away if you're already inside) and leave you in the house when they're done.

| Script | What it does |
|---|---|
| `stash.lic` | Puts things away in the house so your containers have room. `;stash crafting` (forging and shaping gear: the yaml's `forging_tools` and `shaping_tools` plus crafting books, logbooks, oil and flux), `;stash forging`, `;stash shaping`, `;stash all` (crafting gear plus your extras), `;stash add <item>` (taps it to check the name, then adds it to your extras), `;stash remove <item>`, `;stash list`. Items go under the bed, then on the wall, in the wall, on the bookcase, on the table, skipping any spot that's full. |
| `unstash.lic` | Gets back everything `stash` put away, and only that, checking each item's full name so look-alikes stored at home stay put. Each thing goes back in the container it came from. |

Both keep their data in Lich's `data/DR/<character>/` folder: `stash.yaml` is what's stashed right now and where, `stash-extras.yaml` is your extras list.

## Other scripts

| Script | What it does |
|---|---|
| `sell-gems.lic` | Walks to the nearest gem shop, sells every loose gem from your rucksack and scavenger's belt (or containers you name), and walks back. |
| `smash-shells-heal.lic` | Fork of `smash-shells` that goes to a healer and waits for a heal when you're hurt, then goes back to smashing shells. |
| `raffle-watch.lic` | Plays the festival raffle and reports to the Familiar window. Posts each winner as their name goes up on the result board. If it's you, it beeps and puts your ticket on the counter to claim the prize; if you lose, it puts the ticket in the bucket; when picks reopen, it gets a new ticket. Runs until killed; `;raffle-watch once` stops after one drawing. |
| `2hourquit.lic` | Exits the game two hours after it starts, or after the minutes you give it (`;2hourquit 90`). |
