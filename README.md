# fizz_dr_scripts
Ruby scripts for Lich5 for the game known as DragonRealms

This is the `scripts/custom` folder of a Lich5 DragonRealms install, for Fizzlestiks. Run any of them as `;name`.

## Stashing in the vault

Both scripts use your vault at your hometown's Carousel (Crossing is `;go2 8285`). They walk there, go through the first free booth (blackwood, ironwood, then rosewood; the platinum arch is restricted for Fizzlestiks, and if all three booths are busy they wait), `PULL LEVER`, `GO DOOR` and `OPEN VAULT`. When they're done, or if anything goes wrong on the way, they close the vault and leave you in the Carousel. If rent is due they stop at the arch: pay at the Carousel desk (`GO DESK`, 5,000 Kronars for 30 days).

| Script | What it does |
|---|---|
| `stash.lic` | Puts things in your vault so your containers have room. `;stash crafting` (forging, shaping, enchanting, outfitting and alchemy gear: the yaml's `forging_tools`, `shaping_tools`, `enchanting_tools`, `outfitting_tools` and `alchemy_tools` plus crafting books, logbooks, oil, flux and the mana fount; and the materials each one uses, found with LOOK IN across your `storage_containers`: ingots, nuggets, metal bars and ore; lumber, lumber deeds, bone stacks, stone deeds and loose stone; sigil-scrolls and beads; leather, cloth, yarn, thread and dyes), `;stash forging`, `;stash shaping`, `;stash enchanting`, `;stash outfitting`, `;stash alchemy`, `;stash extras` (just your extras), `;stash all` (crafting gear and materials plus your extras), `;stash add <item>` (taps it to check the name, then adds it to your extras), `;stash remove <item>`, `;stash list`. If the vault fills up, the rest stays where it is. |
| `unstash.lic` | Gets back everything `stash` put away, and only that, checking each item's full name so other things in your vault stay put. Each thing goes back in the container it came from. `;unstash forging`, `;unstash shaping`, `;unstash enchanting`, `;unstash outfitting`, `;unstash alchemy`, `;unstash crafting` (all five) or `;unstash extras` gets back just that part, since `stash` writes down what each thing is for. |

Both keep their data in Lich's `data/DR/<character>/` folder: `stash.yaml` is what's in the vault right now and where it came from, `stash-extras.yaml` is your extras list.

## Other scripts

| Script | What it does |
|---|---|
| `sell-gems.lic` | Walks to the nearest gem shop, sells every loose gem from your rucksack and scavenger's belt (or containers you name), and walks back. |
| `empty-sacks.lic` | Empties the random-material sacks in your tote: takes each one out, opens it, moves everything into your tote with `;transfer-items` (your rucksack once the tote is full), and drops the empty sack for the janitor. Start with empty hands. If both are full it stops with the sack in your hand. |
| `smash-shells-heal.lic` | Fork of `smash-shells` that goes to a healer and waits for a heal when you're hurt, then goes back to smashing shells. |
| `raffle-watch.lic` | Plays the festival raffle and reports to the Familiar window. Posts each winner as their name goes up on the result board. If it's you, it beeps and puts your ticket on the counter to claim the prize; if you lose, it puts the ticket in the bucket; when picks reopen, it gets a new ticket. Runs until killed; `;raffle-watch once` stops after one drawing. |
| `announce_monitor.lic` | Posts the Hollow Eve festival's raffle, Limited Treasures and creature capture announcements to a Discord webhook so they reach your phone, with a reminder of how to join (`;go2 raffle`, `;go2 10205` for the Limited Treasures lounge, `;capture-critter hollow_eve`), skipping chatter in the raffle room and the shop. Autostart it with `;autostart add announce_monitor`. `;announce_monitor setup` sets the webhook and which announcements to send; `;announce_monitor test` sends a test message. The webhook lives in Lich's `data/announce_monitor.yaml`, not in this repo. |
| `LT.lic` | Buys at Gortik's Limited Treasures the moment the sale opens (Lich version of Lycette's Genie `limited` scripts). Start it in the lounge: when the deathfiber curtain powers down it goes through the curtained door, buys what you name in that order (`;LT mask greatcoat bookbag`) or whatever is on a stand (`;LT third`; if it can't find the stand it tries `look on display`, then buys what the clerk is handing other people), then echoes what's on each of the three silversteel stands. `;LT` alone just looks; `;LT now ...` is only for when the sale has already opened. It never buys the rock. |
| `2hourquit.lic` | Exits the game two hours after it starts, or after the minutes you give it (`;2hourquit 90`). |
