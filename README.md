<!DOCTYPE html>
<html lang="en">
<head>
<meta charset="UTF-8">
<meta name="viewport" content="width=device-width, initial-scale=1.0">
<title>Capacities Learning Resources</title>
<link rel="preconnect" href="https://fonts.googleapis.com">
<link rel="preconnect" href="https://fonts.gstatic.com" crossorigin>
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300..600&display=swap" rel="stylesheet">
<style>
:root {
  --font: "Inter", -apple-system, BlinkMacSystemFont, sans-serif;
  --bg:           #f5f5f7;
  --surface:      #ffffff;
  --surface-2:    #f0f0f3;
  --surface-3:    #e8e8ec;
  --border:       rgba(0,0,0,0.08);
  --border-mid:   rgba(0,0,0,0.11);
  --text:         #1a1b1e;
  --text-muted:   #6b6f7a;
  --text-faint:   #a8aab5;
  --accent:       #5a5d66;
  --accent-dim:   rgba(90,93,102,0.1);
  --shadow:       0 1px 3px rgba(0,0,0,0.07), 0 2px 8px rgba(0,0,0,0.05);

  --t-gs-bg: rgba(49,130,206,0.09);   --t-gs-fg: #2b6cb0;
  --t-dn-bg: rgba(47,133,90,0.09);    --t-dn-fg: #276749;
  --t-ot-bg: rgba(107,70,193,0.09);   --t-ot-fg: #553c9a;
  --t-qu-bg: rgba(214,122,6,0.09);    --t-qu-fg: #975a16;
  --t-mg-bg: rgba(197,48,48,0.09);    --t-mg-fg: #9b2c2c;
  --t-ai-bg: rgba(49,151,149,0.09);   --t-ai-fg: #285e61;
  --t-pk-bg: rgba(113,63,188,0.09);   --t-pk-fg: #553c9a;
}

*, *::before, *::after { box-sizing: border-box; margin: 0; padding: 0; }
html { -webkit-font-smoothing: antialiased; text-rendering: optimizeLegibility; }
body {
  font-family: var(--font);
  font-size: 13px;
  line-height: 1.5;
  color: var(--text);
  background: var(--bg);
  min-height: 100dvh;
}
button { cursor: pointer; border: none; background: none; font: inherit; color: inherit; }
a { color: inherit; }
:focus-visible { outline: 2px solid var(--accent); outline-offset: 2px; border-radius: 4px; }

.page { display: flex; flex-direction: column; height: 100dvh; overflow: hidden; }

/* TITLEBAR */
.titlebar {
  display: flex; align-items: center; gap: 10px;
  padding: 0 16px; height: 46px;
  border-bottom: 1px solid var(--border);
  background: var(--surface);
  flex-shrink: 0;
}
.breadcrumb { display: flex; align-items: center; gap: 7px; font-size: 13px; font-weight: 500; color: var(--text-muted); }
.breadcrumb svg { color: var(--text-faint); }
.breadcrumb .crumb-name { color: var(--text); }
.titlebar-sep { flex: 1; }
.count-pill {
  font-size: 11px; color: var(--text-faint);
  background: var(--surface-2); border: 1px solid var(--border);
  padding: 2px 8px; border-radius: 20px; font-weight: 500;
}

/* TOOLBAR */
.toolbar {
  display: flex; align-items: center; gap: 8px;
  padding: 9px 16px; border-bottom: 1px solid var(--border);
  background: var(--surface); flex-shrink: 0; flex-wrap: wrap;
}
.search-wrap { position: relative; flex: 1; min-width: 160px; max-width: 300px; }
.search-wrap svg { position: absolute; left: 8px; top: 50%; transform: translateY(-50%); color: var(--text-faint); pointer-events: none; }
.search-input {
  width: 100%; padding: 5px 10px 5px 28px;
  background: var(--surface-2); border: 1px solid var(--border);
  border-radius: 6px; font: inherit; font-size: 12px; color: var(--text); outline: none;
  transition: border-color 0.15s;
}
.search-input::placeholder { color: var(--text-faint); }
.search-input:focus { border-color: var(--accent); }

