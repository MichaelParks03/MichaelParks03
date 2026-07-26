# Michael Parks

A pet care business in Aledo, Texas takes its bookings through software I wrote. I am a Software Engineering student at the University of Texas at Arlington, graduating 2027, and most of what I write ends up deployed and used by someone who is not me.

I work as a Snapdragon Specialist at Qualcomm and build sites for small businesses on the side. I reach for React when a project earns it and plain JavaScript when it does not.

## Projects

**[BuildBetter](https://github.com/MichaelParks03/buildbetter)**
Paste your PC specs, pick a budget and a use case, get a bottleneck analysis and an upgrade plan you can actually buy. Scores 163 desktop CPUs and GPUs against a bundled performance tier table, falls back to a heuristic for parts it does not know, and respects CPU socket and DDR generation so it never suggests a part that will not fit. 27 tests cover the refusal cases: dead sockets, sidegrades, and budgets too small to matter. React, Vite, Tailwind, Netlify Functions, Node.

**[Mimi's Paws](https://mimispaws.com)**
Live booking site for a pet care business. Multi visit cart scheduling, pet intake forms, and an owner side accept or reject flow that hands the owner a ready to send confirmation. Three static files, no framework and no build step, which is the right size for a one person business. Supabase Postgres behind SECURITY DEFINER functions, Netlify.

**[Life Dashboard](https://github.com/MichaelParks03/life-dashboard)**
One dashboard for the things I actually track: finances, investments, meals, workouts, and calendar. Every module writes to a shared data layer, so a logged workout and a logged meal land in the same weekly view instead of in two apps that do not know about each other. Built because the alternative was six apps and no way to see a week at once. Ships as a single HTML file: vanilla JavaScript, CSS, no build step, no dependencies, runs fully offline.

## How I build

Security by architecture, not by discipline. Mimi's Paws runs row level security on every table with zero policies, so there is no client path to a raw table at all. Every read and write goes through a SECURITY DEFINER function. Staff passcodes are bcrypt hashed and throttled at eight failed attempts per IP per fifteen minutes. Life Dashboard is the opposite problem, no server to secure, so its offline guarantee is a Content Security Policy with `connect-src 'none'`: the app cannot make a network request even if I write a bug that tries.

Tests where the product decisions live. BuildBetter's 27 tests are named for behavior rather than functions: a maxed out build is never offered a downgrade, a CPU is never recommended when the exact model is unknown, a negative budget is rejected with a warning instead of quietly made positive.

I would rather a project be correct at the edges than look finished. BuildBetter's planner refuses to recommend an upgrade when the budget cannot buy a meaningful one, and refuses to name a CPU when it cannot verify the socket, because guessing wrong costs someone a motherboard.

## Tools

**Languages:** JavaScript, Python, Java, C, C++, SQL, Luau
**Frontend:** React, Vite, Tailwind CSS
**Backend:** Node, Express, Supabase, PostgreSQL
**Infrastructure:** Netlify, Git, Linux

## Background

Five custom PC builds and a stretch of hands on IT work are where BuildBetter came from. I also teach chess to kids and serve as Grand Scribe on my fraternity's executive committee, which has done more for my technical writing than any class has.

## Contact

[LinkedIn](https://www.linkedin.com/in/michael-parks03/) · [Email](mailto:msparks0831@gmail.com)

Open to software engineering internships and new grad roles.
