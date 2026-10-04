# Best rotating residential proxies: what to check before you pay, plus every 9Proxy plan and price

Rotation is the easiest thing to advertise and one of the harder things to get right. Every provider page promises "millions of IPs" and "auto-rotation," then you plug the endpoint into your scraper and discover the rotation is either too blunt (a new IP every single request, so no session ever survives a login) or too rigid (the same /24 subnet for an hour, so the target flags you after 200 requests).

If you searched for the best rotating residential proxies, the useful answer isn't a ranking. It's knowing which knobs actually matter, then matching those knobs to how your workload burns data. Below is that checklist, applied honestly to one provider — 9Proxy — whose pricing structure happens to suit rotation-heavy work better than most, along with its full current plan list so you can price your own workload.

## What "rotating" means in practice

A rotating residential proxy is an endpoint where the exit IP changes on a schedule you control. That control comes in three flavours, and providers often only support one:

**Per-request rotation.** Every request leaves through a fresh residential IP. This is what you want for SERP checks, price monitoring, and any task where each request is independent.

**Sticky sessions.** The IP stays fixed for a set number of minutes (or until you release it). Needed for logins, carts, multi-step forms, and anything with state.

**Rotating a fixed pool.** You buy N IPs and the tooling rotates through them, sometimes refreshing dead ones on a timer. This is the old 911-style workflow, and it behaves completely differently from a bandwidth-based rotation endpoint: bandwidth is usually unmetered, but the pool size is your hard ceiling.

A provider that only does flavour one will quietly break your account-based tasks. A provider that only does flavour three can't handle 50,000 low-bandwidth requests spread across a thousand cities. Both are called "rotating residential proxies" on the pricing page.

## The five checks that separate usable rotating proxies from cheap ones

**1. Rotation granularity, not just rotation existence.** Can you set the sticky window yourself? Can you run several sticky IPs in parallel from the same configuration? Can you force a random IP for one request and keep the next one fixed?

**2. Geo depth.** Country-level targeting is table stakes. City, state, ZIP, and ISP filtering are what make local SEO checks, ad verification, and offer testing actually meaningful — and they're also the first thing to disappear on budget tiers.

**3. Protocols and auth.** SOCKS5 support matters if you're running anti-detect browsers, Playwright, or proxychains. Username/password auth matters for scripts; IP whitelisting matters for servers and cloud jobs where you can't inject credentials.

**4. Balance behaviour.** Prepaid balance that expires in 30 days is a different product from balance that sits for six months. If your projects are bursty — a big crawl this month, quiet next month — an expiring balance quietly turns into a wasted purchase.

**5. What happens to a bad IP.** Residential IPs die naturally. The question is whether a dead one costs you money.

## How 9Proxy handles rotation

9Proxy runs a residential pool advertised at 20M+ IPs across 90+ countries, with HTTP/HTTPS and SOCKS5 support and targeting down to country, state, city, ZIP, and ISP. It sells two distinct models, and rotation works differently in each — this is the part worth reading twice.

**Residential by GB** is built for rotation. You buy traffic, not IPs, and can generate unlimited endpoints. Two modes:

- *Rotating:* a new IP per request. No session parameters needed.
- *Sticky:* you set `sst-<minutes>` in the username and the IP holds for that window. Adding `ssid-<id>` gives you multiple parallel sticky IPs from the identical configuration, which is how you keep ten accounts on ten separate residential IPs without buying ten packages.

Targeting lives in the username string, so a rotating New York endpoint looks like:


subaccount-country-us-city-newyork


and a 15-minute sticky US session:


subaccount-country-us-sst-15-ssid-device1


ISP-level filtering follows the same pattern (`isp-as22773_Cox_Communications_Inc.`), which is useful when a detection layer fingerprints the carrier and not just the IP. One practical note from the docs: over-filtering (state + city + ISP all at once) narrows the pool and slows responses. Country-only targeting is the fastest.

