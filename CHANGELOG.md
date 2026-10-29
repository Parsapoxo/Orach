# Orach — Changelog

Versioning: Semantic Versioning (MAJOR.MINOR.PATCH). Early versions (2.x) used a simpler scheme (+0.1 small / round up for big).

## 7.0.0-beta.5
- Redesigned the remaining pages in the same language (solid surfaces, pill buttons, big Bebas headings): Rankings and Profile (numbered rows, larger posters, score pills), Sign in / Register, admin tables and the GitHub-token gate, dialog (random pick) and toasts. The old rules for these were replaced, not overridden.
- Franchise pages: ★ site-average chip on each poster, and an "Unrated" filter next to All / Movies / Series (titles you haven't rated yet).
- Home: when signed in, each universe tile shows a progress bar and "N of M rated".
- Cleanup: removed CSS for classes that no longer exist in the page, darker-text token raised for readable contrast, global keyboard focus ring.
## 7.0.0-beta.4
- Search box no longer triggers the browser's saved-password dropdown: it's now a real `type="search"` field (name `q`, read-only until focused, password-manager opt-outs), and the sign-in / register / admin-token fields declare their real `autocomplete` roles so the browser stops guessing that the search field is a username field.
## 7.0.0-beta.3
- Cleanup: removed the whole old glass theme and the code of the previous navigation instead of layering the redesign over it. Gone: glass tokens/blur/inner highlights everywhere (panels are now solid), the sliding + draggable nav indicator, the Rankings sub-tab indicator, the floating liquid-glass mobile tab bar and its drag logic, the old collapsible search states, the old home picker styles. New: one `.nav-item` list (sidebar on desktop), search always visible top right (icon opens it on phones), solid bottom tab bar on phones, a single place that sets the active nav item (`updateFranchiseTabs`).
## 7.0.0-beta.2
- Redesign now matches the concept: search moved to the top right; "Home" item added to the sidebar; account card (avatar + username / "Sign in") at the bottom of the sidebar; All / Movies / Series filter chips on every franchise page; new title page (large poster, big title, breadcrumb, scores beside the poster); The Defenders Saga now always sits last (it appeared between Phase 1 and Phase 2 because of its order values).
## 7.0.0-beta.1
- Redesign ("cinema ledger", branch `redesign`): desktop nav is now a fixed left sidebar (logo, always-open search, Marvel / DC / DCAMU / Star Wars / Rankings with franchise-colored dots, profile at the bottom); gold accent warmed up; home is four franchise tiles (DCAMU added); poster cards get rounder corners and a watch-order number; filter chips and big headings restyled. Mobile keeps its top bar + floating tab bar. All logic unchanged except search now also opens on focus.
## 6.1.3
- Fixed a stray "No titles found" box appearing under the nav on first click. The (collapsed) search input could be filled by browser autofill, which fired the search with that text and could not be dismissed. Search now ignores input while collapsed, always clears/hides on collapse, the results box is hidden via CSS unless the search is open, and the input is marked as non-autofillable.
## 6.1.2
- Nav tabs: the sliding yellow indicator is now perfectly symmetric inside its pill (equal gap on all four sides: 5px top/bottom/left/right on desktop). Fixed a 1px border offset and rounding of widths in the indicator positioning; same fix for the Rankings sub-tab indicator; drag clamp now matches the pill padding.
## 6.1.1
- Poster rows: removed the solid dark side overlays (visible hard edge, extra thin line at the row edges, and a band taller than the posters). The edge fade is now a mask on the row itself, so it blends with the background and is identical on left and right. Arrow buttons are centered on the poster area (not the titles) and no longer have a background box.
## 6.1.0
- Mobile: new navigation. Top bar = logo + search + profile. Section tabs (Marvel / DC / DCAMU / Star Wars / Rankings) moved to a floating liquid-glass tab bar at the bottom, with sliding indicator and drag-to-snap.
## 6.0.1
- Mobile: version badge no longer floats over posters (sits under the nav).
## 6.0.0
- Mobile responsive pass: nav, home picker, poster rows (~2.4 cards/row), stacked detail page, smaller headings, modals/admin tweaks.
## 5.2.0
- The Defenders Saga rebuilt season-by-season (21 cards, user-defined order). Seasons of one show share a single detail page + ratings (`detailId`); parent records hidden from the grid (`hidden:true`) and from global search.
## 5.1.1
- Box office moved from tags into a single box at the left of the score boxes (Opening weekend + Worldwide gross).
## 5.1.0
- Added opening-weekend (domestic) and worldwide gross for 55 Marvel theatrical films (`openingWeekend`, `worldwideGross`). Series have none. Brand New Day marked "still in theaters".
## 5.0.3
- Fixed page horizontal jump between pages with/without scrollbar (`scrollbar-gutter: stable`).
## 5.0.2
- Custom site-styled scrollbar replaces browser default.
## 5.0.1
- Fixed broken top nav (CSS Grid attempt) — reverted to flexbox.
## 5.0.0
- Database migrated Firebase Firestore -> Supabase (tables `users`, `ratings`, RLS off). Separate one-time tool `migrate-to-supabase.html` copies old data.
## 4.1.1
- Attempted grid-based nav indicator (later reverted in 5.0.1).
## 4.1.0
- Draggable nav indicator (grab, drag, snaps to nearest tab). Stronger glass effect. Fixed poster hover shadow clipping. Font-load resync for indicator.
## 4.0.0
- iOS "Liquid Glass" theme applied site-wide (nav, search, dropdowns, cards, modals, admin). Switched to SemVer.
## 3.1
- "Punisher: One Last Kill" released (no longer Coming Soon).
## 3.0
- Download links: section on each title page; owner-only admin panel (GitHub token) saving `data/downloads.json` to the repo.
## 2.5
- Visible version badge bottom-right.
## 2.3 (baseline)
- Marvel phases split into Movies/Series, Phase 6, DCAMU section (26 titles, 2 arcs).
- Home page with Marvel/DC/Star Wars picker, zoom + opening video (`videos/*-intro.mp4`), poster-row layout (horizontal, arrows).
- Rankings: Orach Top 50 + IMDb Animations Top 50 (view-only) with random dice.
- Profile menu, owner-only "Fix ratings" admin, global search, glass-style nav pill with search icon.
- Page persists on refresh; poster cache in localStorage (OMDb quota).
- Ambient visual polish (glow, shimmer headings, staggered lists).
