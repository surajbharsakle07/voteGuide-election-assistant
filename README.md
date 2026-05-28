# VoteGuide | Election Process Education Assistant

An interactive, single-page civic education web application designed to guide voters through registration protocols, election tracking, knowledge evaluations, and ballot counting mechanics.

---

## 🔗 Live Demo URL
* **Deployment URL**: `[Insert Live Deployment Link Here]`

---

## 🎯 Chosen Vertical
**Election Process Education** (Civic Engagement and Public Awareness)

---

## 🧠 Approach and Logic

To build a high-fidelity, comprehensive educational dashboard without framework overhead, we adopted a **Multi-Agent Prompting Architecture**. By partitioning development into specialized sub-agents, we eliminated code bloat, avoided placeholder segments, and ensured that accessibility and logic layers are deeply integrated.

### Multi-Agent Division of Responsibilities
1. **Agent 1 (UI Architect)**: Tasked with visual identity, theme configurations, typography, and strict WCAG 2.1 accessibility benchmarks. This agent implemented HSL color values, dark/light theme classes, custom focus rings (`focus-visible`), Alt+T contrast hotkeys, and global font scaling mechanics to accommodate low-vision users.
2. **Agent 2 (Feature Engineer)**: Tasked with component design and layouts. This agent constructed the physical models for the 6-stage Voter Journey Stepper, Custom Calendar Deadline timers, Ballot Buttons, Search Accordions, and the results "Civic Passport" panel.
3. **Agent 3 (Data & Logic Engine)**: Tasked with core calculations and state transitions. This agent designed the centralized reactive `state` dictionary, computed real-time countdown variables down to the second, parsed the 10 trivia question arrays, resolved local storage write/retrievals, and handled the voting simulator count math.
4. **Agent 4 (QA & Integration Specialist)**: Tasked with safety gates, testing, and clean code documentation. This agent isolated Google Charts loading pipelines with robust checks to prevent offline script crashes, handled responsive redraw behaviors, unified sub-task checkbox connections to master milestone counts, and built isolated print layouts.

---

## 🛠️ How the Solution Works

VoteGuide operates on a **Single-State Reactive State Loop**. User actions trigger updates on the centralized `state` object, which automatically updates the visual elements:

1. **Election Deadlines Tracker**: The user selects a target election (e.g., General Election) or uses an interactive calendar to select a custom target date. A background loop (`setInterval`) computes days/hours/minutes/seconds remaining, updating numerical cards using visual scale transitions and changing notification alert colors based on proximity.
2. **Voter Journey Stepper**: Users navigate 6 chronological stages of the voting cycle. Each stage contains an **interactive sub-task checklist**. Toggling checklist items writes changes to state. When all checklist items are ticked, the main stage lights up green, progress paths fill, and the dashboard progress ring fills in real-time.
3. **Mock Voting Simulator**: Users select a fictional candidate ballot card or trigger a simulated count scan of 50 randomized ballots. The simulator tallies counts inside state and renders responsive charts using Google Charts. It also teaches the difference between "Plurality" and "Majority" counting systems.
4. **Civic Awareness Quiz**: Users participate in a 10-question multiple-choice trivia quiz. Selecting options immediately locks in choices, highlighting correct answers in green, incorrect in red, displaying an explanatory feedback card, and advancing through a visual progress bar to award a final expertise badge.
5. **Voter Rights FAQ accordions**: Accordions slide down using a custom height animation, automatically closing other items. Typing in the search bar instantly filters questions and answers using regex matches, highlighting matching terms with high-contrast `<mark>` tags.
6. **Civic Passport Dashboard & Prints**: A consolidated dashboard displays a checklist of directed civic recommendations based on the user's progress. Clicking "Print Civic Passport" uses specialized CSS print rules to isolate and print a double-bordered Certificate of Civic Awareness while hiding website elements.

---

## 📊 Google Services Used

- **Google Fonts**: Implemented the **Poppins** typeface (for bold, modern headings) and the **Inter** font family (for body text). 
- **Google Charts API**: Integrated the Core Charts library to render responsive **Pie Charts** (displaying simulated ballot share percentages) and **Column Charts** (displaying raw count tallies). Charts automatically update in real-time as votes are cast and dynamically adapt to system themes (light/dark modes) and window size adjustments.

