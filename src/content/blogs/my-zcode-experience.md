---
title: "My ZCode Experience"
date: '2026-09-06'
slug: my-zcode-experience
---

ZCode had a "free weekend" last week where they gave away 300 million tokens of GLM 5.3 Flash, so I thought it would be a good opportunity to try it out for free (the model and the software).

For starters, the "300 million tokens" thing was a bit misleading, as it counted both cache hit *and* cache miss tokens, rather than just the tokens actually used. This meant that the actual number of tokens I could use was significantly lower than 300 million, but you know it's free stuff so I'm not complaining too much.

As for the actual software, it was fine I guess.

![RAM usage](/blogs/my-zcode-experience/ram.webp)

It's an Electron-based application, so it was using nearly 2 GB of RAM while idle, but you get used to Electron's bullshit over time (and you also kinda forget about ZCode when you realise Windows 11 is using nearly 16 GB of RAM just to not let me move my taskbar and break custom cursors in the last update. Thanks Microsoft, fuck you).

![Proc Mon](/blogs/my-zcode-experience/procmon.webp)

There were random bits here and there in Mandarin that weren't translated, which was a bit jarring, and they forgot to disable the application menu in the process monitor.

My three biggest problems, however, were with security, cache hit honesty, and a lack of QA.

![Cache](/blogs/my-zcode-experience/cache.webp)

First, cache hit. I heard of ZCode initially from a Twitter post by the co-founder of OpenCode, showing ZCode with an extremely high cache hit rate. However, if you look at the actual chat logs (which are easily accessible, by the way; I'll talk about them more in the security section), you'll notice ZCode injects a system message reminding the agent to use the to-do list tool every 5-6 tool calls while the agent is running, which massively inflates the cache hit rate.

![Credentials](/blogs/my-zcode-experience/creds.webp)

Next, and arguably more concerning, was the security. Keep in mind, ZCode isn't made by some random hobbyist; it's made by Z.ai themselves, so it more than surprises me that the brilliant minds at Z.ai decided that the best way to store all of your API keys and their internal data is in a JSON file.

And these aren't just *your* LLM/MCP API keys, but also internal base URLs and API keys for Z.ai's own services (which, combined with the fact that they forgot to disable Dev Tools, means you could theoretically reverse-engineer it).

![Trajectory](/blogs/my-zcode-experience/traj.webp)

Finally, the QA, or I should say the lack of it. You'll see randomly untranslated bits and inconsistent modal styles, but with the "model trajectory" feature specifically, it was amazingly in your face. I already assumed ZCode would be largely, if not entirely, vibe-coded, but they didn't even try to make the trajectory panel look decent.

Overall, my experience with ZCode was a pretty mixed bag. I would probably still recommend it to other people, but with a fair share of warnings about its quirks and security concerns.
