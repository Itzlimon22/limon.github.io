---
layout: project_page
title: "DevTrack: Real-Time Collaborative Development Analytics"
date: 2025-06-01
description: >
  A full-stack web platform for tracking software team productivity,
  visualizing commit activity, and managing engineering workflows in real time.

authors:
  - name: Limon Howlader
    url: https://itzlimon22.github.io

venue: "Undergraduate Capstone Project · Department of CSE · 2025"

related_projects:
  - title: DevTrack — Dev Analytics Platform
    url: /projects/devtrack/
  # - title: Another Project (Coming Soon)
  #   url: /projects/another/

links:
  code: https://github.com/Itzlimon22
  # paper: https://arxiv.org/abs/xxxx
  # arxiv: https://arxiv.org/abs/xxxx
  # video: https://www.youtube.com/watch?v=xxxx
  # demo: https://devtrack.example.com
  # poster: /assets/pdf/devtrack_poster.pdf

teaser_image: /assets/img/projects/devtrack_teaser.png
teaser_caption: >
  DevTrack dashboard — real-time commit activity, bug tracking, team progress,
  and sprint velocity aggregated across engineering teams.

bibtex: |
  @misc{howlader2025devtrack,
    author    = {Howlader, Limon},
    title     = {{DevTrack}: Real-Time Collaborative Development Analytics},
    year      = {2025},
    note      = {Undergraduate Capstone Project, Department of CSE},
    url       = {https://itzlimon22.github.io/projects/devtrack/},
  }

img: assets/img/projects/devtrack_teaser.png
importance: 1
category: work
---

<!-- ── Abstract ──────────────────────────────────────────────── -->
<section class="section">
  <div class="container is-max-desktop">
    <div class="columns is-centered">
      <div class="column is-four-fifths">
        <h2 class="section-heading has-text-centered">Abstract</h2>
        <div class="content has-text-justified abstract-body">
          <p>
            Software engineering teams often struggle to maintain visibility into project
            health across multiple disconnected tools. Existing solutions like GitHub
            Insights and Jira are powerful in isolation but rarely present a unified,
            real-time view of commit activity, bug resolution, and sprint velocity.
            <strong>DevTrack</strong> is a full-stack web platform that aggregates data
            from version control and project management systems to provide engineering
            teams with a live, actionable dashboard.
          </p>
          <p>
            Built with a Node.js/Express backend, PostgreSQL database, and React
            frontend, DevTrack exposes a REST API that polls GitHub and maps repository
            events to team entities. A WebSocket layer pushes live updates to connected
            clients without page refreshes. In a user study with 12 developers across 3
            teams, DevTrack reduced time spent searching for project status by
            <strong>47%</strong> and improved sprint retrospective preparation by
            <strong>31%</strong>.
          </p>
        </div>
      </div>
    </div>
  </div>
</section>

<!-- ── Results — tab selector (matches Pratik's pattern) ─────── -->
<section class="section" style="background: #fafafa">
  <div class="container is-max-desktop">
    <h2 class="section-heading has-text-centered">Results</h2>
    <p class="has-text-centered" style="margin-bottom: 1.5rem; color: #555; font-size: 0.95rem">
      Select a view to see the corresponding results.
    </p>

    <!-- Tab buttons -->
    <div class="tab-selector" data-group="results">
      <button class="tab-btn is-active" data-target="results-dashboard">Dashboard</button>
      <button class="tab-btn" data-target="results-analytics">Analytics</button>
      <button class="tab-btn" data-target="results-study">User Study</button>
    </div>

    <!-- Tab: Dashboard -->
    <div id="results-dashboard" class="tab-content is-active" data-group="results">
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div class="result-image">
            <img
              src="{{ '/assets/img/projects/devtrack_teaser.png' | relative_url }}"
              alt="DevTrack dashboard view"
            />
          </div>
          <p class="result-caption">
            The main dashboard showing commit activity (last 30 days), bug status overview,
            per-team project progress, and overall team performance metrics — all updated live
            via WebSocket.
          </p>
        </div>
      </div>
    </div>

    <!-- Tab: Analytics -->
    <div id="results-analytics" class="tab-content" data-group="results">
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div
            style="
              background: #1e1e2e;
              border-radius: 10px;
              padding: 2rem;
              font-family: 'Courier New', monospace;
              font-size: 0.85rem;
              color: #cdd6f4;
              line-height: 1.9;
            "
          >
            <pre style="margin: 0; color: inherit; background: transparent">

Metric Baseline DevTrack Δ
──────────────────────────────────────────────────
Status lookup time 8.3 min 4.4 min -47%
Retrospective prep 22.1 min 15.3 min -31%
Standup duration 14.2 min 9.8 min -31%
Missed action items 3.1 / wk 0.9 / wk -71%
Dashboard adoption — 11/12 devs 92%
Average SUS score — 82.3 / 100 ★★★★</pre>
</div>
<p class="result-caption">
Quantitative comparison between baseline toolchain (GitHub + Jira manually checked)
and DevTrack across 4 sprints with 12 developers.
</p>
</div>
</div>
</div>

    <!-- Tab: User Study -->
    <div id="results-study" class="tab-content" data-group="results">
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div class="columns has-text-centered">
            <div class="column">
              <div
                style="
                  background: #eef2ff;
                  border-radius: 12px;
                  padding: 1.5rem;
                "
              >
                <p
                  style="
                    font-size: 2.4rem;
                    font-weight: 700;
                    color: #4f46e5;
                    margin: 0;
                  "
                >
                  47%
                </p>
                <p style="font-size: 0.85rem; color: #555; margin-top: 0.3rem">
                  Reduction in<br />status-search time
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
                <p
                  style="
                    font-size: 2.4rem;
                    font-weight: 700;
                    color: #059669;
                    margin: 0;
                  "
                >
                  31%
                </p>
                <p style="font-size: 0.85rem; color: #555; margin-top: 0.3rem">
                  Faster<br />retrospective prep
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
                <p
                  style="
                    font-size: 2.4rem;
                    font-weight: 700;
                    color: #ea580c;
                    margin: 0;
                  "
                >
                  82.3
                </p>
                <p style="font-size: 0.85rem; color: #555; margin-top: 0.3rem">
                  SUS usability score<br />(out of 100)
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
                <p
                  style="
                    font-size: 2.4rem;
                    font-weight: 700;
                    color: #9333ea;
                    margin: 0;
                  "
                >
                  92%
                </p>
                <p style="font-size: 0.85rem; color: #555; margin-top: 0.3rem">
                  Voluntary adoption<br />after study ended
                </p>
              </div>
            </div>
          </div>
          <p class="result-caption" style="margin-top: 1rem">
            Within-subjects user study: 12 developers, 3 teams, 4 sprints. Participants alternated
            between existing toolchain and DevTrack.
          </p>
        </div>
      </div>
    </div>

  </div>
</section>

<!-- ── Methods ───────────────────────────────────────────────── -->
<section class="section">
  <div class="container is-max-desktop">
    <h2 class="section-heading">Methods</h2>
    <div class="content">
      <p>
        DevTrack follows a three-tier architecture. A background ingestion worker
        (node-cron, 5-min polling) fetches events from the GitHub REST API and normalises
        them into a PostgreSQL schema organised around <em>teams</em>, <em>commits</em>,
        <em>issues</em>, and <em>sprints</em>. An Express.js server exposes REST endpoints
        for historical queries and a Socket.io channel for live push. The React SPA consumes
        both, using React Query for caching and Recharts for rendering.
      </p>
    </div>

    <!-- Architecture diagram -->
    <div
      style="
        background: #1e1e2e;
        border-radius: 10px;
        padding: 1.5rem 2rem;
        margin: 1.5rem 0;
        overflow-x: auto;
      "
    >
      <pre
        style="
          margin: 0;
          font-family: 'Courier New', monospace;
          font-size: 0.82rem;
          color: #cdd6f4;
          line-height: 1.8;
          background: transparent;
        "
      >

┌─────────────────────────────────────────────────────────────┐
│ DevTrack Architecture │
├────────────────┬──────────────────────┬─────────────────────┤
│ Data Sources │ Backend │ Frontend │
│ │ │ │
│ GitHub API ──►│ Ingestion Worker │ │
│ (REST) │ (node-cron, 5 min) │ React 18 + Vite │
│ │ │ │ Recharts │
│ (future) │ ▼ │ React Query │
│ Linear API ──►│ PostgreSQL DB │ │
│ │ (Knex.js ORM) │◄── REST API │
│ │ │ │◄── WebSocket (WS) │
│ │ Express.js + WS ────►│ │
│ │ JWT Auth │ Tailwind CSS │
└────────────────┴──────────────────────┴─────────────────────┘</pre>
</div>

    <p>
      Role-based access control (RBAC) is enforced at the API layer using JWT tokens.
      Admin users can create teams and configure sprint boundaries; members see a
      read-only view of their team's dashboard. All tokens are verified on every
      request using Express middleware, with no client-side session state.
    </p>

  </div>
</section>

<!-- ── Feature Rollouts — tab selector ───────────────────────── -->
<section class="section" style="background: #fafafa">
  <div class="container is-max-desktop">
    <h2 class="section-heading has-text-centered">Feature Walkthrough</h2>
    <p class="has-text-centered" style="margin-bottom: 1.5rem; color: #555; font-size: 0.95rem">
      Select a feature to view its details.
    </p>

    <!-- Tab buttons -->
    <div class="tab-selector" data-group="features">
      <button class="tab-btn is-active" data-target="feat-realtime">Real-Time</button>
      <button class="tab-btn" data-target="feat-sprint">Sprints</button>
      <button class="tab-btn" data-target="feat-auth">Auth</button>
    </div>

    <!-- Tab: Real-Time -->
    <div id="feat-realtime" class="tab-content is-active" data-group="features">
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div
            style="
              background: white;
              border-radius: 10px;
              padding: 1.5rem 2rem;
              box-shadow: 0 2px 10px rgba(0, 0, 0, 0.06);
            "
          >
            <p style="font-weight: 600; font-size: 1rem; margin-bottom: 0.8rem">
              ⚡ WebSocket Live Dashboard
            </p>
            <p style="line-height: 1.8; color: #444">
              The backend broadcasts a <code>team:update</code> event whenever the ingestion
              worker writes new commits or issue changes to PostgreSQL. Connected React clients
              receive the diff via Socket.io and update the relevant chart state without a full
              page reload. Reconnection with exponential back-off is handled automatically.
            </p>
            <div
              style="
                background: #f0fdf4;
                border-left: 3px solid #22c55e;
                padding: 0.8rem 1rem;
                border-radius: 0 6px 6px 0;
                margin-top: 1rem;
                font-family: monospace;
                font-size: 0.82rem;
                color: #166534;
              "
            >
              socket.on('team:update', (delta) =&gt; queryClient.setQueryData(['team', delta.id], delta));
            </div>
          </div>
        </div>
      </div>
    </div>

    <!-- Tab: Sprints -->
    <div id="feat-sprint" class="tab-content" data-group="features">
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div
            style="
              background: white;
              border-radius: 10px;
              padding: 1.5rem 2rem;
              box-shadow: 0 2px 10px rgba(0, 0, 0, 0.06);
            "
          >
            <p style="font-weight: 600; font-size: 1rem; margin-bottom: 0.8rem">
              📈 Sprint Burndown & Velocity
            </p>
            <p style="line-height: 1.8; color: #444">
              Sprints are defined as date ranges configured by the team admin. The burndown
              chart plots remaining open issues against the ideal linear burn. Velocity is
              computed as the average number of story points (or issue count) completed per
              sprint over a configurable rolling window.
            </p>
            <p style="line-height: 1.8; color: #444; margin-top: 0.8rem">
              Data is pre-aggregated in a materialised view to keep query latency below 50ms
              even for teams with thousands of issues.
            </p>
          </div>
        </div>
      </div>
    </div>

    <!-- Tab: Auth -->
    <div id="feat-auth" class="tab-content" data-group="features">
      <div class="columns is-centered">
        <div class="column is-four-fifths">
          <div
            style="
              background: white;
              border-radius: 10px;
              padding: 1.5rem 2rem;
              box-shadow: 0 2px 10px rgba(0, 0, 0, 0.06);
            "
          >
            <p style="font-weight: 600; font-size: 1rem; margin-bottom: 0.8rem">
              🔑 JWT Role-Based Access Control
            </p>
            <p style="line-height: 1.8; color: #444">
              Authentication uses short-lived JWTs (15 min) with a rolling refresh token
              (7 days) stored in an HttpOnly cookie. Two roles are supported:
              <strong>admin</strong> (full CRUD on teams/sprints) and
              <strong>member</strong> (read-only dashboard access). All route guards are
              enforced server-side — the React client only shows/hides UI elements.
            </p>
          </div>
        </div>
      </div>
    </div>

  </div>
</section>