---

## 📌 Assumptions Made

1. **Local Sandboxing**: Assumed the file may be opened offline or inside restrictive sandbox folders. Consequently, the script includes safe guards to prevent Google Charts load crashes when offline, falling back to styled graphics.
2. **Browser Support**: Assumed users are on modern evergreen browsers (Chrome, Edge, Firefox, Safari) that support CSS custom transitions and the `localStorage` API.
3. **Mock Parameters**: Mock dates are mapped to the 2026 election cycle. Custom date picker options are provided so the user can easily input real future dates.

---

## 💻 Tech Stack
- **Structure & Layout**: Semantic HTML5, Font Awesome CDN
- **Styling**: Tailwind CSS CDN, Vanilla CSS custom variable overrides (for high-contrast contrast overrides and print layout isolation)
- **Logic**: Vanilla ES6 JavaScript (Single-State Reactive State Loop)
- **APIs & Assets**: Google Fonts, Google Charts Core API

---

## 🛠️ Prompt Architecture Table

| Prompt # | Agent Role / Phase | Prompt Purpose | Key Output & Outcome |
| :--- | :--- | :--- | :--- |
| **Prompt 1** | UI Architect | Design base responsive wireframe, typography configurations, high-contrast systems, and theme toggle buttons. | Established Poppins/Inter typography, custom Tailwind config, Alt+T contrast hotkey scripts, and global font resizing buttons. |
| **Prompt 2** | Feature Engineer | Build journey stepper nodes, checklist layouts, and the countdown timer widget with custom date selectors. | Completed the 6-stage stepper dashboard and custom calendar count timers with dynamic urgency color alerts. |
| **Prompt 3** | Logic & Trivia | Develop the 10-question voter awareness evaluation with instant answers, scoring badges, and explanation boxes. | Created the modular quiz container with progress metrics, score registries, and three custom badge classifications. |
| **Prompt 4** | Feature & Text | Structure a searchable FAQ accordion layout with real-time text input matching and highlighting. | Implemented custom max-height accordion transitions and fuzzy search keyword highlights using safe regex escape logic. |
| **Prompt 5** | QA & Dashboard | Integrate Google Charts simulation counting loops, centralized state engines, dashboard recommendation metrics, and isolated print styles. | Wired all features to a single state engine, synchronized local storage, resolved chart resizing squish bugs, and built printable certificate assets. |

---

## 🚀 Local Setup

No compilers, local installations, or heavy servers are required. The entire application is self-contained:

1. Download or clone this directory.
2. Double-click **[index.html](file:///c:/Users/bhars/OneDrive/Antigravity/project1/voteGuide-election-assistant/index.html)** (or right-click and choose to open in Google Chrome/Edge/Firefox).
3. Interact with the application immediately. All external CDN files are loaded securely via HTTPS.

---

## ♿ Accessibility Notes

Designed to strictly align with **WCAG 2.1 Level AA** standards:
- **ARIA Compliance**: Interactive controls feature screen-reader descriptive labels, exact roles, and reactive expansion states (`aria-expanded`, `aria-selected`, `aria-label`).
- **Keyboard Navigation**: The entire page is navigable via standard `Tab` focus cycles. Interactive nodes support both `Spacebar` and `Enter` activations.
- **Visual Sizing & Contrasts**: Includes deep accessibility triggers supporting light mode, dark mode, Stark Black-and-White High Contrast theme overrides (Alt+T shortcut), and a global text size scale (+10%, +20%, +25%).

---

## 🔮 Future Improvements

1. **Localized Election APIs**: Integrate open municipal APIs (like the Google Civic Information API) to automatically fetch actual registration cut-offs, ballot locations, and candidate lists based on zip code.
2. **Ranked-Choice Voting Simulator**: Expand the mock simulator to showcase advanced counting algorithms like Ranked-Choice Voting (RCV) and proportional allocations.
3. **Multi-lingual Support**: Introduce translation dictionaries (English, Spanish, French, etc.) to support diverse non-native speaking citizen populations.
4. **Offline Service Workers**: Package the single page application with modern service workers and cached assets to allow full quiz, checklists, and visual offline operations.