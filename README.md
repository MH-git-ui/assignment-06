<div align="center">

<img src="public/logo.png" alt="FitLog logo" width="56" />

# **FitLog — Workout Library**

**Train with purpose. Track every set.**

A dark, focused gym companion: explore exercises, add them to today's workout plan, and keep track of your weekly training progress.

[Live Site](#-links) · [Features](#-features) · [Tech Stack](#%EF%B8%8F-technologies-used) · [Getting Started](#-getting-started)

</div>

---

## **📖 About**

FitLog is a responsive workout-library web application developed with **Next.js (App Router)** and **Tailwind CSS**, based on a Figma design. It retrieves twelve exercises from the FitLog API and presents them in an organized, browsable library. Users can view detailed information for each workout, add exercises to today's plan, or save them for later. The daily workout plan is limited to five unfinished exercises and is persisted in the browser for a seamless experience across page reloads.

## **✨ Features**

1. **Workout library** — Displays all 12 exercises retrieved from the API in a responsive 3 × 4 grid (3 → 2 → 1 columns). Each workout card includes an image, muscle-group tags, equipment details, and duration / calories / rating statistics. A skeleton loading interface with a spinner is displayed while workout data is being loaded.

2. **Detailed workout pages** — The `/workout/[id]` route provides a detailed view of each exercise, including a large visual, description, tags, a key-specifications panel covering equipment, difficulty, sets, reps, duration, calories, and rating, along with step-by-step instructions.

3. **Today's Plan & Saved lists** — Users can add exercises to "Today's Plan" or save them for later. Navbar badges update instantly, while toast notifications provide feedback for user actions. If an exercise is added more than once, an "already added" notification is displayed instead of creating a duplicate.

4. **Five-lift daily cap** — Today's Plan supports a maximum of 5 unfinished exercises at a time. Completing an exercise frees up a slot, allowing another workout to be added.

5. **My Plan dashboard** — Provides live Exercises / Minutes / Calories statistics along with Today's Plan / Saved tabs. Users can sort workouts by Duration, Calories, or Rating, mark exercises as completed, remove them, and view appropriate loading and empty states.

6. **Persistent data** — Today's Plan and Saved lists are stored using `localStorage` and synchronized across browser tabs, ensuring that workout selections remain available after page reloads.

7. **Robust routing** — Includes a custom 404 page for unknown routes and invalid workout IDs, an error boundary with retry functionality when the API request fails, and safe page reload handling across routes.

8. **Fully responsive** — The interface is optimized for mobile, tablet, and desktop screen sizes, with a collapsible navigation menu for mobile devices.

## **🛠️ Technologies Used**

| Technology | Purpose |
| --- | --- |

| [Next.js 16](https://nextjs.org/) (App Router, Turbopack) | Application framework, routing, server components, and streaming |

| [React 19](https://react.dev/) + React Compiler | User interface development and performance optimization |

| [TypeScript](https://www.typescriptlang.org/) | Static typing and improved code reliability |

| [Tailwind CSS v4](https://tailwindcss.com/) | Styling, responsive design, and Figma-based design tokens |

| [lucide-react](https://lucide.dev/) | Interface icons |

| [react-hot-toast](https://react-hot-toast.com/) | Toast notifications |

| `next/font` (Oswald + Inter) | Display and body typography |

| FitLog REST API | Workout and exercise data |

## **🗂️ Project Structure**

```text
├── public/                      # logo, banner, footer icon
└── src/
    ├── app/
    │   ├── page.tsx             # Home: hero + workout library
    │   ├── workout/[id]/        # Workout details page + loading skeleton
    │   ├── my-plan/             # My Plan dashboard
    │   ├── not-found.tsx        # Custom 404 page
    │   ├── error.tsx            # Error boundary
    │   └── layout.tsx            # Navbar, footer, fonts, and toaster
    ├── components/              # Navbar, Hero, WorkoutCard, PlanCard, SortSelect, …
    ├── context/PlanContext.tsx  # usePlan() hook
    └── lib/                     # API helpers, types, and localStorage-backed plan store

## 🔌 API

| Endpoint | Description |
| --- | --- |
| `GET https://api.abcz.workers.dev/api/fitlog` | All workouts |
| `GET https://api.abcz.workers.dev/api/fitlog/:id` | A single workout |

## 🚀 Getting Started

```bash
git clone https://github.com/MH-git-ui/assignment-06.git
cd Assignment_6
npm install
npm run dev        # http://localhost:3000
```

Production build:

```bash
npm run build
npm start
```

### Deploying to Vercel

1. Import the GitHub repo on [vercel.com/new](https://vercel.com/new) (framework preset: Next.js).
2. Keep the default settings and click **Deploy** — no environment variables are needed.

## 🔗 Links

- **Live Site:** https://assignment-06-gold.vercel.app/
- **GitHub Repository:** https://github.com/MH-git-ui/assignment-06

---

<div align="center">

© 2026 FitLog — Workout Library. Train hard, log honest.

</div>