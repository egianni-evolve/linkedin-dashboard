# Changelog

## 2026-07-04 — SHIPPED

### Accomplished
- A live, single-file dashboard that turns the raw LinkedIn export into strategic reads: a decision-maker-heavy network (39% formal Director/VP/C-suite, 52% with founders), AI and Legal the fastest-growing segments, posting correlated with growth (r = 0.61), and, as of July 2026, inbound connection requests overtaking outbound.
- Survived two full data cycles (March 2026 build, June correction, July refresh), proving the refresh workflow: re-run `analyze.py`, update the arrays, verify rendered output, push.

### Harder than expected
- Keeping derived numbers honest. The June re-review found six hard-number errors in the original build; the July refresh hit LinkedIn renaming export CSVs (member-ID suffixes) and a Chart.js grid-blowout race.

### Surprises
- The inbound flip: 65% outbound invitations in February, 58% inbound by June, with the network still adding 46-52 connections/month during a near-zero posting stretch.
- Erika's own profile pruning (76 → 38 skills) showing up in the data.

### Lessons
- Re-derive every metric from raw data on each cycle; don't trust prior numbers or agent-reported values.
- Expect LinkedIn export format drift between pulls; check filenames and headers before re-running analysis.
- (Neither is a third strike; nothing promoted to scar-tissue.)

### Live at
- https://egianni-evolve.github.io/linkedin-dashboard/
- https://github.com/egianni-evolve/linkedin-dashboard

## 2026-07-04 — Data refresh: Jul 3, 2026 export (Claude Fable 5)
Re-derived every metric from the new Complete export (Jul 3, 2026) and updated all charts and narrative. Totals include data through Jul 3; monthly trend windows end at June 2026, the last full month. Headline moves since February: connections 3,811 → 3,998; certifications 35 → 40; r = 0.64 → 0.61; seniority headline now 39% formal Director/VP/C-suite (52% with founders). Biggest story: the inbound/outbound invitation balance flipped, with 58% of the last six months' invitations inbound (was 65% outbound) and 108 of 148 Apr-Jun connections initiated by others. Also hardened the dashboard grid against a Chart.js column-blowout race (minmax(0,1fr)), refreshed the skills card (profile pruned 76 → 38 skills), and updated analyze.py for LinkedIn's new member-ID-suffixed CSV names.

## 2026-06-02 — Opus 4.8 re-review and correction
Independently re-derived every metric from the Feb 23, 2026 data export with Claude Opus 4.8 and corrected the dashboard. The original (Opus 4.6) story held; several hard numbers were fixed.

- Corrected counts: connections 3,810 → 3,811; comments 2,962 (was 3,005, an artifact of multi-line comment rows); certifications 33 → 35; companies followed 797 → 798.
- Reaction breakdown now includes the previously dropped "Maybe" type (33).
- Top-companies bars corrected upward (Akamai 73 → 77, Bixal 43 → 54, etc.); ranking unchanged.
- Audience-shift, function, seniority, and industry charts recomputed with a documented keyword ruleset. Audience-shift percentages now reported as a share of classifiable connections so the trend is comparable across reviews (AI 4% → 14%, Legal 2% → 13%, Founders 15% → 28%).
- Seniority headline reframed: 40% hold a formal Director/VP/C-suite title, 51% are decision-makers including founders.
- Relationship-depth buckets refreshed (within 1-2 of prior). Posting correlation re-confirmed at r = 0.64.
- Added an "About These Numbers" methodology note and updated the footer.

## 2026-03-28 — Initial dashboard
First LinkedIn insights dashboard (Opus 4.6), built from the Complete LinkedIn Data Export. Static single-file `index.html`, published to GitHub Pages.
