# Dev Portfolio CMS

A **premium developer portfolio** with a built-in admin panel — no database required.  
Built with Next.js, TypeScript, Tailwind CSS, and Framer Motion.

![Next.js](https://img.shields.io/badge/Next.js-16-black?logo=next.js)
![TypeScript](https://img.shields.io/badge/TypeScript-5-blue?logo=typescript)
![Tailwind](https://img.shields.io/badge/Tailwind-4-06B6D4?logo=tailwindcss)

## Features

- **Public Portfolio** — Home, Projects, Skills, About, Blog, Contact
- **Admin Panel** — Password-protected CMS with hidden access URL (security by obscurity + password)
- **GitHub Integration** — Auto-fetches your public repos, sorted by stars
- **Blog System** — Create, edit, and delete posts with Markdown support
- **Dark/Light Mode** — System detection + toggle + localStorage persistence
- **JSON Storage** — All content stored in `/data/*.json` files — no database needed
- **Framer Motion** — Smooth animations throughout
- **Mobile Responsive** — Looks great on all devices
- **Vercel Ready** — Deploy with zero configuration

## Quick Start

### 1. Clone & Install

```bash
git clone https://github.com/YOUR_USERNAME/dev-portfolio-cms.git
cd dev-portfolio-cms
npm install
```

### 2. Configure Environment

```bash
cp .env.example .env.local
```

Edit `.env.local`:

```env
ADMIN_PASSWORD=your_password
GITHUB_USERNAME=your_github_username
NEXT_PUBLIC_ADMIN_SECRET=your-secret-admin-path
```

**Note:** The admin panel is accessible at `/{NEXT_PUBLIC_ADMIN_SECRET}` instead of `/admin` for security. Direct `/admin` access is blocked.

### 3. Customize Content

Edit the JSON files in `/data/` to add your info:

| File | Content |
|------|---------|
| `data/site.json` | Name, title, hero text, social links, featured projects |
| `data/about.json` | About page content and timeline |
| `data/skills.json` | Skills grouped by category with proficiency levels |
| `data/blog.json` | Blog posts (or manage via admin panel) |

### 4. Add Resume

Place your resume file at `public/resume.pdf` (or update the path in `data/site.json`).

### 5. Run

```bash
npm run dev
```

Open [http://localhost:3000](http://localhost:3000)  
Admin panel: `http://localhost:3000/{your-secret-path}` (uses the value from `.env.local`)

## Deploy to Vercel

1. Push to GitHub
2. Import project on [vercel.com](https://vercel.com)
3. Add environment variables: `ADMIN_PASSWORD`, `GITHUB_USERNAME`, `NEXT_PUBLIC_ADMIN_SECRET`
4. Deploy — done!

## Project Structure

```
app/                    # Next.js App Router pages
  admin/                # Admin panel (dashboard, content, skills, blog, projects, settings)
  api/                  # API routes (auth, data CRUD, GitHub proxy)
  blog/[slug]/          # Dynamic blog post pages
  projects/             # GitHub projects page
  skills/               # Skills & technologies
  about/                # About with timeline
  contact/              # Contact & social links
components/             # Reusable UI components
lib/                    # Utilities (GitHub API, JSON DB, auth)
data/                   # JSON content files (your data lives here)
```

## Tech Stack

- **Framework:** Next.js 16 (App Router)
- **Language:** TypeScript (strict)
- **Styling:** Tailwind CSS 4
- **Animations:** Framer Motion
- **Icons:** React Icons
- **Markdown:** React Markdown
- **Deployment:** Vercel Serverless

## License

MIT — use it, fork it, make it yours.
