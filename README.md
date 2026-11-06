# fizz_dr_scripts
Ruby scripts for Lich5 for the game known as DragonRealms

This is the `scripts/custom` folder of a Lich5 DragonRealms install, for Fizzlestiks. Run any of them as `;name`.

## Stashing at home

Fizzlestiks's house is reached with `;go2 14665` then `MOVE ARCH`. Both scripts go there on their own (or start right away if you're already inside) and leave you in the house when they're done.

| Script | What it does |
|---|---|
| `stash.lic` | Puts things away in the house so your containers have room. `;stash crafting` (forging, shaping and enchanting gear: the yaml's `forging_tools`, `shaping_tools` and `enchanting_tools` plus crafting books, logbooks, oil, flux and the mana fount), `;stash forging`, `;stash shaping`, `;stash enchanting`, `;stash all` (crafting gear plus your extras), `;stash add <item>` (taps it to check the name, then adds it to your extras), `;stash remove <item>`, `;stash list`. Items go under the bed, then on the wall, in the wall, on the bookcase, on the table, skipping any spot that's full. |
| `unstash.lic` | Gets back everything `stash` put away, and only that, checking each item's full name so look-alikes stored at home stay put. Each thing goes back in the container it came from. |

Both keep their data in Lich's `data/DR/<character>/` folder: `stash.yaml` is what's stashed right now and where, `stash-extras.yaml` is your extras list.

## Other scripts

| Script | What it does |
|---|---|
| `sell-gems.lic` | Walks to the nearest gem shop, sells every loose gem from your rucksack and scavenger's belt (or containers you name), and walks back. |
| `smash-shells-heal.lic` | Fork of `smash-shells` that goes to a healer and waits for a heal when you're hurt, then goes back to smashing shells. |
| `raffle-watch.lic` | Plays the festival raffle and reports to the Familiar window. Posts each winner as their name goes up on the result board. If it's you, it beeps and puts your ticket on the counter to claim the prize; if you lose, it puts the ticket in the bucket; when picks reopen, it gets a new ticket. Runs until killed; `;raffle-watch once` stops after one drawing. |
| `announce_monitor.lic` | Posts the Hollow Eve festival's raffle, Limited Treasures and creature capture announcements to a Discord webhook so they reach your phone, with a reminder of how to join (`;go2 raffle`, `;go2 10205` for the Limited Treasures lounge, `;capture-critter hollow_eve`), skipping chatter in the raffle room and the shop. Autostart it with `;autostart add announce_monitor`. `;announce_monitor setup` sets the webhook and which announcements to send; `;announce_monitor test` sends a test message. The webhook lives in Lich's `data/announce_monitor.yaml`, not in this repo. |
| `LT.lic` | Buys at Gortik's Limited Treasures the moment the sale opens (Lich version of Lycette's Genie `limited` scripts). Start it in the lounge: when the deathfiber curtain powers down it goes through the curtained door, buys what you name in that order (`;LT mask greatcoat bookbag`) or whatever is on a stand (`;LT third`), then echoes what's on each of the three silversteel stands. `;LT` alone just looks; `;LT now ...` is only for when the sale has already opened. It never buys the rock. |
| `2hourquit.lic` | Exits the game two hours after it starts, or after the minutes you give it (`;2hourquit 90`). |