.filter-row { display: flex; gap: 6px; flex-wrap: wrap; align-items: center; }
.cap-select {
  padding: 4px 22px 4px 9px;
  background: var(--surface-2); border: 1px solid var(--border);
  border-radius: 6px; font: inherit; font-size: 11px; color: var(--text-muted);
  cursor: pointer; appearance: none;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='10' height='10' viewBox='0 0 24 24' fill='none' stroke='%23aaa' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat; background-position: right 6px center; outline: none;
  transition: border-color 0.15s;
}
.cap-select:focus { border-color: var(--accent); }
.cap-select.active { border-color: var(--accent); background-color: var(--accent-dim); color: var(--text); }
.clear-link { font-size: 11px; color: var(--text-faint); cursor: pointer; padding: 3px 6px; border-radius: 5px; transition: color 0.15s; }
.clear-link:hover { color: var(--text-muted); }

/* TABLE */
.table-area { flex: 1; overflow: auto; background: var(--bg); }
table { width: 100%; border-collapse: collapse; font-size: 12.5px; }
thead { position: sticky; top: 0; z-index: 20; }
th {
  padding: 7px 12px; text-align: left; font-size: 11px; font-weight: 500;
  color: var(--text-faint); white-space: nowrap;
  background: var(--surface); border-bottom: 1px solid var(--border-mid);
  letter-spacing: 0.03em; cursor: pointer; user-select: none;
}
th:hover { color: var(--text-muted); }
th.sorted { color: var(--accent); }
.sort-arrow { opacity: 0; font-size: 10px; margin-left: 3px; transition: opacity 0.1s; }
th:hover .sort-arrow { opacity: 0.4; }
th.sorted .sort-arrow { opacity: 1; }
.c-title { min-width: 220px; width: 26%; }
.c-topic { min-width: 165px; }
.c-format { min-width: 80px; }
.c-source { min-width: 90px; }
.c-diff { min-width: 100px; }
.c-status { min-width: 100px; }
.c-notes { min-width: 200px; }
tr { border-bottom: 1px solid var(--border); }
tr:last-child { border-bottom: none; }
tr:hover td { background: var(--surface); }
td { padding: 7px 12px; vertical-align: middle; transition: background 0.1s; }

.title-cell { display: flex; align-items: center; gap: 6px; }
.title-link { color: var(--text); text-decoration: none; font-weight: 450; line-height: 1.35; transition: color 0.15s; }
.title-link:hover { color: var(--accent); text-decoration: underline; text-underline-offset: 2px; }
.ext-icon { flex-shrink: 0; color: var(--text-faint); opacity: 0; transition: opacity 0.15s; }
tr:hover .ext-icon { opacity: 1; }

