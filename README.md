# Buy Dedicated Server: What $95/Month Actually Rents, Why the Cheapest Configs Are Sold Out, and How to Tell Bare Metal From "Dedicated Resources" (Full Plan Table)

A dedicated server costs anywhere from about $36 a month to $400+ for a current-generation 32-core machine, and the headline price is the least useful number on the page. Three things change what you actually pay: whether the box is physical hardware or a virtualised slice sold as "dedicated resources", whether that exact configuration is in stock, and whether the figure is a real monthly rate or a 12-month average with VAT folded in. Ava Hosting runs the physical kind out of Chișinău, Moldova, lists four configurations from $95.32/month, and its cheapest listing showed **0 available** when this was written.

What follows is the four plans with their current prices, the stock and delivery picture across the market, what prepaying really saves, and the checks worth doing before you enter a card number.

> **Quick pick.** If you want physical hardware with DDoS filtering and 24/7 staff for under $170/month, the value sits in Ava Hosting's 2x Xeon E5-2699 v3 at **$167.09/month** (36 cores, 72 threads) or the 2x E5-2620 v3 at **$134.57/month** for lighter workloads. The $95.32 Ryzen 5 4650G is the one most people will want first, and it's also the one showing no stock.
> 👉 See Ava Hosting's four dedicated server plans and live availability

## The four Ava Hosting dedicated servers, and who each one fits

All four are single-tenant physical machines on a 1 Gbps port with one IPv4 address, free DDoS protection and 24/7 support, billed monthly in USD. The specs below are what the store page shows, with RAM and disk listed as "from" values because they're configurable at order time.

