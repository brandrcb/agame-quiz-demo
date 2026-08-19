# A-Game Coaching × ScholarGuard — Quiz Demos

Live, interactive demos of the "A-Game Score" athlete-mindset quiz and the
one-on-one coaching application, built for Steven Griffith's A-Game Coaching
(https://agamecoach.com/).

## Live demo links

GitHub Pages is enabled for this repo, so all three pages are live at:

- **Main quiz:** https://brandrcb.github.io/agame-quiz-demo/agame-score-quiz.html
- **Star-rating variant:** https://brandrcb.github.io/agame-quiz-demo/agame-score-quiz-stars.html
- **Coaching application:** https://brandrcb.github.io/agame-quiz-demo/agame-coaching-application.html

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

## Files

| File | What it is |
|------|------------|
| `agame-score-quiz.html` | Main quiz — "What's Your Athlete's A-Game Score?" Self-contained interactive demo. |
| `agame-score-quiz-stars.html` | Alternate version using a star-rating style ("Rate Your Athlete's Mindset"). |
| `agame-coaching-application.html` | Long-form one-on-one coaching application — parent and athlete details, ten mindset ratings, four written questions, and a scored results view. |
| `agame-score-quiz-agame-only.html` | Main quiz with ScholarGuard branding removed (A-Game only). |
| `agame-score-quiz-stars-agame-only.html` | Star-rating variant with ScholarGuard branding removed (A-Game only). |
| `agame-logo-white.png` | Official A-Game Coaching logo (white, transparent) used in the quiz header. |
| `favicon.ico` | Multi-size browser icon (16 and 32px), used by all three pages. |
| `agame-favicon-32.png` | 32px PNG favicon. |
| `agame-apple-touch-icon.png` | 180px icon for iOS home-screen bookmarks. |

This is a public repository intended only for sharing the client-facing demos.
Internal sales materials live in the separate private project repo.
