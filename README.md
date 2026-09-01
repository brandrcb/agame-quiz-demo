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

**Lead capture posts to this form's own Google Apps Script handler**, which logs
a row to the *A-Game Parent Applications* sheet, emails the team a lead alert,
and emails the parent their score report. The page
only shows its confirmation checkmark once the handler confirms all of that —
see [Lead capture](#lead-capture) below.

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

It has its own handler and its own *A-Game Pro Applications* sheet, because it
is a different form for a different audience: the field names differ from the
parent application (`name`/`phone` rather than `parent_name`/`parent_phone`,
`improving` rather than `skills_wanted`, no school or age), it collects sport and
team instead, and it recommends no A-Game Ready modules. Keeping it separate
means its sheet carries no empty parent columns and its email copy — written to
the athlete rather than about them — can be edited without touching any other
form.

## Lead capture

Each application form posts to **its own** Google Apps Script web app, set as
`CONFIG.webhookUrl` at the top of that file's `<script>` block — a separate
sheet and deployment per form, and a third, older one for the ScholarGuard
quizzes. On each submission the handler does three independent things:

1. appends a row to the *A-Game Quiz Leads* Google Sheet,
2. emails a lead alert to the team, with reply-to set to the applicant,
3. emails the applicant their own score report.

It answers with `{"ok":true,"handler":"…","logged":true,"alerted":true,"client":true}`. The
form reads that answer and only shows its success message on `ok:true`; anything
else shows a plain failure notice and a retry button. A `fetch` that merely
resolves is not treated as proof the lead landed — that assumption is what
previously let a real application vanish behind a green checkmark.

The scripts, their deployment details and the test bench live in the private
project repo, not here.

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