/* CHIPS */
.chip { display: inline-flex; align-items: center; gap: 4px; padding: 2px 7px; border-radius: 4px; font-size: 11px; font-weight: 500; white-space: nowrap; line-height: 1.6; }
.chip-gs { background: var(--t-gs-bg); color: var(--t-gs-fg); }
.chip-dn { background: var(--t-dn-bg); color: var(--t-dn-fg); }
.chip-ot { background: var(--t-ot-bg); color: var(--t-ot-fg); }
.chip-qu { background: var(--t-qu-bg); color: var(--t-qu-fg); }
.chip-mg { background: var(--t-mg-bg); color: var(--t-mg-fg); }
.chip-ai { background: var(--t-ai-bg); color: var(--t-ai-fg); }
.chip-pk { background: var(--t-pk-bg); color: var(--t-pk-fg); }
.chip-fmt { background: var(--surface-3); color: var(--text-muted); }
.chip-off { background: var(--accent-dim); color: var(--accent); }
.chip-com { background: var(--surface-3); color: var(--text-muted); }
.chip-3p  { background: var(--surface-3); color: var(--text-faint); }
.chip-beg { background: rgba(47,133,90,0.09);  color: #276749; }
.chip-int { background: rgba(214,122,6,0.09);  color: #975a16; }

/* STATUS */
.cap-status {
  appearance: none; border: none; background: transparent;
  font: inherit; font-size: 11px; font-weight: 500; color: var(--text-faint);
  cursor: pointer; padding: 2px 18px 2px 7px; border-radius: 4px;
  background-image: url("data:image/svg+xml,%3Csvg xmlns='http://www.w3.org/2000/svg' width='9' height='9' viewBox='0 0 24 24' fill='none' stroke='%23aaa' stroke-width='2'%3E%3Cpath d='M6 9l6 6 6-6'/%3E%3C/svg%3E");
  background-repeat: no-repeat; background-position: right 4px center;
  transition: background-color 0.15s;
}
.cap-status:hover { background-color: var(--surface-3); }
.cap-status.s-done  { background-color: rgba(47,133,90,0.09);  color: #276749; }
.cap-status.s-rev   { background-color: rgba(214,122,6,0.09);  color: #975a16; }

.notes-text { color: var(--text-faint); font-size: 11.5px; line-height: 1.4; }

.empty-wrap { display: flex; flex-direction: column; align-items: center; justify-content: center; padding: 64px 24px; gap: 10px; text-align: center; }
.empty-wrap svg { color: var(--text-faint); opacity: 0.4; }
.empty-wrap p { font-size: 13px; color: var(--text-muted); }
.empty-wrap span { font-size: 12px; color: var(--text-faint); max-width: 280px; }

.statusbar {
  display: flex; align-items: center; gap: 12px;
  padding: 5px 16px; border-top: 1px solid var(--border);
  background: var(--surface); font-size: 11px; color: var(--text-faint); flex-shrink: 0;
}
.statusbar-sep { flex: 1; }

@media (max-width: 600px) {
  .titlebar, .toolbar { padding: 8px 12px; }
  td, th { padding: 6px 8px; }
  .c-notes { display: none; }
}
</style>
</head>
<body>
<div class="page">

<div class="titlebar">
  <div class="breadcrumb">
    <svg width="15" height="15" viewBox="0 0 16 16" fill="none">
      <rect x="1" y="1" width="6" height="6" rx="1.5" fill="currentColor"/>
      <rect x="9" y="1" width="6" height="6" rx="1.5" fill="currentColor" opacity="0.35"/>
      <rect x="1" y="9" width="6" height="6" rx="1.5" fill="currentColor" opacity="0.35"/>
      <rect x="9" y="9" width="6" height="6" rx="1.5" fill="currentColor" opacity="0.6"/>
    </svg>
    <span class="crumb-name">Capacities Learning Resources</span>
  </div>
  <div class="titlebar-sep"></div>
  <span class="count-pill" id="row-count">53 objects</span>
</div>

<div class="toolbar">
  <div class="search-wrap">
    <svg width="12" height="12" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
    <input type="search" class="search-input" id="search" placeholder="Search…" autocomplete="off">
  </div>
  <div class="filter-row">
    <select class="cap-select" id="f-topic" aria-label="Topic">
      <option value="">Topic</option>
      <option>Getting Started</option>
      <option>Daily Notes &amp; Calendar</option>
      <option>Object Types &amp; Structure</option>
      <option>Queries, Tags &amp; Collections</option>
      <option>Migration from Notion</option>
      <option>AI &amp; Advanced Features</option>
      <option>PKM Setup &amp; Community</option>
    </select>
    <select class="cap-select" id="f-format" aria-label="Format">
      <option value="">Format</option>
      <option>Video</option>
      <option>Docs</option>
      <option>Article</option>
      <option>Community</option>
    </select>
    <select class="cap-select" id="f-source" aria-label="Source">
      <option value="">Source</option>
      <option>Official</option>
      <option>Community</option>
      <option>Third-party</option>
    </select>
    <select class="cap-select" id="f-diff" aria-label="Level">
      <option value="">Level</option>
      <option>Beginner</option>
      <option>Intermediate</option>
    </select>
    <button class="clear-link" id="clear">Clear</button>
  </div>
</div>

<div class="table-area">
  <table aria-label="Learning resources">
    <thead>
      <tr>
        <th class="c-title" data-col="title">Title <span class="sort-arrow">↑</span></th>
        <th class="c-topic" data-col="topic">Topic <span class="sort-arrow">↑</span></th>
        <th class="c-format" data-col="format">Format <span class="sort-arrow">↑</span></th>
        <th class="c-source" data-col="source">Source <span class="sort-arrow">↑</span></th>
        <th class="c-diff" data-col="difficulty">Level <span class="sort-arrow">↑</span></th>
        <th class="c-status">Status</th>
        <th class="c-notes">Notes</th>
      </tr>
    </thead>
    <tbody id="tbody"></tbody>
  </table>
  <div class="empty-wrap" id="empty" style="display:none">
    <svg width="32" height="32" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="1.5"><circle cx="11" cy="11" r="8"/><path d="m21 21-4.35-4.35"/></svg>
    <p>No results</p>
    <span>Try a different search or clear your filters</span>
  </div>
</div>

<div class="statusbar">
  <svg width="11" height="11" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" opacity="0.4"><rect x="3" y="3" width="7" height="7" rx="1"/><rect x="14" y="3" width="7" height="7" rx="1"/><rect x="3" y="14" width="7" height="7" rx="1"/><rect x="14" y="14" width="7" height="7" rx="1"/></svg>
  <span id="status-text">53 objects</span>
  <div class="statusbar-sep"></div>
  <span>Resource · Custom object type</span>
</div>

</div>
<script>
const DATA = [
  ["Getting Started","Getting Started — Capacities Docs","Docs","Official","Beginner","https://docs.capacities.io/tutorials/getting-started","Official guide: objects, linking, and the calendar system"],
  ["Getting Started","Getting Started with Capacities (video)","Video","Official","Beginner","https://www.youtube.com/watch?v=A7UPhggi7Ek","~15 min official walkthrough using built-in templates"],
  ["Getting Started","Capacities' Three Fundamental Pillars","Video","Official","Beginner","https://www.youtube.com/watch?v=iSJcw81pYx0","5 min intro: networked, object-based, time-based note-taking"],
  ["Getting Started","Capacities App Tutorial & Review 2026","Video","Community","Beginner","https://www.youtube.com/watch?v=jpBg1H8HODM","Independent step-by-step overview, late 2025"],
  ["Getting Started","A Step by Step Guide — Mar 2026","Video","Community","Beginner","https://www.youtube.com/watch?v=N-fR9pbxkZI","Recent community walkthrough, March 2026"],
  ["Getting Started","How to Use Capacities 2025 | Beginner","Video","Community","Beginner","https://www.youtube.com/watch?v=CXvmCtwKhkA","Community beginner tutorial, March 2025"],
  ["Getting Started","A Guide to PKM with Capacities — Blog","Article","Official","Beginner","https://capacities.io/blog/guide-to-pkm","Official 16-min-read guide to building a PKM system"],
  ["Getting Started","Capacities Documentation Home","Docs","Official","Beginner","https://docs.capacities.io","Main docs landing page — start here"],
  ["Daily Notes & Calendar","Dates and Daily Notes — Docs","Docs","Official","Beginner","https://docs.capacities.io/reference/dates-and-daily-notes","Full calendar system: day/week/month views, date links, timeline"],
  ["Daily Notes & Calendar","Customise Daily Note Template — Docs","Docs","Official","Beginner","https://capacities.io/tutorials/customize-daily-notes","Official guide: tables, to-do blocks, heading templates"],
  ["Daily Notes & Calendar","Customising Your Daily Note Template","Video","Official","Beginner","https://www.youtube.com/watch?v=rzjT4iWDzhU","10 min: two-column layout, task actions, default templates"],
  ["Daily Notes & Calendar","Recreating Steffen's Daily Note Template","Video","Official","Intermediate","https://www.youtube.com/watch?v=6wuEXxb0Foo","Co-founder's setup with daily reflection practice"],
  ["Daily Notes & Calendar","Daily & Weekly Notes — Queries & More (Apr 2026)","Video","Community","Intermediate","https://www.youtube.com/watch?v=rh-C33HykPg","43 min: two-way linking, date properties, variable queries"],
  ["Daily Notes & Calendar","My Capacities LifeOS Setup (Mar 2025)","Video","Community","Intermediate","https://www.youtube.com/watch?v=193Ph5OEnoM","Full LifeOS: daily/weekly/monthly linking, goals, projects"],
  ["Daily Notes & Calendar","My LifeOS — central daily note, goals, projects","Video","Community","Intermediate","https://www.youtube.com/watch?v=TuFe2zlh9RM","Daily note as hub linking quarterly, monthly, weekly notes"],
  ["Daily Notes & Calendar","Daily Notes 2.0 — What's New Release 8","Article","Official","Beginner","https://capacities.io/whats-new/release-8","Week and month overview views, templates, shortcuts"],
  ["Object Types & Structure","Object Types — Docs Reference","Docs","Official","Beginner","https://docs.capacities.io/reference/content-types","Main reference for built-in and custom object types"],
  ["Object Types & Structure","Define Your Own Object Types — Docs","Docs","Official","Beginner","https://docs.capacities.io/tutorials/custom-content-types","Step-by-step: custom types, properties, layouts"],
  ["Object Types & Structure","When to Create a New Object Type — Docs","Docs","Official","Beginner","https://docs.capacities.io/tutorials/when-to-create-new-object-type","Three-question framework for deciding on new types"],
  ["Object Types & Structure","Object Properties — Docs Reference","Docs","Official","Beginner","https://docs.capacities.io/reference/object-properties","All property types including two-way linked properties"],
  ["Object Types & Structure","Create Your Own Object Type (official video)","Video","Official","Beginner","https://www.youtube.com/watch?v=ink--8N3C4c","Official short guide: creating and customising an object type"],
  ["Object Types & Structure","How to Create a Custom Object (2025)","Video","Community","Beginner","https://www.youtube.com/watch?v=zrH4sEpsPQY","Community video using a book tracker as worked example"],
  ["Object Types & Structure","My Best Tips for Structuring Capacities","Video","Community","Intermediate","https://www.youtube.com/watch?v=VxW5WoAtCn0","Objects, collections, and tags working together"],
  ["Object Types & Structure","Deep Dive: Source Object Type (Nov 2025)","Video","Community","Intermediate","https://www.youtube.com/watch?v=E-PgO2LCEPg","In-depth example of building a Source object type"],
  ["Object Types & Structure","Customizing Your Object Types (video)","Video","Official","Beginner","https://www.youtube.com/watch?v=eq550oIk2bg","Official walkthrough: layouts and colour customisation"],
  ["Object Types & Structure","Two-Way Linked Properties — Jul 2025","Video","Official","Intermediate","https://www.youtube.com/watch?v=CizsDy1e-hA","Sync properties between two custom object types automatically"],
  ["Queries, Tags & Collections","Queries — Docs Reference","Docs","Official","Intermediate","https://docs.capacities.io/reference/queries","Full reference: object type, search, and tag queries"],
  ["Queries, Tags & Collections","Tags — Docs Reference","Docs","Official","Beginner","https://docs.capacities.io/reference/tags","How tags work vs labels and collections"],
  ["Queries, Tags & Collections","Collections — Docs Reference","Docs","Official","Beginner","https://docs.capacities.io/reference/collections","Manual curation groups within a single object type"],
  ["Queries, Tags & Collections","Tags vs. Collections — Docs Tutorial","Docs","Official","Beginner","https://docs.capacities.io/tutorials/tags-vs-collections","Collections within a type; tags across types"],
  ["Queries, Tags & Collections","Organizational Structures — Docs Reference","Docs","Official","Beginner","https://docs.capacities.io/reference/organizational-structures","Full decision tree: types, labels, tags, collections, queries"],
  ["Queries, Tags & Collections","Working with Tags in Capacities","Video","Official","Beginner","https://www.youtube.com/watch?v=_TiJuqVeD30","Quick tip: using and filtering by tag"],
  ["Queries, Tags & Collections","Tags and Collections Part I (Sep 2024)","Video","Official","Beginner","https://www.youtube.com/watch?v=85rFpvl0pvM","Intro to tags and collections with AI-organised collections demo"],
  ["Queries, Tags & Collections","Label Properties in Capacities (Aug 2025)","Video","Official","Beginner","https://www.youtube.com/watch?v=aICbyg5X9xw","Label properties: structure and filter within one object type"],
  ["Queries, Tags & Collections","Object Type Queries (video)","Video","Official","Intermediate","https://www.youtube.com/watch?v=35GCX55BNsE","Building and saving object type queries"],
  ["Queries, Tags & Collections","4 More Ways to Use Queries (Jun 2025)","Video","Official","Intermediate","https://www.youtube.com/watch?v=pLLcmJZWS-A","Tag reviews, backlog tracking, and more query patterns"],
  ["Queries, Tags & Collections","Label Properties — What's New Release 52","Article","Official","Beginner","https://capacities.io/whats-new/release-52","Release notes: label properties and more powerful queries"],
  ["Migration from Notion","Switching from Notion to Capacities — Docs","Docs","Official","Beginner","https://docs.capacities.io/migration/switching-from-notion","Concept mapping: notion page → object, database → object type"],
  ["Migration from Notion","Coming from Other Tools — Migration Overview","Docs","Official","Beginner","https://docs.capacities.io/migration","Full recommended migration path from various apps"],
  ["Migration from Notion","Import Content to Capacities — Docs","Docs","Official","Beginner","https://docs.capacities.io/reference/import","Import markdown, html, txt; bulk import up to 100 per run"],
  ["Migration from Notion","Notion to Capacities Guide — EuropeanTechMap","Article","Third-party","Beginner","https://europeantechmap.eu/migration-guide/notion-to-capacities","Third-party feature and pricing comparison"],
  ["AI & Advanced Features","AI Assistant — Docs Reference","Docs","Official","Intermediate","https://docs.capacities.io/reference/ai-assistant","AI chat with your space context; @ to add notes"],
  ["AI & Advanced Features","Release 59 — AI Assistant Got Smarter (Mar 2026)","Article","Official","Intermediate","https://capacities.io/whats-new/release-59","AI shows which notes it used; richer context support"],
  ["AI & Advanced Features","Release 59 — Smarter AI Assistant (video)","Video","Official","Intermediate","https://www.youtube.com/watch?v=TTlR4T7r4WU","Video walkthrough of the smarter AI features"],
  ["AI & Advanced Features","What's Next — Capacities Roadmap (Apr 2026)","Article","Official","Intermediate","https://capacities.io/whats-next","Public roadmap: AI chat vision and upcoming MCP features"],
  ["AI & Advanced Features","Is Capacities Pro Worth It? — Reddit (Feb 2026)","Article","Community","Beginner","https://www.reddit.com/r/capacitiesapp/comments/1r9r9s5/is_capacities_pro_worth_it/","Community: queries and tasks justify Pro"],
  ["AI & Advanced Features","Capacities Believer Plan — Official Page","Docs","Official","Beginner","https://capacities.io/believer","Believer plan: all Pro features + beta access"],
  ["PKM Setup & Community","r/capacitiesapp — Subreddit","Community","Community","Beginner","https://www.reddit.com/r/capacitiesapp/","Main community: tips, workflows, Q&A"],
  ["PKM Setup & Community","The PKM + Project Management Hybrid (Dec 2025)","Article","Community","Intermediate","https://www.systemsandflow.io/p/capacities-in-2025-the-pkm-project","In-depth write-up: PKM + project management in 2025"],
  ["PKM Setup & Community","How I Use Capacities for Task Management (Jan 2026)","Article","Community","Intermediate","https://www.reddit.com/r/capacitiesapp/comments/1q6k372/how_i_use_capacities_for_task_and_project/","Reddit: Google Calendar sync, Todoist, weekly reviews"],
  ["PKM Setup & Community","Capacities YouTube Channel — Official Videos","Community","Official","Beginner","https://www.youtube.com/@CapacitiesHQ","Official channel: 20+ tutorials and feature walkthroughs"],
  ["PKM Setup & Community","Capacities Blog — All Posts","Article","Official","Beginner","https://capacities.io/blog","Official blog: product updates, PKM philosophy, workflows"],
  ["PKM Setup & Community","Capacities What's New — All Releases","Article","Official","Beginner","https://capacities.io/whats-new","Full release history — reference for available features"],
];

const TOPIC_CHIP={"Getting Started":"chip-gs","Daily Notes & Calendar":"chip-dn","Object Types & Structure":"chip-ot","Queries, Tags & Collections":"chip-qu","Migration from Notion":"chip-mg","AI & Advanced Features":"chip-ai","PKM Setup & Community":"chip-pk"};
const FMT_ICON={"Video":`<svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><polygon points="5 3 19 12 5 21 5 3"/></svg>`,"Docs":`<svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M14 2H6a2 2 0 0 0-2 2v16a2 2 0 0 0 2 2h12a2 2 0 0 0 2-2V8z"/><polyline points="14 2 14 8 20 8"/></svg>`,"Article":`<svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><path d="M4 6h16M4 12h16M4 18h7"/></svg>`,"Community":`<svg width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2.5"><circle cx="12" cy="8" r="4"/><path d="M20 21a8 8 0 1 0-16 0"/></svg>`};

const statuses={};
const rows=DATA.map((r,i)=>({id:i,topic:r[0],title:r[1],format:r[2],source:r[3],difficulty:r[4],url:r[5],notes:r[6]}));
let sortCol=null,sortDir=1;

function srcChip(s){return s==="Official"?"chip-off":s==="Third-party"?"chip-3p":"chip-com";}
function diffChip(d){return d==="Intermediate"?"chip-int":"chip-beg";}
function stClass(s){return s==="Done"?"s-done":s==="Revisit"?"s-rev":"";}

function buildRow(r){
  const st=statuses[r.id]||"To Watch";
  return `<tr>
    <td class="c-title"><div class="title-cell">
      <a href="${r.url}" class="title-link" target="_blank" rel="noopener noreferrer">${r.title}</a>
      <svg class="ext-icon" width="10" height="10" viewBox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2"><path d="M18 13v6a2 2 0 0 1-2 2H5a2 2 0 0 1-2-2V8a2 2 0 0 1 2-2h6"/><polyline points="15 3 21 3 21 9"/><line x1="10" y1="14" x2="21" y2="3"/></svg>
    </div></td>
    <td class="c-topic"><span class="chip ${TOPIC_CHIP[r.topic]||'chip-gs'}">${r.topic}</span></td>
    <td class="c-format"><span class="chip chip-fmt" style="gap:4px">${FMT_ICON[r.format]||""}${r.format}</span></td>
    <td class="c-source"><span class="chip ${srcChip(r.source)}">${r.source}</span></td>
    <td class="c-diff"><span class="chip ${diffChip(r.difficulty)}">${r.difficulty}</span></td>
    <td class="c-status"><select class="cap-status ${stClass(st)}" data-id="${r.id}" aria-label="Status">
      <option${st==="To Watch"?" selected":""}>To Watch</option>
      <option${st==="Done"?" selected":""}>Done</option>
      <option${st==="Revisit"?" selected":""}>Revisit</option>
    </select></td>
    <td class="c-notes"><span class="notes-text">${r.notes}</span></td>
  </tr>`;
}

function getFiltered(){
  const q=(document.getElementById("search").value||"").toLowerCase();
  const ft=document.getElementById("f-topic").value;
  const ff=document.getElementById("f-format").value;
  const fs=document.getElementById("f-source").value;
  const fd=document.getElementById("f-diff").value;
  ["f-topic","f-format","f-source","f-diff"].forEach(id=>{document.getElementById(id).classList.toggle("active",document.getElementById(id).value!=="");});
  return rows.filter(r=>{
    if(q&&!r.title.toLowerCase().includes(q)&&!r.notes.toLowerCase().includes(q)&&!r.topic.toLowerCase().includes(q))return false;
    if(ft&&r.topic!==ft)return false;
    if(ff&&r.format!==ff)return false;
    if(fs&&r.source!==fs)return false;
    if(fd&&r.difficulty!==fd)return false;
    return true;
  });
}

function render(){
  let f=getFiltered();
  if(sortCol)f.sort((a,b)=>a[sortCol].localeCompare(b[sortCol])*sortDir);
  const tbody=document.getElementById("tbody");
  const empty=document.getElementById("empty");
  if(!f.length){tbody.innerHTML="";empty.style.display="flex";}
  else{
    tbody.innerHTML=f.map(buildRow).join("");
    empty.style.display="none";
    tbody.querySelectorAll(".cap-status").forEach(sel=>{
      sel.addEventListener("change",function(){
        statuses[+this.dataset.id]=this.value;
        this.className="cap-status "+stClass(this.value);
      });
    });
  }
  const txt=f.length===DATA.length?`${DATA.length} objects`:`${f.length} of ${DATA.length} objects`;
  document.getElementById("row-count").textContent=txt;
  document.getElementById("status-text").textContent=txt;
}

["search","f-topic","f-format","f-source","f-diff"].forEach(id=>{
  const el=document.getElementById(id);
  el.addEventListener("input",render);el.addEventListener("change",render);
});
document.getElementById("clear").addEventListener("click",()=>{
  document.getElementById("search").value="";
  ["f-topic","f-format","f-source","f-diff"].forEach(id=>{const el=document.getElementById(id);el.value="";el.classList.remove("active");});
  render();
});
document.querySelectorAll("th[data-col]").forEach(th=>{
  th.addEventListener("click",()=>{
    const col=th.dataset.col;
    if(sortCol===col){sortDir*=-1;}else{sortCol=col;sortDir=1;}
    document.querySelectorAll("th[data-col]").forEach(h=>{h.classList.remove("sorted");h.querySelector(".sort-arrow").textContent="↑";});
    th.classList.add("sorted");
    th.querySelector(".sort-arrow").textContent=sortDir===1?"↑":"↓";
    render();
  });
});
render();
</script>
</body>
</html>
