# Dipendra Sharma
I'm a backend-leaned developer from Nepal currently studying at Chitkara University. I build systems that survive real traffic, not just demo day — and I learn by shipping, not by watching tutorials.

## How I think
I don't chase perfect systems. I chase systems that know how to break gracefully.

A **fault** is one component misbehaving — a PostgreSQL connection pool leaking, a Render instance cold-starting for 50 seconds, a cron job firing twice because you forgot to guard it. A **failure** is the whole platform collapsing because nobody asked "what if?" I design for the first so I never have to explain the second.

Scalability isn't a badge you earn once. It's the question you keep asking — what happens when this grows 10x? I load-tested my job portal at 100 concurrent users when I barely had 5. Not because I needed to, but because the bottleneck should surprise you in data, not in production.

Even AWS doesn't build 100% fault-tolerant systems. They build systems that know which faults matter. That's the standard I hold my work to.

---

## What I've built

### Yeti Jobs — A production job portal
*Backend · DevOps · Database Architecture · System Design*

Built this solo, from the database schema up. 50+ REST APIs, JWT auth with RBAC across three user roles, and a PostgreSQL schema tuned with composite and GIN indexes that took search latency from 7ms down to 0.9ms.

The backend is strict MVC — controllers, services, models, thin routes. I wrote the migration system as 14 numbered SQL files with dependency ordering (extensions → enums → tables → indexes → triggers) so the schema evolves cleanly. Every table has database-level validation — even if someone bypasses the client and server, the data stays clean.

I didn't just ship features. I tried to break it:
- Load-tested with Apache Bench: 67 req/sec sustained, 100 concurrent users, zero failures
- Multi-stage Docker builds shrank the backend image from 1.99GB to 520MB
- Caught a PostgreSQL pool leak before it hit production — learned that `Pool` queries must be released or transactions silently fail
- Built a cron job that keeps the free-tier Render instance alive, taking cold starts from 50+ seconds to under 2s — 99.5% uptime over 3 months
- 28+ integration tests with Jest and Supertest covering the critical routes

Also shipped an AI resume scorer using Grok + pdf-parse, a notification system for followed companies, and full Swagger docs.

**Tech:** Node.js · Express · PostgreSQL · Prisma · Docker · Jest · Supabase · Render

---

### StateFlow — A Jira-inspired task manager
*Frontend · State Management · Performance · UX*

Drag-and-drop kanban boards with dark mode, keyboard shortcuts, and full responsive layout. The core is a custom undo/redo engine I built with three-stack state history — past, present, future — handling 50+ sequential operations at O(1) without lag.

I used React Context API with localStorage persistence, but added hydration safety checks so refreshing the browser never corrupts state. For the drag-and-drop, I optimized rendering with strategic memoization and ref-based callbacks to keep 60fps even with 50+ task cards mounted. Built client-side CSV/JSON export with Blob generation — zero server dependency.

**Tech:** Next.js · React · TypeScript · Tailwind CSS · DnD Kit · Chart.js

---

### HomeFinder — An Airbnb-style rental platform
*Full-stack · Authentication · Cloud Integration · Deployment*

My first serious backend project. MVC pattern with Express and MongoDB. Session-based auth using Passport.js with salted+bcrypt hashing and a MongoDB-backed session store. I learned the hard way that MemoryStore leaks in production — switched to connect-mongo before deploying.

Built an image upload pipeline with Cloudinary (multer parses, Cloudinary stores, database keeps the reference) and integrated MapTiler for geocoding — type an address, get a live map marker. Deployed on Render with environment isolation.

**Tech:** Node.js · Express · MongoDB · Passport.js · Cloudinary · MapTiler · EJS

---

## Problem solving

I don't collect LeetCode numbers for the sake of it. I solve problems because every hard question teaches me to see the shape of a solution before I write code.

