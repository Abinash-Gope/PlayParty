# 👋 Hi, I'm Abinash!

A passionate Full-Stack Developer dedicated to building high-performance, real-time web applications with rich user experiences. I specialize in modern JavaScript/TypeScript ecosystems, real-time sync engines, and sleek interface design.

---

## 🚀 Featured Project: 🎉 PlayParty
> **A Real-Time Collaborative Video Watching Application**
> 
> *Watch YouTube videos with friends in perfectly synchronized rooms, chat in real-time, and manage shared video queues.*

<div align="center">
  <br />
  
  [![React](https://img.shields.io/badge/React-20232A?style=for-the-badge&logo=react&logoColor=61DAFB)](https://react.dev/)
  [![Vite](https://img.shields.io/badge/Vite-B73BFE?style=for-the-badge&logo=vite&logoColor=FFD62E)](https://vitejs.dev/)
  [![TypeScript](https://img.shields.io/badge/TypeScript-007ACC?style=for-the-badge&logo=typescript&logoColor=white)](https://www.typescriptlang.org/)
  [![Supabase](https://img.shields.io/badge/Supabase-181818?style=for-the-badge&logo=supabase&logoColor=3ECF8E)](https://supabase.com/)
  [![Tailwind CSS](https://img.shields.io/badge/Tailwind_CSS-38B2AC?style=for-the-badge&logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

  <br /><br />

  [🎮 Launch Live Application](https://playparty.vercel.app) • [📄 Project Showcase & Source](https://github.com/Abinash-Gope/PlayParty)

  <br />
</div>

### 🛠️ Tech Stack & Architecture
* **Frontend**: `React 18` + `Vite` for sub-second hot module reloading.
* **Language**: `TypeScript` ensuring strict type-safety across client-side logic.
* **Styling**: `Tailwind CSS` & `shadcn/ui` for a premium, accessible component architecture.
* **State Management**: `React Query` & `React Context API`.
* **Backend & Real-Time Sync**: `Supabase Realtime` (WebSockets) for synchronizing room state, active presence, and chat logs.
* **Media Integration**: `YouTube IFrame API` wrapped in custom synchronization hooks.

### 🌐 System Architecture
The following flowchart illustrates how the synchronization engine connects multiple clients, Supabase WebSockets, database stores, and external APIs to achieve low-latency synchronization:

```mermaid
graph TD
    subgraph ClientApp ["Client Application"]
        ClientA["💻 Host Client (Abinash)"]
        ClientB["📱 Peer Client (Friend)"]
    end

    subgraph Backend ["Backend Infrastructure"]
        DB["🗄️ PostgreSQL Database"]
        RealtimeWebSocket["⚡ Supabase Realtime Hub (WebSockets)"]
    end

    subgraph External ["External APIs & Services"]
        YT["📺 YouTube IFrame API"]
        AI["🤖 Gemini AI Rec Engine"]
    end

    ClientA <-->|"1. WebSocket Handshake"| RealtimeWebSocket
    ClientB <-->|"1. WebSocket Handshake"| RealtimeWebSocket

    ClientA -->|"2. Broadcast Sync State - Play, Pause, Seek"| RealtimeWebSocket
    RealtimeWebSocket -->|"3. Propagate Sync State"| ClientB

    ClientA <-->|"4. Read & Write Playlist Queue"| DB
    ClientB <-->|"4. Read & Write Playlist Queue"| DB

    ClientA <-->|"5. Render Video Player"| YT
    ClientB <-->|"5. Render Video Player"| YT

    ClientA -->|"6. Request Video Recs"| AI
    DB -->|"Fetch Room Context"| AI
```

### 📂 Codebase Directory Tree
The codebase is structured to enforce strong separation of concerns, housing custom sync hooks, reusable ui elements, and real-time state managers:

```text
watch-party-hub/
├── supabase/                    # Supabase Database Migrations, Functions & Schema setups
├── public/                      # Static assets, backgrounds & branding resources
└── src/
    ├── components/              # Interactive UI Components
    │   ├── ui/                  # Primitive shadcn/ui components (Buttons, Dialogs, Inputs)
    │   ├── AIChatbot.tsx        # Real-time room AI assistant chatbot
    │   ├── ReactionBar.tsx      # Emoji bar for live room interaction
    │   ├── FloatingReactions.tsx# Floating screen micro-animations
    │   └── VideoQueuePanel.tsx  # Dynamic collaborative queue manager
    ├── hooks/                   # Custom Hooks for player hooks & backend APIs
    │   ├── useYouTubePlayer.ts  # Handlers for YouTube Player API integration
    │   ├── usePresence.ts       # Peer presence tracking engine
    │   ├── useRoom.ts           # Room state syncing & WebSocket orchestration
    │   └── useVideoReactions.ts # Reaction syncing logic
    ├── pages/                   # Views & Routing Handlers
    │   ├── WatchRoom.tsx        # Main theater room viewport
    │   ├── ExploreRooms.tsx     # Active public rooms lobby
    │   └── AIRecommendations.tsx# AI recommendations screen
    ├── lib/                     # Client configuration setups (e.g. supabaseClient)
    ├── App.tsx                  # Main router setup & layout configurations
    └── main.tsx                 # Bootstrap React mount endpoint
```

### ✨ Key Technical Features & Challenges Solved
1. **Real-time Playback Sync**: Developed a custom reconciliation loop inside `src/hooks/useYouTubePlayer.ts` that checks and matches client drift. When a user seeks or pauses, the state broadcasts through WebSockets, synchronizing other clients in under 100ms.
2. **Dynamic Peer Presence**: Utilized Supabase Presence tracking to manage active users, updating the roster live and triggering animated entry alerts on member join.
3. **Collaborative Queue Reconciliation**: Designed an optimistic UI update flow where users can search and queue videos instantly without wait lag. Client changes auto-resolve with PostgreSQL queue states in the background.

---

## 🛠️ Skills & Technologies

| Category | Technologies |
| :--- | :--- |
| **Frontend** | React, TypeScript, Next.js, Vite, HTML5, CSS3, Tailwind CSS, shadcn/ui |
| **Backend & Databases** | Node.js, Express, Supabase, PostgreSQL, REST APIs, WebSockets |
| **Tools & Devops** | Git & GitHub, npm/bun, Vercel, Netlify, Docker |

---

## 📈 GitHub Activity & Profile Summary

<div align="center">
  <a href="https://github.com/Abinash-Gope">
    <img src="https://github-readme-stats.vercel.app/api?username=Abinash-Gope&show_icons=true&theme=dark" alt="Abinash's GitHub Stats" width="49%" />
    <img src="https://github-readme-stats.vercel.app/api/top-langs/?username=Abinash-Gope&layout=compact&theme=dark" alt="Top Languages" width="49%" />
  </a>
</div>
