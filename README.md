# DMIT Eyeball: What the CMIN2 Mid-Tier Actually Delivers, Which Plans Are Still on Sale, and How to Pick One

Search for DMIT Eyeball and you'll find a mess. Some guides still quote `TYO.EB` prices for a Tokyo line that got discontinued. Others list "HKG EBv2" plans at $29.90/month that vanished in August. And the Los Angeles numbers differ depending on which hardware platform the writer happened to screenshot.

The reason is simple: Eyeball has been DMIT's most restless product line. It gets renamed, repriced, discontinued, and relaunched more often than either of the other two network tiers. So instead of another generic "DMIT review," here's what Eyeball actually is, which plans you can still order, what they cost, and where the line stops making sense.

One warning before the tables: DMIT's stock and pricing move quickly, and Eyeball has been repriced more than once. Everything below is cross-checked against recent plan listings and DMIT's own product descriptions, but confirm the figure in your cart before paying.

## What "Eyeball" means inside DMIT's lineup

DMIT is a US-registered VPS provider (New York) selling KVM virtual servers in Los Angeles, Hong Kong, and Tokyo. It splits every location into three network tiers, and the tier matters more than the CPU does.

- **Tier 1 (T1)** — plain international BGP. Cheap, big traffic allowances, no China routing work at all.
- **Eyeball (EB)** — Tier 1 transit plus what DMIT calls "reasonable effort" China routing. This is the middle tier.
- **Premium (Pro)** — CN2 GIA and premium backbone, with China routing treated as a guarantee rather than an effort.

The word DMIT uses in its own Eyeball product description is the important one: **reasonable effort**. Not guaranteed, not SLA-backed. On the Los Angeles Eyeball line, the routes shake out roughly like this:

- China Telecom: AS9929 / AS58807 load balancing
- China Unicom: AS9929
- China Mobile: AS58807 (CMIN2)

| Tier | China routing promise | Who it suits | Price position |
| --- | --- | --- | --- |
| Tier 1 | None | International sites, backups, CI/CD, transit nodes | Lowest |
| Eyeball | Reasonable effort (CMIN2 / CMI / 9929) | Mobile-heavy audiences, budget-conscious projects that still want decent China latency | Middle |
| Premium | Best-effort guaranteed CN2 GIA, both directions | Business sites and anything where evening peak stability is non-negotiable | Highest |

A practical consequence: on Eyeball, the routes can be adjusted. That isn't marketing hedging, it's an operational reality of the tier. If you need a route that won't change under you, you're shopping in the wrong line.

## Which DMIT Eyeball plans are actually still available

This is where most published guides are out of date, so take it location by location.

### Los Angeles — the live, mainstream Eyeball line

LAX Eyeball is the one to look at. It runs on two hardware generations: AS3 (AMD EPYC 7003) and the newer AN5 platform (AMD EPYC 9000 series). Both come with KVM virtualisation, enterprise NVMe storage, one IPv4 and one IPv6 /64 by default, and traffic that throttles instead of cutting off.

Los Angeles also has the widest spread of configurations, from a 1-core entry box to a 6-core, 30 TB machine. It restocks in batches, and each batch has sold out within weeks.

### Hong Kong — alive, but officially in Beta

Hong Kong Eyeball exists again, on both AS3 and AN5 hardware. DMIT's own product profile carries a warning worth reading in full before you pay:

> HKG Eyeball is currently in Beta. The product and its network routing are still being tuned and optimized, so performance and routes may change. It is not yet recommended for production workloads that require high stability.

The same profile describes the network as "Tier 1 + Reasonable Effort For China Routing." Hong Kong Eyeball routes lean on CMI, which makes it a genuinely good fit for China Mobile users and a weaker fit for Telecom and Unicom at peak hours.

If you're deploying something you can't afford to have re-routed mid-month, put Hong Kong Eyeball in the "test and watch" bucket rather than the production bucket.

### Tokyo Eyeball — discontinued

The `TYO.AS3.EB` line was withdrawn. Archived listings show it ran from an entry plan around $25.90/month up to a large 8-core configuration in the $749.90/month range, with China Telecom and Unicom going out via CTG GIA and China Mobile over CMI. That's history now. If a guide is selling you a Tokyo Eyeball plan, it's stale.