**Residential by IPs** works the other way. You buy a fixed number of IPs with unlimited bandwidth, and each IP naturally lives anywhere from a few hours to about 24 hours. There's no per-request rotation here by default. Rotation is handled by the desktop app's Auto Rotation Proxy, which swaps IPs on selected ports at intervals you define, plus an auto-refresh feature that replaces ports that go offline. The trade-off is real: you get unmetered traffic, but you need the 9Proxy app running locally (Windows or macOS), because traffic is routed through local port forwarding.

There's also a small documented refund policy worth knowing about: if an IP fails within 60 seconds of activation, it gets credited back, and the Today List lets you reuse IPs you already touched in the last 24 hours at no extra charge. For testing-heavy workflows, those two things cut waste more than a small discount does.

## Every current 9Proxy plan and price

The prices below reflect the adjustment that took effect on 1 June 2026, when IP-based and bundle pricing went up and GB-based pricing stayed as it was. Rates change; confirm the numbers on the plan page before you commit.

### Residential by IPs (unlimited bandwidth per IP)

| Plan | What you get | Unit price | Total | Validity | Buy |
| --- | --- | --- | --- | --- | --- |
| 100 IPs | 100 residential IPs, unlimited traffic | $0.24 / IP | $24 | Unused IPs don't expire | [Start with the 100 IP pack](https://bit.ly/9-Proxy) |
| 500 IPs | 500 residential IPs, unlimited traffic | $0.144 / IP | $72 | Unused IPs don't expire | [Get the 500 IP package](https://bit.ly/9-Proxy) |
| 1,000 + 500 bonus IPs | 1,500 IPs in total, unlimited traffic | $0.084 / IP | $126 | Unused IPs don't expire | [Take the 1,500 IP pack with bonus](https://bit.ly/9-Proxy) |
| 2,500 IPs | 2,500 residential IPs, unlimited traffic | $0.084 / IP | $210 | Unused IPs don't expire | [Buy 2,500 IPs](https://bit.ly/9-Proxy) |
| 5,000 IPs | 5,000 residential IPs, unlimited traffic | $0.072 / IP | $360 | Unused IPs don't expire | [Buy 5,000 IPs](https://bit.ly/9-Proxy) |
| 15,000 IPs | 15,000 residential IPs, unlimited traffic | $0.048 / IP | $720 | Unused IPs don't expire | [Buy 15,000 IPs](https://bit.ly/9-Proxy) |
| 25,000 IPs | 25,000 residential IPs, unlimited traffic | $0.035 / IP | $863 | Unused IPs don't expire | [Buy 25,000 IPs](https://bit.ly/9-Proxy) |
| 50,000 IPs | 50,000 residential IPs, unlimited traffic | $0.029 / IP | $1,438 | Unused IPs don't expire | [Buy 50,000 IPs](https://bit.ly/9-Proxy) |
| 100,000 IPs (Business) | 100,000 residential IPs, unlimited traffic | $0.023 / IP | $2,300 | Unused IPs don't expire | [Request the 100,000 IP tier](https://bit.ly/9-Proxy) |
| 200,000 IPs (Business) | 200,000 residential IPs, unlimited traffic | $0.021 / IP | $4,140 | Unused IPs don't expire | [Request the 200,000 IP tier](https://bit.ly/9-Proxy) |
| 500,000 IPs (Business) | 500,000 residential IPs, unlimited traffic | $0.018 / IP | $8,625 | Unused IPs don't expire | [Request the 500,000 IP tier](https://bit.ly/9-Proxy) |

### Residential by GB (rotating and sticky endpoints)

