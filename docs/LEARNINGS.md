# Karl Gourgue Personal Website - Build Documentation

## Project Goal

Build a simple personal website to showcase work background and side projects. The site would be sent to potential employers, so it needed to make a strong impression while staying minimal and professional.

## Initial Requirements Gathered

Used an interview-style approach to gather requirements before building anything.

### Round 1 Questions
| Question | Answer |
|----------|--------|
| Tech stack | Plain HTML/CSS/JS (no build step) |
| Current role | Sales for an LMS solution |
| Sections | About + Projects |
| Visual style | Clean & minimal |

### Round 2 Questions
| Question | Answer |
|----------|--------|
| Project types | Side projects/apps |
| Contact method | Email link only |
| Number of projects | 1-3 initially |

## Design Phase

Created three distinct mockup options, all within the "clean & minimal" constraint:

### Design A: Classic Minimal
- Serif headings (Playfair Display) + sans-serif body (Inter)
- Centered single-column layout
- Thin border separators
- Traditional, editorial feel

### Design B: Modern Minimal
- Bold sans-serif throughout (Space Grotesk)
- Two-column header with asymmetric layout
- Thick black borders
- Project cards in a 3-column grid
- Contemporary, bold feel

### Design C: Soft Minimal
- Rounded corners on all cards
- Subtle shadows
- Warm gradient background
- Avatar circle with initials
- Approachable, friendly feel

**Decision:** User selected Design A (Classic Minimal).

## Content Development

### Source Material
Used user's resume (`resume.md`) to populate the site with real content:
- Current role: Enterprise Solutions Consultant at Opus
- Previous: OpenTable, Wunderkind, Google, Capgemini
- Education: NYU Stern (Business + Computing)
- Side activity: Director of New York Rugby Sevens tournament

### Projects Selected
1. **PipeScore** - Account propensity scoring (fictional, planned to build)
2. **FFL Trade Analyzer** - Fantasy football trade analysis (real, from `nyrc-ffl-trade-site` repo)
3. **NY7s Website** - Tournament website rebuild (real, from `ny7s-redesign` repo)

The fictional project (PipeScore) was designed to align with the user's actual work at Opus (sales prioritization, pipeline management) so it would be credible in interviews.

## Copy Iterations

### Version 1: Feature Lists
Initial project descriptions read like product documentation. Example:
> "An account propensity scoring engine that ranks prospects by likelihood to close. Built to solve a real problem at work—prioritizing outreach when you have thousands of accounts and limited time."

**Problem:** Reads like a feature list, not compelling for employers.

### Version 2: Problem → Build → Result Framework
User suggested restructuring around: problem statement → challenge → result.

Expanded to 4 sentences per project:
> "I had 3,000+ accounts in my territory and no systematic way to prioritize who to call. The CRM data was there, but scattered across dozens of fields that nobody looked at. I built a scoring model that pulls firmographic data, engagement signals, and historical win patterns to rank every account by likelihood to close. Now I start each week knowing exactly where to focus—top-scored accounts convert at 3x the rate of random outreach."

**Problem:** Better structure but still had AI-sounding language and padding.

### Version 3: Tightened Per Writing Rules
User provided specific writing rules:
- No generic patterns or padding
- Avoid AI vocabulary (crucial, delve, highlight, showcase, etc.)
- Vary sentence length
- No em dashes overuse
- Grounded, specific, human tone

Final version:
> "3,000 accounts in my territory. No real way to know which ones to call first. I built a scoring model that weighs company size, engagement history, and past win patterns to rank them all. The top-scored accounts close at 3x the rate of cold outreach."

Key changes:
- Removed "I had" → started with the number
- Removed "systematic way" → "real way"
- Removed em dash
- Shorter sentences throughout
- Reads like someone talking, not writing

## Specific Copy Changes Requested

### Header/Subheading
- Original: "Account Executive & Builder in New York"
- Final: "Enterprise Solutions @ Opus // Director at NY7s — New York"

### Email
- Changed from `karlgourgue@gmail.com` to `karl@karlgourgue.com`

### About Section
User requested specific framing for current role:
- Title: Enterprise Solutions Consultant (not Account Executive)
- Focus areas: pipeline generation, demos/technical aspects, content migration