- **325+ problems solved** on LeetCode (peak rating 1570, 365-Day Badge)
- **Active on Codeforces** — currently solving A & B level problems, building up contest stamina
- Languages: **C++** (primary for CP), JavaScript, TypeScript, SQL

---

## Currently exploring

- **Next.js as a full-stack framework** — not just frontend, but wiring APIs directly in the app layer with TypeScript
- **Redis** — not just "caching," but persistence models, rate limiting internals, and why hash sets perform differently under load
- **AWS** — hands-on with S3, EC2, IAM, and Lambda
- **Clean code as a discipline** — writing code so clear that anyone from junior to senior can read it without asking questions

---

## Highlights

- 🥇 **Winner — Code-a-Thon 7.0** (university hackathon, cash prize)
- 🌟 **Shortlisted for Round 2 — MyPolaris Fellowship 2026** (selected from 10,000+ students across 300+ cities)
- 🌟 **Selected Contributor — GirlScript Summer of Code 2026** (national open-source program)
- 📚 **CEED Member** — Entrepreneurship Program, Chitkara University

---

## Note

I don't hit every topic above every single day — time is tight. But I touch something meaningful at least biweekly. Consistency over intensity.

**Open to backend, full-stack, SDE, and DevOps internships across India.**

📫 **hello@dipsharma.me** · [LinkedIn](https://linkedin.com/in/tech-dipesh) · [Portfolio](https://dipsharma.me)

## My Recent Projects:
<div><a href="https://github.com/tech-dipesh/yeti-jobs/">Yeti Jobs</a></div
<div><a href="https://state-flows.vercel.app">State Flows Project Management</a></div>
<div><a href="https://mega-project-listing.onrender.com">Home Finder</a></div>
<div><a href="https://tech-dipesh.github.io/Beat-Bridge">Beat Bridge: Music Player</a></div>
<div><a href="https://dipsharma.me">Personal Website</a></div>


## 🌐 Socials:
<p align="center"> <a href="https://linkedin.com/in/tech-dipesh"> <img src="https://skillicons.dev/icons?i=linkedin" height="25"/> </a> &nbsp; <a href="https://stackoverflow.com/users/29766757/dipesh"> <img src="https://skillicons.dev/icons?i=stackoverflow" height="25"/> </a> &nbsp; <a href="https://www.leetcode.com/tech-dipesh"> <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" height="25"/> </a> &nbsp; <a href="https://discord.com/users/973585874027688016"> <img src="https://skillicons.dev/icons?i=discord" height="25"/> </a> &nbsp; <a href="https://x.com/tec_dipesh"> <img src="https://skillicons.dev/icons?i=twitter" height="25"/> </a> </p>

<h3 align="left">Languages and Tools:</h3>
<h4>Scripting:</h4>
<img src="https://skillicons.dev/icons?i=js,ts,c,cpp,java">
<h4>Backend:</h4>
<img src="https://skillicons.dev/icons?i=nodejs,express">
<h4>Frontend Framework:</h4>
<img src="https://skillicons.dev/icons?i=nextjs,react,tailwind,redux">
<h4>DataBase:</h4>
<img src="https://skillicons.dev/icons?i=postgres,mongodb,mysql,supabase" alt="mongodb">
<h4>Devops & Tools:</h4>
<img src="https://skillicons.dev/icons?i=docker,neovim,linux,git,vite,npm,vercel,babel,vscode,postman,regex,vim">
  
# 📊 GitHub Stats


![Most Used Languages](https://github-readme-stats.shion.dev/api/top-langs/?username=tech-dipesh&theme=radical&hide_border=false&include_all_commits=true&count_private=true)

![GitHub Stats](https://github-readme-stats.shion.dev/api?username=tech-dipesh&hide_border=false&include_all_commits=true&count_private=true)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=tech-dipesh&theme=dark&hide_border=false)

![View Count](https://komarev.com/ghpvc/?username=tech-dipesh&color=blue)



