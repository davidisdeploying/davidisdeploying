## David Gomez

I build AI systems, and applications with them.

Configuration Technician by day. The rest of the time I run a multi-node Linux fleet at home and the agent platform that runs on top of it — tool calling over MCP, retrieval over my own notes, model routing that picks the cheapest model that can do the job, and a rule that nothing counts as done until it can prove it.

Everything here is self-hosted and in daily use by me. None of it is a demo.

I came to this from infrastructure, not from software engineering. My degree is an AAS in cloud computing, and the programming foundation under it is that degree's Python coursework plus Harvard's CS50P. Everything here is built with AI writing most of the code. What I own is the architecture, the machines it runs on, the review of every diff, and the verification: nothing counts as done until it proves it.

### The agent platform

**[Tower](https://github.com/davidisdeploying/tower)** — an MCP server that turns the fleet into a pool of AI workers. 21 typed tools, quota-aware routing across Claude, GPT and Gemini plus a local open-weight model on my own GPU, jobs serialised by what they touch rather than by which machine runs them, and an evidence contract: exit 0 means the process ended, not that the work happened.

**[Nexus](https://github.com/davidisdeploying/nexus)** — the operator surface for it. Live node health, running and finished agent jobs with the evidence each returned, and tiered retrieval over my own notes: compact cards first, a separate index over working history second, raw sources only for an audit.

### Applications

**[Loupe](https://github.com/davidisdeploying/loupe)** — photo culling with its own ML pipeline. Face clustering, scene and aesthetic scoring across ~80k frames, every model running on my own GPU. [loupeculling.com](https://loupeculling.com)

**[Waypoint](https://github.com/davidisdeploying/waypoint)** — study and credential workspace joining certification milestones to a corpus-and-coaching engine over my own reference library.

**[Prospect](https://github.com/davidisdeploying/prospect)** — local-first job-application tracker with a browser capture extension.

**[Homestead](https://github.com/davidisdeploying/homestead)** — house-hunting workspace built on immutable capture: listing sites edit and pull their own pages, so each capture is archived as evidence and the comparable-property database rebuilds from it.

**[Breadcrumbs](https://github.com/davidisdeploying/breadcrumbs)** — grocery receipt itemizer. A browser extension that turns one lump "GROCERY $127.22" charge into every line item at the price actually paid, read from the tab already open, so nothing is stored and nothing leaves the browser.

### Homelab — the fleet underneath

Machines with defined roles — control plane, standby, GPU compute, deploy host, storage — meshed with Tailscale across two subnets, public services behind Cloudflare Tunnel and Access, and a failover design that got tested for real when the control-plane box died.

### Writing

I keep a devblog at **[davidgomez.cc](https://davidgomez.cc)** — what I built, what broke, and what I got wrong. Some of the more useful ones:

- [The agent platform, described in one place](https://davidgomez.cc/devblog/an-agent-platform-in-one-place) — how a job gets dispatched, which model runs it, and what it has to prove
- [Letting the fleet choose which model runs each job](https://davidgomez.cc/devblog/letting-the-fleet-choose-the-model) — quota-aware routing, and two live failures that both exited zero
- [Getting a local model to follow an exact plan](https://davidgomez.cc/devblog/local-model-exact-plan) — 3/30 to 30/30, and why the middle number was progress in the wrong direction
- [Restoring a backup I had never actually restored](https://davidgomez.cc/devblog/restoring-a-backup-i-never-restored) — the archive was 1,471 bytes and perfectly valid

📍 Dallas–Fort Worth, TX
