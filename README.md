# A-Game Coaching × ScholarGuard — Quiz Demos

Live, interactive demos of the "A-Game Score" athlete-mindset quiz and the
one-on-one coaching application, built for Steven Griffith's A-Game Coaching
(https://agamecoach.com/).

## Live demo links

GitHub Pages is enabled for this repo, so all four pages are live at:

- **Main quiz:** https://brandrcb.github.io/agame-quiz-demo/agame-score-quiz.html
- **Star-rating variant:** https://brandrcb.github.io/agame-quiz-demo/agame-score-quiz-stars.html
- **Coaching application (parents):** https://brandrcb.github.io/agame-quiz-demo/agame-coaching-application.html
- **Pro application (athletes):** https://brandrcb.github.io/agame-quiz-demo/agame-pro-application.html

## The coaching application

`agame-coaching-application.html` is the newer, parent-facing long-form page.
A parent works through it in one pass:

- **Parent contact info** — names, email, phone.
- **Student athlete details** — name, age, school, sports, position(s).
- **Ten-area mindset rating** — each area rated 1–10.
- **Four written questions** — what skills they want their athlete to have,
  what is holding them back, what happens if nothing changes, and their own
  commitment level.
- **Scored results** — an overall A-Game Score measured against an adjustable
  expectation, plus the three lowest-rated growth areas with a recommended
  focus for each.

**Lead capture is not yet connected.** `CONFIG.webhookUrl` is deliberately
empty, pending a new Google Sheet and Apps Script deployment — this form's
fields differ from those of the older quizzes, so it needs its own sheet and
handler rather than reusing theirs. Until that URL is filled in, submissions
only log to the browser console.

## The Pro application

`agame-pro-application.html` is the same intake reworked to be **athlete-facing**
— the athlete fills it in themselves rather than a parent doing it for them. It
follows the order of Steven's original questionnaire:

- **About you** — name, email, phone, sport, team/organization, position.
- **Ten-area mindset rating** — the same ten areas, rated 1–10, asked in the
  first person ("How do you rate right now?").
- **Four written questions** — what they want to improve, what is holding them
  back, what happens if nothing changes, and their commitment level.
- **Scored results** — the same A-Game Score, tier, adjustable standard, and
  top three growth areas.

Its lead capture is **also** unconnected, and it needs its own destination: the
field names differ from the parent application (`name`/`phone` rather than
`parent_name`/`parent_phone`, `improving` rather than `skills_wanted`, no
school or age), so it cannot share a sheet with either of the other forms.

## Files

| File | What it is |
|------|------------|
| `agame-score-quiz.html` | Main quiz — "What's Your Athlete's A-Game Score?" Self-contained interactive demo. |
| `agame-score-quiz-stars.html` | Alternate version using a star-rating style ("Rate Your Athlete's Mindset"). |
| `agame-coaching-application.html` | Long-form one-on-one coaching application — parent and athlete details, ten mindset ratings, four written questions, and a scored results view. |
| `agame-pro-application.html` | Athlete-facing version of the application — same ten ratings and scored report, asked in the first person. |
| `agame-score-quiz-agame-only.html` | Main quiz with ScholarGuard branding removed (A-Game only). |
| `agame-score-quiz-stars-agame-only.html` | Star-rating variant with ScholarGuard branding removed (A-Game only). |
| `agame-logo-white.png` | Official A-Game Coaching logo (white, transparent) used in the quiz header. |
| `favicon.ico` | Multi-size browser icon (16 and 32px), used by all four pages. |
| `agame-favicon-32.png` | 32px PNG favicon. |
| `agame-apple-touch-icon.png` | 180px icon for iOS home-screen bookmarks. |

This is a public repository intended only for sharing the client-facing demos.
Internal sales materials live in the separate private project repo.
