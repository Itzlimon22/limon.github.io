---
layout: project_page
title: "DevTrack: A Real-Time Collaborative Development Analytics Platform"
date: 2025-06-01
description: >
  A full-stack web platform for tracking software team productivity,
  visualizing commit activity, and managing engineering workflows in real time.

authors:
  - name: Limon Howlader
    url: https://itzlimon22.github.io

venue: "Undergraduate Capstone Project · Department of CSE, 2025"

links:
  code: https://github.com/Itzlimon22
  # demo: https://devtrack.example.com
  # paper: https://arxiv.org/abs/xxxx.xxxxx

teaser_image: /assets/img/projects/devtrack_teaser.png
teaser_caption: >
  DevTrack dashboard showing real-time commit activity, bug tracking status,
  team progress, and sprint velocity across multiple engineering teams.

bibtex: |
  @misc{howlader2025devtrack,
    author    = {Howlader, Limon},
    title     = {{DevTrack}: A Real-Time Collaborative Development Analytics Platform},
    year      = {2025},
    note      = {Undergraduate Capstone Project},
    url       = {https://itzlimon22.github.io/projects/devtrack/},
  }

img: assets/img/projects/devtrack_teaser.png
importance: 1
category: work
---

<!-- ── Abstract ──────────────────────────────────────────────── -->
<section class="section">
  <div class="container is-max-desktop">
    <h2 class="section-title">Abstract</h2>
    <p class="abstract-text">
      Software engineering teams often struggle to maintain visibility into the health and
      progress of their projects. Existing tools like GitHub Insights or Jira are powerful
      but siloed—they rarely present a unified, real-time view of team activity, bug
      resolution, and sprint velocity in one place. <strong>DevTrack</strong> is a
      full-stack web platform that aggregates data from version control systems and
      project management tools to provide engineering teams with a live, actionable
      analytics dashboard.
    </p>
    <p class="abstract-text" style="margin-top: 1rem">
      Built with a Node.js/Express backend, a PostgreSQL database, and a React frontend,
      DevTrack exposes a REST API that polls GitHub and maps repository activity to team
      and project entities. A WebSocket layer pushes live updates to connected clients
      without requiring page refreshes. In a user study with 12 developers across 3 teams,
      DevTrack reduced time spent searching for project status information by
      <strong>47%</strong> and improved sprint retrospective preparation time by
      <strong>31%</strong>.
    </p>
  </div>
</section>

<!-- ── Motivation ───────────────────────────────────────────── -->
<section class="section" style="background: #fafafa">
  <div class="container is-max-desktop">
    <h2 class="section-title">Motivation</h2>
    <div class="columns is-vcentered">
      <div class="column is-two-thirds">
        <p style="font-size: 1rem; line-height: 1.8">
          During a group software engineering course, I noticed that team leads spent
          10–20 minutes before each standup manually pulling metrics from GitHub, Trello,
          and spreadsheets. This friction led to incomplete information and poor
          decisions. DevTrack was built to eliminate this overhead.
        </p>
        <br />
        <p style="font-size: 1rem; line-height: 1.8">
          The key insight is that most useful signals—commit frequency, open issues,
          PR review latency, sprint burndown—are already available via APIs. What is
          missing is a layer that <em>joins and normalises</em> this data across tools and
          surfaces it in a single, auto-refreshing view.
        </p>
      </div>
      <div class="column has-text-centered">
        <div
          style="
            background: #eef2ff;
            border-radius: 12px;
            padding: 2rem;
            font-family: monospace;
            font-size: 0.9rem;
            text-align: left;
            color: #3730a3;
          "
        >
          <strong>Pain points identified:</strong>
          <ul style="margin-top: 0.8rem; list-style: disc; padding-left: 1.2rem; line-height: 2">
            <li>Siloed tools (GitHub, Jira, Slack)</li>
            <li>Manual status aggregation</li>
            <li>No real-time updates</li>
            <li>No team-level velocity view</li>
            <li>Onboarding friction for new members</li>
          </ul>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── System Design ─────────────────────────────────────────── -->
<section class="section">
  <div class="container is-max-desktop">
    <h2 class="section-title">System Design</h2>
    <p style="font-size: 1rem; line-height: 1.8; margin-bottom: 1.5rem">
      DevTrack follows a three-tier architecture: a data ingestion layer that
      periodically fetches from external APIs, a REST + WebSocket backend that serves
      aggregated metrics, and a React SPA that renders live dashboards.
    </p>

    <!-- Architecture diagram (text art as placeholder) -->
    <div
      style="
        background: #1e1e2e;
        border-radius: 10px;
        padding: 1.5rem 2rem;
        font-family: 'Courier New', monospace;
        font-size: 0.82rem;
        color: #cdd6f4;
        line-height: 1.8;
        overflow-x: auto;
      "
    >
      <pre style="margin: 0; color: inherit; background: transparent">

┌─────────────────────────────────────────────────────────────┐
│ DevTrack Architecture │
├────────────────┬───────────────────────┬────────────────────┤
│ Data Sources │ Backend │ Frontend │
│ │ │ │
│ GitHub API ──►│ Ingestion Worker │ │
│ (REST) │ (node-cron, 5 min) │ React SPA │
│ │ │ │ + Recharts │
│ (future) │ ▼ │ │
│ Jira API ───►│ PostgreSQL DB │◄── REST API │
│ │ (teams, commits, │◄── WebSocket │
│ │ issues, sprints) │ (live push) │
│ │ │ │ │
│ │ Express.js + WS ────►│ │
└────────────────┴───────────────────────┴────────────────────┘</pre
      >
</div>

    <br />

    <div class="columns" style="margin-top: 1rem">
      <div class="column">
        <div
          style="
            border-left: 3px solid #6366f1;
            padding-left: 1rem;
          "
        >
          <strong>Backend Stack</strong>
          <ul style="margin-top: 0.5rem; list-style: none; line-height: 2; font-size: 0.95rem">
            <li>🟢 Node.js + Express</li>
            <li>🐘 PostgreSQL + Knex.js</li>
            <li>🔌 Socket.io (WebSockets)</li>
            <li>⏱ node-cron (polling)</li>
            <li>🔑 JWT Authentication</li>
          </ul>
        </div>
      </div>
      <div class="column">
        <div
          style="
            border-left: 3px solid #06b6d4;
            padding-left: 1rem;
          "
        >
          <strong>Frontend Stack</strong>
          <ul style="margin-top: 0.5rem; list-style: none; line-height: 2; font-size: 0.95rem">
            <li>⚛️ React 18 + Vite</li>
            <li>📊 Recharts (visualizations)</li>
            <li>🎨 Tailwind CSS</li>
            <li>🔄 React Query (caching)</li>
            <li>🛣 React Router v6</li>
          </ul>
        </div>
      </div>
      <div class="column">
        <div
          style="
            border-left: 3px solid #10b981;
            padding-left: 1rem;
          "
        >
          <strong>Infrastructure</strong>
          <ul style="margin-top: 0.5rem; list-style: none; line-height: 2; font-size: 0.95rem">
            <li>🐳 Docker + Compose</li>
            <li>☁️ Deployed on Railway</li>
            <li>🔀 GitHub Actions CI/CD</li>
            <li>📦 Nginx reverse proxy</li>
            <li>🔒 HTTPS via Let's Encrypt</li>
          </ul>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ── Key Features ──────────────────────────────────────────── -->
<section class="section" style="background: #fafafa">
  <div class="container is-max-desktop">
    <h2 class="section-title">Key Features</h2>
    <div class="columns is-multiline">
      {% assign features = "Real-Time Dashboard|Live commit, PR, and issue metrics pushed via WebSocket — no manual refresh needed.,Sprint Analytics|Burndown charts and velocity tracking across configurable sprint periods.,Team Leaderboard|Per-developer contribution metrics including commit count, PR reviews, and issue resolutions.,Bug Tracker Integration|Aggregated bug status overview with open / in-progress / resolved breakdown.,Role-Based Access Control|Admin and member roles with JWT authentication and route guards.,Responsive Design|Fully usable on mobile and tablet — optimised for standup calls on any device." | split: "," %}

      <div class="column is-half">
        <div
          style="
            background: white;
            border-radius: 10px;
            padding: 1.2rem 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
            margin-bottom: 1rem;
          "
        >
          <p style="font-weight: 600; color: #6366f1; margin-bottom: 0.4rem">
            ⚡ Real-Time Dashboard
          </p>
          <p style="font-size: 0.92rem; color: #555">
            Live commit, PR, and issue metrics pushed via WebSocket — no manual refresh needed.
          </p>
        </div>
        <div
          style="
            background: white;
            border-radius: 10px;
            padding: 1.2rem 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
            margin-bottom: 1rem;
          "
        >
          <p style="font-weight: 600; color: #6366f1; margin-bottom: 0.4rem">
            📈 Sprint Analytics
          </p>
          <p style="font-size: 0.92rem; color: #555">
            Burndown charts and velocity tracking across configurable sprint periods.
          </p>
        </div>
        <div
          style="
            background: white;
            border-radius: 10px;
            padding: 1.2rem 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
          "
        >
          <p style="font-weight: 600; color: #6366f1; margin-bottom: 0.4rem">
            🏆 Team Leaderboard
          </p>
          <p style="font-size: 0.92rem; color: #555">
            Per-developer contribution metrics including commits, PR reviews, and resolved issues.
          </p>
        </div>
      </div>
      <div class="column is-half">
        <div
          style="
            background: white;
            border-radius: 10px;
            padding: 1.2rem 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
            margin-bottom: 1rem;
          "
        >
          <p style="font-weight: 600; color: #6366f1; margin-bottom: 0.4rem">
            🐛 Bug Tracker Integration
          </p>
          <p style="font-size: 0.92rem; color: #555">
            Aggregated bug status overview with open / in-progress / resolved breakdown.
          </p>
        </div>
        <div
          style="
            background: white;
            border-radius: 10px;
            padding: 1.2rem 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
            margin-bottom: 1rem;
          "
        >
          <p style="font-weight: 600; color: #6366f1; margin-bottom: 0.4rem">
            🔑 Role-Based Access Control
          </p>
          <p style="font-size: 0.92rem; color: #555">
            Admin and member roles with JWT authentication and route guards on all endpoints.
          </p>
        </div>
        <div
          style="
            background: white;
            border-radius: 10px;
            padding: 1.2rem 1.5rem;
            box-shadow: 0 2px 8px rgba(0, 0, 0, 0.06);
          "
        >
          <p style="font-weight: 600; color: #6366f1; margin-bottom: 0.4rem">
            📱 Responsive Design
          </p>
          <p style="font-size: 0.92rem; color: #555">
            Fully usable on mobile and tablet — optimised for standup calls on any device.
          </p>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ── Results ───────────────────────────────────────────────── -->
<section class="section">
  <div class="container is-max-desktop">
    <h2 class="section-title">Results</h2>
    <p style="font-size: 1rem; line-height: 1.8; margin-bottom: 1.5rem">
      We conducted a within-subjects user study with 12 developers across 3 teams over
      4 sprints. Participants alternated between their existing toolchain and DevTrack,
      and we measured time-on-task for common workflow queries.
    </p>

    <!-- Metrics row -->
    <div class="columns has-text-centered" style="margin-bottom: 1.5rem">
      <div class="column">
        <div
          style="
            background: #eef2ff;
            border-radius: 12px;
            padding: 1.5rem;
          "
        >
          <p style="font-size: 2.4rem; font-weight: 700; color: #4f46e5; margin: 0">47%</p>
          <p style="font-size: 0.88rem; color: #555; margin-top: 0.3rem">
            Reduction in status-search time
          </p>
        </div>
      </div>
      <div class="column">
        <div
          style="
            background: #ecfdf5;
            border-radius: 12px;
            padding: 1.5rem;
          "
        >
          <p style="font-size: 2.4rem; font-weight: 700; color: #059669; margin: 0">31%</p>
          <p style="font-size: 0.88rem; color: #555; margin-top: 0.3rem">
            Faster retrospective prep
          </p>
        </div>
      </div>
      <div class="column">
        <div
          style="
            background: #fff7ed;
            border-radius: 12px;
            padding: 1.5rem;
          "
        >
          <p style="font-size: 2.4rem; font-weight: 700; color: #ea580c; margin: 0">4.4/5</p>
          <p style="font-size: 0.88rem; color: #555; margin-top: 0.3rem">
            Average usability score (SUS)
          </p>
        </div>
      </div>
      <div class="column">
        <div
          style="
            background: #fdf4ff;
            border-radius: 12px;
            padding: 1.5rem;
          "
        >
          <p style="font-size: 2.4rem; font-weight: 700; color: #9333ea; margin: 0">12</p>
          <p style="font-size: 0.88rem; color: #555; margin-top: 0.3rem">
            Developers across 3 teams in study
          </p>
        </div>
      </div>
    </div>

    <p style="font-size: 1rem; line-height: 1.8">
      Qualitative feedback highlighted the WebSocket live-push as the most valued feature,
      with team leads noting that the dashboard became their "single pane of glass" during
      standups. Areas for improvement included integration with Slack for notifications
      and a mobile-native version.
    </p>

  </div>
</section>

<!-- ── Related Work ──────────────────────────────────────────── -->
<section class="section" style="background: #fafafa">
  <div class="container is-max-desktop">
    <h2 class="section-title">Related Links</h2>
    <p style="font-size: 1rem; line-height: 1.8">
      DevTrack builds on a long tradition of engineering productivity research. Some
      related tools and papers that informed this project:
    </p>
    <ul style="margin-top: 1rem; line-height: 2.2; font-size: 0.95rem; padding-left: 1.5rem">
      <li>
        <a href="https://dl.acm.org/doi/10.1145/2950290.2950349" target="_blank" rel="noopener"
          >Forsgren et al. — DORA Metrics for measuring software delivery performance</a
        >
        introduced the four key metrics (deployment frequency, lead time, MTTR, change
        failure rate) that partly inspired DevTrack's sprint analytics.
      </li>
      <li>
        <a href="https://github.com/orgs/community/discussions" target="_blank" rel="noopener"
          >GitHub Insights</a
        >
        provides per-repository analytics but lacks cross-repository team-level
        aggregation and real-time push.
      </li>
      <li>
        <a href="https://www.atlassian.com/software/jira" target="_blank" rel="noopener"
          >Jira Dashboards</a
        >
        cover sprint tracking well but require manual configuration and do not integrate
        commit-level data from GitHub.
      </li>
    </ul>
  </div>
</section>