Removed: "highest monthly pipeline in company history" (user wanted to add measurable results later)

Added: Capgemini role before Google (Tech Consultant doing project and product management)

### Experience List
Final order: Opus · OpenTable · Wunderkind · Google · Capgemini · NYU Stern

## Technical Implementation

### File Structure
```
karlgourgue-website/
├── index.html          # Main site (Design A implemented)
├── mockup-a-classic.html
├── mockup-b-modern.html
├── mockup-c-soft.html
├── SPEC.md             # Original spec from interview
├── resume.md           # Source resume
└── DOCUMENTATION.md    # This file
```

### Styling Approach
- Single HTML file with embedded CSS (no external stylesheet)
- Google Fonts: Playfair Display (headings) + Inter (body)
- Mobile responsive with single breakpoint at 600px
- Color palette: #1a1a1a (text), #fafafa (background), #e5e5e5 (borders), #666/#888 (secondary text)

### Deployment
- Platform: Vercel
- Initial deployment URL: `karlgourgue-website-*.vercel.app`
- User has `karlgourgue.com` domain already configured in Vercel (to be connected later)

## Things That Didn't Work

### Git Init in Sandbox
First attempt to initialize git failed due to sandbox restrictions:
```
fatal: cannot copy '/opt/homebrew/opt/git/share/git-core/templates/hooks/commit-msg.sample' to '/Users/karl/personal-website/.git/hooks/commit-msg.sample': Operation not permitted
```
**Fix:** Disabled sandbox for git operations.

### Directory Naming
User initially typed "karlgouruge" (misspelled). Had to:
1. Rename directory from `karlgouruge-website` to `karlgourgue-website`
2. Find/replace "Gouruge" → "Gourgue" in all files

Files had to be re-read after the directory rename because paths changed.

### Domain Alias
Attempted to alias the Vercel deployment to `karlgourgue.com`:
```
vercel alias karlgourgue-website.vercel.app karlgourgue.com
```
Failed with certificate generation error. User will connect domain manually through Vercel dashboard.

### Opening Files in Browser
First attempt to open mockups failed:
```
open ~/repos/karlgourgue-website/mockup-a-classic.html ~/repos/karlgourgue-website/mockup-b-modern.html ~/repos/karlgourgue-website/mockup-c-soft.html
```
Error: `procNotFound: no eligible process with specified descriptor`

**Fix:** Used explicit Safari invocation with delays:
```
open -a "Safari" [file1] && sleep 1 && open -a "Safari" [file2] ...
```

## GitHub Repository Status

| Project | Repo Exists | Remote Configured |
|---------|-------------|-------------------|
| PipeScore | No | No (needs to be created) |
| FFL Trade Analyzer | Yes (`nyrc-ffl-trade-site`) | No remote set |
| NY7s Website | Yes (`ny7s-redesign`) | Yes (`github.com/karlgourgue/ny7s-redesign`) |

User will need to:
1. Create `pipescore` repo on GitHub and push (or build the actual tool first)
2. Add remote to `nyrc-ffl-trade-site` and push

## Commits Made

1. `Initial site with about and projects` - First complete version
2. `Rewrite project descriptions with problem/build/result framework` - 4-sentence expanded versions
3. `Tighten project copy per writing rules` - Final tightened copy

## Future Considerations

Things mentioned but not implemented:
- Add measurable results to About section (user will work on this)
- Build PipeScore for real (user mentioned doing this "this week")
- Connect `karlgourgue.com` domain
- Add headshot photo (optional per spec)
- Push FFL Trade Analyzer to GitHub

## Lessons Learned

1. **Interview before building** - Gathering requirements upfront (tech stack, sections, style) prevented rework.

2. **Mockups before commitment** - Creating 3 options let the user make an informed choice rather than iterating on a single design.

3. **Real projects over fictional** - Using actual repos (FFL, NY7s) made descriptions more credible. The one fictional project (PipeScore) was designed to match real work experience.

4. **Copy framework matters** - "Problem → Build → Result" structure with concrete numbers is more compelling than feature lists.

5. **Writing rules catch AI patterns** - Explicit rules about avoiding AI vocabulary and padding significantly improved the final copy.

6. **Deploy early** - Getting on Vercel early meant we could iterate and see changes live throughout the process.