| Plan | Cores / RAM / storage | Price | Best for | Order |
| --- | --- | --- | --- | --- |
| AMD Ryzen 5 4650G | 6C/12T · from 16GB DDR4 · from 256GB NVMe · up to 4 extra disks | $95.32/mo | Game servers, small databases, build agents | [ View plan and availability](https://my.ava.hosting/aff.php?aff=15562) |
| 2x Xeon E5-2680 v2 | 20C/40T · 256GB DDR3 ECC · 8x600GB SAS · RAID controller | $111.02/mo | RAM-heavy and storage-heavy workloads | [ View plan and availability](https://my.ava.hosting/aff.php?aff=15562) |
| 2x Xeon E5-2620 v3 | 12C/24T · from 32GB DDR4 · from 1TB SSD · RAID controller | $134.57/mo | Web and application hosting | [ View plan and availability](https://my.ava.hosting/aff.php?aff=15562) |
| 2x Xeon E5-2699 v3 | 36C/72T · from 32GB DDR4 · from 1TB SSD · RAID controller | $167.09/mo | Virtualisation hosts, rendering, parallel jobs | [ View plan and availability](https://my.ava.hosting/aff.php?aff=15562) |

The Ryzen 5 4650G is the newest architecture in the lineup and the only single-socket option. Six cores with strong per-core speed suits Minecraft and similar game servers, a small Postgres instance, or a CI runner better than a 20-core Xeon from 2013 does. It's also the plan whose listing showed **0 available**, with no restock date given.

The 2x E5-2680 v2 is the odd one out in a useful way: 256GB of RAM and eight 600GB SAS drives for $111.02 is a lot of memory and spindles per dollar, and DDR3 with mechanical disks is exactly the trade-off you'd expect at that price. If you're running an in-memory cache, a backup target or a lab box, it works. If your job is CPU-bound, the older cores will show their age. One unit was in stock.

The two DDR4/SSD Xeons are the general-purpose picks. The E5-2620 v3 at $134.57 is the entry point for "I need real hardware and predictable I/O, not maximum cores", while the E5-2699 v3 at $167.09 nearly triples the thread count for $32.56 more per month. That gap is the clearest value jump in the lineup: 36 cores and 72 threads for under $170 doesn't exist in the managed tier of the market.

Two details worth asking about before ordering. The three Xeon listings mention a RAID controller and remote management; the Ryzen listing doesn't, so if out-of-band access matters to you, confirm it rather than assume it. And the plan pages don't state a money-back window, which is the single thing I'd want in writing before paying.

## "Dedicated" is sold as two different products

Search the phrase and you'll get results from two categories that share a name and almost nothing else. netcup, for instance, openly says its root servers are **not classic bare metal**: they're virtualised instances with guaranteed, exclusively assigned CPU cores, RAM and storage, starting at €12.93/month excluding VAT for 2 cores, 4GB and 64GB NVMe, on a 12-month contract with a 30-day money-back guarantee. OVHcloud, by contrast, defines a dedicated server as a machine handing over all of its RAM, storage and compute with no virtualisation layer at all.

The practical split:

- **Dedicated resources on a hypervisor** gets you isolation from noisy neighbours, fast provisioning and a much lower entry price. You don't get your own kernel, you can't run a hypervisor of your own underneath, and hardware-level access is whatever the provider exposes through its console.
- **Bare metal** gets you the full machine. You need it if you're running KVM or Proxmox on top, passing a GPU through, loading a custom kernel or a non-standard OS, or you want IPMI-level control to fix a box that won't boot.

Ava Hosting sells the second kind. If your actual requirement is "a fast, isolated Linux box with root", a €12.93 dedicated-resource instance does the job for a fraction of $95, and the honest answer is that most small teams over-buy here.

## The price on the card versus the price you pay

Advertised entry prices across this market are calculated in at least four different ways.

Dedicated.com lists a $36.00/month starting point, but its own prepay table shows the real structure: a Xeon Gold 6140 with 36 cores, 256GB DDR4, 2x2TB SSD, a 10 Gbps port and 100TB of transfer is **$183.99/month**, or **$1,942.93** on a 12-month prepay. Monthly billing for a year comes to $2,207.88, so the annual discount is about 12%, and 3- and 6-month terms save 3% and 6%.

Contabo's AMD Genoa 24-core listing reads **€179.10/month**, down from €199.00, and the page states plainly that this is the equivalent monthly price of a 12-month subscription including tax, for the first 12 months only. Renewal goes back to the standard rate.

netcup quotes €12.93 excluding VAT and shows €14.87 including 19% German VAT next to it, on a 12-month contract.

Ava Hosting displays plain monthly USD prices with a currency selector, and third-party write-ups report automatic savings of roughly 5–15% when you prepay 3 to 12 months. Treat that as a prompt to check the cart, not a published rate.

Four questions close most of the gap: what does this cost in month 13, what contract length am I committing to, is tax included, and how many IPv4 addresses come with it. That last one has real money attached. Ava Hosting includes **one** IPv4 per server; Dedicated.com includes a /29 with five usable addresses. If you're hosting mail or want dedicated IPs per site, that difference shows up on the invoice.

👉 Check Ava Hosting's dedicated server prices in your currency

## Stock decides whether you launch today

Inventory is the part of this market that pricing pages hide. Dedicated.com's snapshot at 10:40 UTC on 11 November 2026 showed **39 configurations, 32 in stock**, and a starting price of $36.00 attached to an 8GB DDR3 machine with two 1TB drives that had two units left in Los Angeles. Most of the $43.99 to $63.99 older-platform configs were marked sold out everywhere, including the well-specced $183.99 Gold 6140.

Ava Hosting shows the same pattern on a smaller scale: the $95.32 Ryzen at zero, the $111.02 dual E5-2680 v2 at one unit, and the two DDR4 Xeons without a stock count. Older and cheaper hardware is what sells out first, because that's what everyone clicks.

Delivery speed varies as much as price. Dedicated.com deploys in-stock servers the moment payment clears, with the OS install taking about 20 minutes and credentials emailed automatically. OVHcloud advertises under 120 seconds. netcup says a few minutes. If your migration window is a weekend, "in stock and installs in 20 minutes" is worth more than a $20 saving on a config you'll wait three weeks for. Both Dedicated.com and Ava Hosting let you check availability before committing, and out-of-stock sites can notify you when a line returns.

👉 See which Ava Hosting configurations are in stock right now

## Managed or self-managed changes the comparison completely

Ava Hosting's 36-core, 72-thread E5-2699 v3 at $167.09/month is unmanaged. You handle the kernel, the firewall, the DDoS tuning beyond the included filtering, and the backups.

Liquid Web's entry dedicated plan, on a page dated March 2025, lists an Intel 6226R with 16 cores, 64GB RAM, 2x960GB SSD in RAID-1 and 10TB of bandwidth at **$167.50/month** with 50% off the first two months, and includes 99.99% uptime, built-in DDoS protection and 24/7 expert management. Roughly the same money buys half the cores and a quarter of the threads, plus a team that patches the box for you.

That's the actual decision most readers face, and it has nothing to do with which provider is "better". If nobody on your team wants to be paged at 3am, the managed premium is cheap. If you have someone who's comfortable with a shell, self-managed hardware buys dramatically more machine per dollar.

## What third-party coverage says about Ava Hosting

A 2026 review on an independent review site describes the facility as a hardened underground data centre built into a former military shelter in Moldova, with roughly 50 Gbit/s of network capacity, about 1.6 MW of power backed by generators, and DDoS mitigation measured in the hundreds of Gbit/s. Support runs 24/7 over chat, ticket and phone, with replies typically in the 15 to 30 minute range during that reviewer's testing.

The same page carries a verified customer review scored 2.5/5 complaining about slow ticket responses and load times that swing between fast and slow. Both things can be true of the same provider, and on a budget offshore host the support queue is the part I'd test first with a pre-sales ticket. The Moldovan jurisdiction is also the selling point for some buyers and a disqualifier for others, so decide which before you order.

👉 Compare the four Ava Hosting configurations side by side

## Who shouldn't rent a dedicated server

A blog, a small API, a single WordPress site, a VPN for a handful of users: none of these need physical hardware. A VPS or a dedicated-resource instance handles them at €5 to €40 a month, with snapshots and a console included. Renting metal for that workload means paying three to ten times more for capacity you'll never touch, and taking on patching you didn't have to do.

The same applies if you need someone else to own the uptime. Self-managed bare metal means the DDoS scrubbing rules, the kernel hardening and the backup rotation are yours. Providers will sell you the box; they won't run it.

## FAQ

**Why can't I buy the $36 server I saw advertised?**
Because it's a clearance configuration with a handful of units. Dedicated.com's $36.00 plan had two left in one location, and most of its $43.99–$63.99 configs were sold out everywhere. The price is real, the availability isn't.

**Does "dedicated resources" count as a dedicated server?**
Not in the bare-metal sense. netcup states outright that its root servers are a virtualised alternative, not classic bare metal, even though CPU cores, RAM and storage are reserved for you. It's a fine product with a 30-day money-back guarantee and a 12-month term; it just isn't the same thing as owning the machine.

**Is unlimited traffic really unlimited?**
Read the footnote. Contabo's unlimited traffic is subject to fair-use and the provider reserves the right to throttle at its discretion for exceptionally high or disruptive usage. OVHcloud's bare metal is unlimited by default but reserves the right to cut outgoing public bandwidth by up to 50% if it affects other users. Unlimited traffic and unlimited bandwidth are different promises.

**How much does prepaying actually save?**
At Dedicated.com, a 12-month prepay on the $183.99 Gold 6140 comes to $1,942.93 against $2,207.88 paid monthly, about 12%. Contabo's €179.10 headline is a 12-month subscription average including tax, for the first year only. Compare month-13 prices, not month-one prices.

**Can I get a refund if it doesn't work out?**
netcup offers 30 days. Ava Hosting's plan listings don't state a refund window, so get the terms confirmed in writing before paying. Prepay discounts usually make refunds messier, not cleaner.

## How to choose

Match the workload, not the spec sheet:

- **Under 10 people, one app, no ops capacity** → a VPS or dedicated-resource instance, or a managed dedicated plan around $167/month.
- **Game server, small database, or CI** → Ava Hosting's 6-core Ryzen at $95.32, if it's in stock.
- **General web and app hosting on real hardware** → the 2x E5-2620 v3 at $134.57.
- **Virtualisation, rendering, heavy parallelism** → the 2x E5-2699 v3 at $167.09, which is the strongest price-to-thread ratio in the lineup.
- **Maximum RAM and disk on a budget, CPU secondary** → the 2x E5-2680 v2 at $111.02, while its single unit lasts.

Two things to confirm before checkout: whether the configuration you want is actually available today, and whether the price you're looking at is monthly, prepaid, or tax-inclusive. Everything else is a preference.

👉 Start with Ava Hosting's dedicated server lineup and current stock
