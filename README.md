# Wetland Explorers — interactive presentation demo

## Open the demo

**Quickest:** open `index.html` in Chrome or Edge. No installation or internet connection is needed.

**Recommended for a presentation:** on Windows, double-click `start-demo.cmd`, then open the local URL printed in its window (normally `http://127.0.0.1:8876`). Keep that window open. The launcher uses the bundled Codex Node runtime when available, or an installed Node.js. On another operating system with Node.js, run `node serve.cjs` from this folder.

Use the same browser and URL during the presentation: file URLs and HTTP URLs have separate local browser storage. Browser private modes or settings can limit persistence; the app then reports that the session is temporary.

## Suggested presentation: 5–7 minutes

1. **Home:** click a chapter node; explain the four Biodiversity topics and daily activity route. Collect the daily bonus once.
2. **Growth / Raising:** switch between Mira, the fiddler crab, and Pip, the black-faced spoonbill. Feed a companion, use a recovery item, and equip or remove the hat.
3. **Shop:** buy the crown, equip it, and optionally sell it back. Coins and accessories do not carry academic marks.
4. **Activities:** open Invertebrates → In-class activity, answer the MC question, write a short explanation, and submit. Coins are awarded once. The assessed medal remains pending.
5. **Teacher workspace → Review responses:** open the submitted activity, enter a reasoning score and feedback, and approve the review.
6. **Student view → Achievement:** show the newly reviewed medal, the separate in-class / after-class medals, and the non-graded activity-streak badges. No course percentage allocations are displayed.
7. **Teacher → Question bank:** edit a question, create a new one, or export the bank as JSON and import it again. Students' submitted answers retain snapshots of their original questions.
8. **Teacher → Scenes & characters:** upload an SVG, PNG, JPEG or WebP and apply it. The original SVG kit can supply sample files; upload a map/scenery SVG as a companion scene or a character SVG as a character. Uploaded accessories appear in the shop. Custom characters do not yet support accessory fitting.
9. **Course selector:** choose Plant Biology to preview a tree-based course profile. This is a theme preview, not a second configured course. Opening functional sections returns to the Biodiversity course.

Settings includes display size, gentle animation, logout, and reset. Logout returns to the demo account chooser and preserves progress. Reset clears this demo's progress, question edits, and uploaded artwork from the current browser origin after confirmation.

## Implemented

- Responsive student homepage using separate SVG map layers and accessible chapter buttons.
- Both species with separate removable accessories and independent Health, Hunger and Stamina.
- Inventory, buying/selling, care items, daily bonuses and activity rewards, with duplicate reward protection.
- Four topics × two assessed activities, each seeded with an MC question and short explanation.
- Daily practice, a hypothetical conservation special event, feedback and Hong Kong calendar-day streak tracking.
- Teacher question creation/editing, validated JSON import/export and topic filtering.
- Local artwork uploads, previews, scene/character selection, and asset removal.
- Teacher review and reviewed-activity medals; approved reasoning scores and CSV export.
- Local persistence, a presentation account chooser, and an optional dependency-free local server.

## Boundaries

This is a **local demonstration with one fictional student**, not an authenticated multi-user system. The teacher toggle is a presentation control, not access control. HKUST/Microsoft authentication, account passwords, shared server storage, and institutional gradebook transfer are not connected. No data is sent to an external service by the app.

The question examples are authored demonstration content; they have not been represented as extracted or approved lecture questions. The course team must review content, rubrics and medal-award rules before real student use. MC feedback is automatic; the teacher assigns the demonstration reasoning score. Approval awards a reviewed-activity medal, without an implemented mastery threshold or course-grade weighting.

Uploaded assets are limited to 500 KB each and a roughly 2.2 MB combined data-URL library to fit local browser storage. Static SVG validation rejects scripts, event handlers and external references; this is a demo restriction, not a substitute for a production upload service. On storage quota failure, the attempted change is rolled back with a message.

The map follows broad placement in the supplied park reference and is an illustrative learning map, not a visitor navigation map. The species artwork uses the supplied photographs as reference. Source screenshots and photograph pixels are not embedded.

## Files and checks

`index.html`, `styles.css`, `questions.js` and `app.js` form a buildless web app. `assets/` contains the vector assets. No dependency installation is required. `serve.cjs` and `start-demo.cmd` are optional launch helpers.

`validation.json` records automated browser checks. `screenshots/` contains desktop and mobile QA previews. The workspace test source is `build/check-wetland-demo.cjs`; tests use a disposable browser context and do not modify the presentation user's records.


## Module access codes
In Teacher workspace > Module codes, set or generate one code per in-class module. In Student view, open the locked in-class activity and enter that code. After-class activities need no code. Codes and unlocks are browser-local demo data, not secure cross-device authentication. Changing a code does not revoke existing unlocks. Special Events have been retired; Revision replaces Daily Question.