| Plan | What you get | Rate | Total | Validity | Buy |
| --- | --- | --- | --- | --- | --- |
| 5 GB | Rotating + sticky endpoints | $3.00 / GB | $15 | 180 days | [Test rotation with 5 GB](https://bit.ly/9-Proxy) |
| 50 GB + 5 GB bonus | 55 GB of rotation traffic | $2.10 / GB | $105 | 180 days | [Get the 55 GB pack](https://bit.ly/9-Proxy) |
| 100 GB | Rotating + sticky endpoints | $1.50 / GB | $150 | 180 days | [Buy 100 GB](https://bit.ly/9-Proxy) |
| 200 GB | Rotating + sticky endpoints | $1.00 / GB | $200 | 180 days | [Buy 200 GB](https://bit.ly/9-Proxy) |
| 1,000 GB | Rotating + sticky endpoints | $0.80 / GB | $800 | 180 days | [Buy 1,000 GB](https://bit.ly/9-Proxy) |
| 2,000 GB | Rotating + sticky endpoints | $0.75 / GB | $1,500 | 180 days | [Buy 2,000 GB](https://bit.ly/9-Proxy) |
| Enterprise 3,000 GB | Rotating + sticky, team features | $0.72 / GB | $2,160 | No expiry | [Ask about Enterprise 3,000 GB](https://bit.ly/9-Proxy) |
| Enterprise 6,000 GB | Rotating + sticky, team features | $0.70 / GB | $4,200 | No expiry | [Ask about Enterprise 6,000 GB](https://bit.ly/9-Proxy) |
| Enterprise 10,000 GB | Rotating + sticky, team features | $0.68 / GB | $6,800 | No expiry | [Ask about Enterprise 10,000 GB](https://bit.ly/9-Proxy) |

Enterprise plans also include team mode (one owner plus up to five members), non-expiring shared bandwidth inside the team, per-member traffic controls, activity logs, and unlimited share code generation.

### Bundle plans (IPs plus traffic)

| Plan | What you get | Total | Notes | Buy |
| --- | --- | --- | --- | --- |
| Starter Bundle | 100 IPs + 5 GB | $30 | Traffic valid 180 days | [Grab the Starter Bundle](https://bit.ly/9-Proxy) |
| Popular Bundle | 1,500 IPs + 50 GB | $180 | Traffic valid 180 days | [Grab the Popular Bundle](https://bit.ly/9-Proxy) |
| Pro Bundle | 5,000 IPs + 500 GB | $720 | Traffic valid 180 days | [Grab the Pro Bundle](https://bit.ly/9-Proxy) |

The bundles are only worth it if you'd otherwise buy both halves. Run the arithmetic: the Starter Bundle at $30 beats buying 100 IPs ($24) plus a 5 GB pack ($15) separately, which comes to $39. The Popular Bundle at $180 is cheaper than 1,500 IPs ($126) plus 55 GB ($105) bought apart. If your workload is purely rotation-based with no fixed-IP needs, ignore bundles entirely and stay on GB pricing.

## Which model fits which rotating workload

Rough decision rules that hold up in practice:

- **Requests are small and spread out.** Scraping product pages, checking rankings, polling APIs, geo-QA. Go GB-based. You rotate across the entire pool and only pay for bytes.
- **Requests are large and few.** Pulling big JSON payloads, downloading media, long-running sessions on a handful of IPs. Go IP-based, where bandwidth is unmetered.
- **You need both.** Multi-account operations that also crawl. Bundle, or split the budget: a small IP pack for the accounts, a GB pack for the crawling.
- **You need a specific city but not a specific IP.** GB-based with `city-` targeting. City-level filtering is available there, and hunting for the same city on a fixed-IP package is the slower path.

One number worth doing before purchase: estimate bytes per request × requests per month. A text-heavy scraper often runs 40–80 KB per response; at 100,000 requests that's 4–8 GB, so the entry GB pack covers it. If your per-request payload is a few megabytes of images, the arithmetic flips hard toward unmetered IPs.

## Setting up a rotating endpoint

The GB route is the low-friction one. In the dashboard you pick country, state, city, ZIP, or ISP, generate endpoints, and export as `.txt` or `.csv` with ready-made code samples. Authentication is username/password, or IP whitelisting if you're running from a fixed server. A minimal test:

bash
curl -x your_proxy_host:your_port \
     -U "subuser-country-us:yourpassword" \
     https://ipinfo.io


Run it five times with the same username and you'll see five different exit IPs. Add `sst-15` to the username and the same command returns the same IP for fifteen minutes. That single string is the whole rotation configuration — no software, no local proxy layer.

The IP-based route needs the desktop app, because traffic is forwarded through local ports with optional proxy authentication. It's a heavier setup, but once ports are configured you can rotate on custom intervals, save location and ISP filters, and let auto-refresh swap out dead ports without restarting anything.

If you're starting from zero and want to compare the two dashboards side by side, 👉 [open a 9Proxy account and look at both plan types](https://bit.ly/9-Proxy) before buying traffic.

## Where rotation helps, and where it actively hurts

Rotation is the right answer for: SERP and SEO monitoring, price intelligence, ad verification, market research across regions, geo-restricted content checks, and broad public data collection where each request stands alone.

Rotation is the wrong answer for: aged social accounts, marketplace seller accounts, anything with multi-step login, and payment-adjacent workflows. Aggressive IP switching on those triggers re-verification, session resets, and trust score damage — and the usual conclusion ("the proxies are bad") is wrong. The problem is the pattern, not the IP. If that's your workload, buy the IP-based package and use sticky sessions measured in hours, not requests. 9Proxy's own documentation draws the same line: rotating mode for speed, sticky mode for continuity, and the IP packages for identity-stable work.

## Limits and fine print worth knowing before you buy

- **GB balance expires after 180 days** on all non-Enterprise plans. Bursty projects should either size the pack to what they'll actually burn in six months, or pay for Enterprise to remove the clock.
- **IP-based packages don't rotate natively.** Rotation there depends on the desktop app and port configuration. If you can't run a local client, the GB model is the only viable option.
- **Over-targeting slows you down.** Adding state, city, and ISP filters simultaneously shrinks the available pool. Pick the two that matter.
- **Support and status.** 9Proxy runs 24/7 support through live chat, Telegram, and email. Separately, some third-party comparison sites reported extended service outages during 2026, so it's sensible not to park an entire annual budget in any single provider's wallet — a rule that applies to every budget proxy vendor, not just this one.
- **Pool size isn't class-leading.** At 20M+ IPs across 90+ countries, 9Proxy is smaller than the enterprise-tier networks that advertise 70M–150M+. That matters if you need country coverage in the hundreds; it rarely matters for US, UK, and Western European targets, where the pool depth is concentrated.

## FAQ

**Do I need a subscription?** No. Pricing is prepaid and balance-based, which is unusual in a market full of monthly minimums. You buy IPs or traffic once and use them at your own pace.

**Can I rotate on every single request?** Yes, on GB-based traffic — that's the default rotating mode. Just omit the `sst` parameter from the username.

**Can I hold one IP for longer than a few minutes?** Yes. Set `sst` to the number of minutes you need, and add `ssid` if you want several independent sticky IPs running at once from the same setup.

**What protocols are supported?** HTTP, HTTPS, and SOCKS5, which covers anti-detect browsers, Python and Node scraping stacks, and proxychains-style routing.

**How do I pay?** Card, crypto, and Google Pay are among the listed options.

**What's the cheapest way to test rotation?** The 5 GB pack at $15. It's enough for tens of thousands of text-based requests, and it tells you more about success rates on your actual targets than any review will.

## The short version

If your work is rotation-first — many small requests, geographic spread, no persistent identity — the GB model is the sensible structure, and 9Proxy's entry rate and lack of a subscription make it cheap to validate against your own targets. Buy 5 GB, run your real workload through it for a week, and look at the success rate and how much traffic you actually consumed. Then size up: 200 GB at $1.00/GB is the tier where most mid-volume operations land, and the 1,500 IP pack at $126 covers the parts of the job that need a stable identity.

👉 [See the current 9Proxy plans and pick the one that matches your rotation volume](https://bit.ly/9-Proxy)