### Hong Kong EBv2 — discontinued, with a migration path

The older Hong Kong Eyeball generation, sold as `HKG.EB.TINYv2`, `STARTERv2` and so on at $29.90 / $59.90 / $89.90 per month, was retired on 10 August 2026. Affected customers were offered refunds pro-rated to remaining service value, plus a migration discount on other DMIT products reported in the 20–30% recurring range depending on which notice you read.

This is why two Hong Kong Eyeball price lists can both be "real" and still disagree with each other. The `v2` names and prices belong to a deleted product line. The current names are `HKG.AS3.EB.*` and `HKG.AN5.EB.*`, at different prices.

## DMIT Eyeball pricing: the Los Angeles AS3 lineup

Monthly prices, USD, one IPv4 plus IPv6 /64 on every plan.

| Plan | CPU | RAM | SSD | Traffic / month | Port | Price | After quota | Order |
| --- | --- | --- | --- | --- | --- | --- | --- | --- |
| LAX.AS3.EB.TINY | 1 vCore | 2 GB | 20 GB | 1.5 TB | 2 Gbps | $10.90/mo | 4 Mbps unmetered | [Check TINY availability](https://www.dmit.io/aff.php?aff=12046) |
| LAX.AS3.EB.Pocket | 2 vCore | 2 GB | 40 GB | 3 TB | 4 Gbps | $16.90/mo | 4 Mbps unmetered | [See the Pocket plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX.AS3.EB.STARTER | 2 vCore | 2 GB | 80 GB | 5 TB | 10 Gbps | $34.90/mo | 4 Mbps unmetered | [Open STARTER details](https://www.dmit.io/aff.php?aff=12046) |
| LAX.AS3.EB.MINI | 4 vCore | 4 GB | 80 GB | 10 TB | 10 Gbps | $62.90/mo | 8 Mbps unmetered | [View the MINI plan](https://www.dmit.io/aff.php?aff=12046) |
| LAX.AS3.EB.MICRO | 4 vCore | 4 GB | 160 GB | 14 TB | 10 Gbps | $87.90/mo | 8 Mbps unmetered | [Check MICRO specs](https://www.dmit.io/aff.php?aff=12046) |
| LAX.AS3.EB.MEDIUM | 6 vCore | 8 GB | 160 GB | 30 TB | 10 Gbps | $199.90/mo | 10 Mbps unmetered | [See the MEDIUM plan](https://www.dmit.io/aff.php?actor=12345) |

Two things stand out in that table. First, the jump from Pocket to STARTER costs $18 and buys you 2 TB more traffic plus a 10 Gbps port, which is where the value curve bends. Second, the traffic allowances are large relative to the price, and that is the entire point of Eyeball. The tier exists because not everyone needs CN2 GIA badly enough to pay for it.

The AN5-platform Los Angeles Eyeball configs overlap with these at the entry end and stretch further up. DMIT's store shows them at similar price points with newer EPYC silicon, so if AS3 is out of stock, there's often an AN5 equivalent sitting next to it.

## DMIT Eyeball pricing: Hong Kong AS3 lineup

| Plan | CPU | RAM | SSD | Traffic / month | Port | Price | Order |
| --- | --- | --- | --- | --- | --- | --- | --- |
| HKG.AS3.EB.WEE | 1 vCore | 1 GB | 20 GB | 500 GB | 500 Mbps | $24.90/mo | [Check the WEE entry plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.AS3.EB.TINY | 1 vCore | 1 GB | 20 GB | 800 GB | 1 Gbps | $39.90/mo | [View Hong Kong TINY](https://www.dmit.io/aff.php?aff=12046) |
| HKG.AS3.EB.STARTER | 1 vCore | 2 GB | 40 GB | 1.5 TB | 1 Gbps | $79.90/mo | [See STARTER in Hong Kong](https://www.dmit.io/aff.php?aff=12046) |
| HKG.AS3.EB.MINI | 2 vCore | 4 GB | 60 GB | 2.2 TB | 1 Gbps | $126.90/mo | [Open the MINI plan](https://www.dmit.io/aff.php?aff=12046) |
| HKG.AS3.EB.MICRO | 4 vCore | 4 GB | 80 GB | 3 TB | 1 Gbps | $179.90/mo | [Check MICRO in Hong Kong](https://www.dmit.io/aff.php?aff=12046) |
| HKG.AS3.EB.MEDIUM | 4 vCore | 8 GB | 160 GB | 4 TB | 1 Gbps | $239.90/mo | [See MEDIUM details](https://www.dmit.io/aff.php?aff=12046) |

The Hong Kong AN5 Eyeball tier continues above that, starting around $149.90/month for a 4 vCore / 4 GB / 80 GB machine with 2.2 TB of traffic and climbing to roughly $759.90/month for a 12 vCore / 24 GB / 640 GB box with 9 TB. Same network profile, newer hardware.

Compare the two tables and the Hong Kong premium is obvious. $39.90 gets you 800 GB in Hong Kong; $34.90 gets you 5 TB in Los Angeles. You are buying roughly 40 milliseconds, and you are paying a lot per gigabyte for it.

## What happens when you burn through the traffic allowance

This is the detail that separates buyers into happy and annoyed, and it's worth its own section.

Eyeball plans don't get shut off when the monthly quota runs out. They drop to a slow unmetered speed. On the Los Angeles AS3 line that's 4 Mbps on the smaller plans, 8 Mbps from MINI upward, and 10 Mbps on MEDIUM.

For context, Tier 1 plans throttle to somewhere between 100 Mbps and 500 Mbps depending on size. Eyeball's post-quota speed is an order of magnitude slower. So if your workload is "steady, predictable traffic with occasional spikes," Eyeball's overage behavior is fine. If your workload is "I routinely blow past the quota and need usable speed afterwards," Tier 1 or a larger Eyeball plan is the honest answer, because 4 Mbps won't carry much.

## Eyeball vs Premium vs Tier 1: how to actually choose

Here's the comparison that matters most, and it's counterintuitive.

On the Los Angeles AS3 lineup, Premium TINY costs $10.90/month with 1 TB of traffic on a 1 Gbps port. Eyeball TINY costs the same $10.90/month with 1.5 TB of traffic on a 2 Gbps port, and routes over CMIN2/9929 instead of guaranteed CN2 GIA. Premium's entry plan also appears at $9.99/month on the AN5 platform.

Same money, different bet. You're choosing between route quality guarantees and raw traffic plus port speed. Neither is wrong, but they serve different people:

- **Pick Premium** if your visitors are on China Telecom, if you need evening peak stability that doesn't wobble, or if your site is revenue-bearing and latency complaints cost you more than bandwidth does.
- **Pick Eyeball LAX** if your audience skews China Mobile, if you push a lot of data (media, APIs, mirrors, backups with a public endpoint), or if you simply don't want to pay CN2 GIA prices per gigabyte.
- **Pick Eyeball Hong Kong** if your users are in Hong Kong, Taiwan, or Southeast Asia and mainland China is secondary. The physical latency is the whole product here.
- **Pick Tier 1** if your traffic never touches China. There's no reason to subsidise China routing you don't use.

The Premium-versus-Eyeball Premium decision is the one worth thinking hardest about, because at the entry tier they cost identical money. Buy Eyeball for the 50% traffic bump and the wider port. Buy Premium for the fact that nobody at DMIT is allowed to shrug if the route degrades.

## DMIT Eyeball coupons and current promos

DMIT doesn't run continuous sales. It discounts in bursts and then stops. A few things worth knowing:

- **Entry Eyeball plans are usually excluded from coupons.** The TINY and WEE-class machines are the loss leaders; DMIT has historically blocked discount codes on them rather than stack a coupon on top of an already thin margin. If a stock-restocked entry plan is in front of you, buy it rather than hunting for a code.
- **A recurring 20% code for non-monthly LAX Eyeball has been circulating** under the name `LAX-EB-LAUNCH-NON-MONTHLY-RECURRING-20OFF`. It applies to non-monthly billing cycles and recurs, meaning the discount repeats on renewal. It shows up in multiple independent promo trackers, but codes rotate and expire. Validate it in the cart with the "Validate Code" button before assuming it works.
- **Seasonal stacks have appeared for LAX Pro and EB.** Trackers have listed codes like `2025-XMAS-LAX-PRO-EB-10-OFF-RECURRING` (10% recurring) and a 15%-plus-cashback variant restricted to annual STARTER plans and above.
- **Legacy Standard network codes** such as `Lite-Annually-Recur-30OFF` still get cited for annual billing on the old Standard line, but they don't map cleanly onto the current Eyeball SKUs.

Treat all of that as "worth trying in the cart," not as a price you can count on. Third-party coupon lists go stale silently, and DMIT frequently ships restocks with no code at all. The reliable pattern is: monthly billing for a first test, then a non-monthly cycle with a validated recurring code once you know the plan works for you.

👉 [Validate today's Eyeball pricing and stock](https://www.dmit.io/aff.php?aff=12046)

## Before you order

A few practical notes that come up repeatedly with this line.

**Stock is genuinely volatile.** Los Angeles Eyeball has sold out in repeated cycles, and DMIT has paused sales entirely in the past while waiting for new hardware to land. Restocks are announced without long notice and the cheaper configs go first. If you need a specific configuration, waiting for a "better moment" has historically been the wrong strategy.

**The Hong Kong Beta warning is not decoration.** Reroutes during a Beta period can change how your service performs against benchmarks you took on day one. Keep a fallback.

**Payments are China-friendly.** Alipay, PayPal, and major cards are supported, which removes the foreign-card problem for a lot of buyers.

**The refund window is short.** Third-party guides consistently describe a window of only a few days on a first purchase, conditional on not breaching the terms of service and on the IP not being blocked. It isn't a free trial. Decide what you're buying before checkout, and run your own throughput and latency tests immediately after delivery.

**Order from a clean connection.** DMIT's billing-side fraud screening is strict, and community guidance is unanimous about not signing up through a proxy or VPN if you want the order to clear.

**IP quality is not a promise.** DMIT's IPs have a good reputation for streaming and AI service access, and the Premium line generally does better than Eyeball. But no tier comes with an unlock guarantee, and the terms are clear that specific streaming access isn't contractual.

**Test routes before committing to a year.** DMIT publishes Looking Glass endpoints per network, which lets you trace the actual path from your city to the Los Angeles or Hong Kong Eyeball nodes before you pay for anything.

## Common questions about DMIT Eyeball

**Is DMIT Eyeball still available?**
Yes, in Los Angeles and Hong Kong. The Tokyo Eyeball line is retired, and the older Hong Kong EBv2 generation was shut down on 10 August 2026. What's on sale now is `LAX.AS3.EB` / `LAX.AN5.EB` and `HKG.AS3.EB` / `HKG.AN5.EB`.

**Is Eyeball worse than Premium?**
Different, not worse. Premium guarantees premium China routing in both directions. Eyeball makes a reasonable effort and compensates with more traffic and bigger ports at the same price. For China Mobile-heavy audiences, Eyeball often measures better than people expect.

**Why is Hong Kong Eyeball so much more expensive per gigabyte?**
Hong Kong bandwidth costs more than Los Angeles bandwidth. The $39.90 Hong Kong plan ships 800 GB; the $34.90 Los Angeles plan ships 5 TB. You're paying for proximity, not capacity.

**What happens when I exceed the traffic limit?**
The server keeps running at a throttled unmetered speed, 4 to 10 Mbps on Los Angeles AS3 Eyeball plans. It doesn't stop, but it slows down considerably.

**Should I start monthly or annual?**
Monthly first, always, for a product line that reroutes. Once the plan has held up through a couple of peak-hour cycles, move to a non-monthly cycle and try a recurring code on the renewal.

👉 [Start with the Eyeball plan that fits your traffic](https://www.dmit.io/aff.php?aff=12046)

## The short version

Eyeball is the tier you buy when CN2 GIA is more than your routing needs justify, and Los Angeles is where that trade-off pays off best: $10.90/month for 1.5 TB and a 2 Gbps port, scaling to 30 TB at $199.90/month. Hong Kong Eyeball gives you proximity and China Mobile routing at a steep price per gigabyte, and it's still officially in Beta. Tokyo's gone, the old Hong Kong v2 line is gone, and the codes floating around for the line mostly don't apply to the entry plans anyway.

Check what's in stock before you plan around it. This line sells out, and the good configurations are the first to go.

👉 [See current DMIT Eyeball availability](https://www.dmit.io/aff.php?aff=12046)
