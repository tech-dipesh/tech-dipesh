# Dipendra Sharma

Backend-leaned developer from Nepal, studying at Chitkara University Baddi, India. I build systems that survive real traffic — and i love to build a cool things. Which also help me to learn by shipping code.

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

### Daigo — A peer-to-peer commute marketplace
*Backend · Real-Time Systems · Geospatial · Distributed Architecture*

A two-sided marketplace where riders post commute requests and drivers accept them in real time. Price is agreed before the trip. When no single driver covers the full route, the system chains two drivers through one relay transfer — structurally closer to multi-leg flight search than a typical carpool clone.

Real engineering problems I'm solving here:

- **Cold-start bootstrapping** — a marketplace with no drivers has no value for riders. Solved with circle-based matching (college/office email domains get priority) before opening to the general public, plus a notify-me waitlist.
- **Geospatial matching** — Prisma has no native PostGIS support, so route overlap uses raw `$queryRaw` SQL. Calculates detour limits and suggests meeting points from lat/long proximity. Every result uses an explicit custom generic type, never `any`.
- **Cross-instance real-time** — Vercel's serverless functions don't share memory. A WebSocket message from one function can't reach a user connected to another. Redis pub/sub solves it: match events publish to a channel, every instance forwards to its connected clients. 75-second countdown, first-accept-wins enforced via Prisma transactions.
- **Pricing correctness** — per-zone multipliers, time-of-day bands, and demand multipliers. Two hard caps (per-km and absolute) checked against the *rounded* value, not the raw float — or a rounded price can land just over the cap.
- **Failure-resistant backend** — idempotency keys for payment retries (a dropped connection can't duplicate a charge), webhook verification, atomic seat release (two riders can't book the same seat), and refresh token rotation with revocation.
- **Signed-URL uploads** — server validates type and size, then the client uploads directly to Supabase storage. Backend never touches the file.
- **Background jobs** — CSV exports, document verification, and alerts run through Upstash QStash instead of blocking API responses.

Built entirely on free-tier infrastructure — Next.js on Vercel, Upstash Redis, Stadia Maps, Brevo for email, Razorpay in test mode. Every tool has a verified free tier, which forces architectural decisions a bigger budget would let you avoid.

**Tech:** Next.js · TypeScript · PostgreSQL + PostGIS · Prisma · Redis · QStash · Stadia Maps · Razorpay

---

## Problem solving
- **300+ problems solved** on LeetCode (peak rating 1570, 365-Day Badge, 100-Day Badge 2026)
- **Active on Codeforces** — solving A & B level problems, building contest stamina
- Languages: **C++** (primary for CP), JavaScript, TypeScript, SQL

---

## Currently exploring

- **Computer Foundation (Revision)** — We're not a robot to once we study we are always perfect we always need a revision/Multiple Practice
- **Redis internals** — persistence models, rate limiting, why hash sets behave differently under load
- **AI Infrastructure** — Ai is the Future, i've to be ready for that
- **Clean code as a discipline** — writing code so clear anyone from junior to senior can read it without asking

---

## Highlights
- 🥇 **Winner — Code-a-Thon 7.0** (university hackathon, cash prize)
- 🌟 **Shortlisted for Round 2 — Polaris Fellowship 2026** (selected from 10,000+ students across 300+ cities)
- 🌟 **Selected Contributor — GirlScript Summer of Code 2026** (national open-source program)
- 📚 **CEED Member** — Entrepreneurship Program, Chitkara University

---

## Note
I don't hit every topic above every single day — time is tight. But I touch something meaningful at least biweekly. Consistency over intensity.

**Open to backend, full-stack, SDE, and DevOps internships across India.**
📫 **hello@dipsharma.me** · [LinkedIn](https://linkedin.com/in/tech-dipesh) · [Portfolio](https://dipsharma.me)

## My Recent Projects:
<div><a href="https://yeti-jobs.vercel.app">Yeti Jobs</a></div
<div><a href="https://github.com/tech-dipesh">Daigo</a></div
<div><a href="https://state-flows.vercel.app">State Flows Project Management</a></div>
<div><a href="https://tech-dipesh.github.io/Beat-Bridge">Beat Bridge: Music Player</a></div>
<div><a href="https://dipsharma.me">Personal Website</a></div>


## 🌐 Socials:
<p align="center"> <a href="https://linkedin.com/in/tech-dipesh"> <img src="https://skillicons.dev/icons?i=linkedin" height="25"/> </a> &nbsp; <a href="https://stackoverflow.com/users/29766757/dipesh"> <img src="https://skillicons.dev/icons?i=stackoverflow" height="25"/> </a> &nbsp; <a href="https://www.leetcode.com/tech-dipesh"> <img src="https://raw.githubusercontent.com/rahuldkjain/github-profile-readme-generator/master/src/images/icons/Social/leet-code.svg" height="25"/> </a> &nbsp; <a href="https://discord.com/users/973585874027688016"> <img src="https://skillicons.dev/icons?i=discord" height="25"/> </a> &nbsp; <a href="https://x.com/tec_dipesh"> <img src="https://skillicons.dev/icons?i=twitter" height="25"/> </a> </p>

<h3 align="left">Languages and Tools:</h3>
<h4>Scripting:</h4>
<img src="https://skillicons.dev/icons?i=js,ts,c,cpp,java" alt="Scripting">
<h4>Backend:</h4>
<img src="https://skillicons.dev/icons?i=nodejs,express" alt="Backend">
<h4>Frontend Framework:</h4>
<img src="https://skillicons.dev/icons?i=nextjs,react,tailwind,redux" alt="Frontend">
<h4>DataBase:</h4>
<img src="https://skillicons.dev/icons?i=postgres,mongodb,mysql,supabase" alt="mongodb">
<h4>Devops & Tools:</h4>
<img src="https://skillicons.dev/icons?i=docker,neovim,linux,git,npm,vscode,bun,regex,vim,pnpm" alt="devops \& tools">
  
# 📊 GitHub Stats

![Most Used Languages](https://github-readme-stats.shion.dev/api/top-langs/?username=tech-dipesh&theme=radical&hide_border=false&include_all_commits=true&count_private=true)

![GitHub Stats](https://github-readme-stats.shion.dev/api?username=tech-dipesh&hide_border=false&include_all_commits=true&count_private=true)

![GitHub Streak](https://github-readme-streak-stats.herokuapp.com/?user=tech-dipesh&theme=dark&hide_border=false)

![View Count](https://komarev.com/ghpvc/?username=tech-dipesh&color=blue)



