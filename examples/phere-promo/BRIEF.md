# Phere promo: video-studio demo

A real run of the video-studio workflow: a 16-second landscape promo for Phere (phere.tech), a wedding
planning and family ledger app for Indian families, built from the app's actual screens.

## Brief

- **Audience:** families planning a wedding, and developers looking at what video-studio produces.
- **Message:** the wedding's money, guests and shagun live in one place.
- **Format:** 1920×1080, 30 fps, 16 s, no voice or music (it doubles as a silent README GIF).
- **Engine:** HyperFrames (HTML/CSS, Apache-2.0). Chosen over Remotion because this is a standalone motion
  piece, not a React project.
- **Assets:** real Phere screens with demonstration data (dashboard, guests, shagun register), the official
  logo, OFL fonts Instrument Serif and Outfit. Nothing generated, no paid services.
- **Brand:** cream ground `#FBF5EA`, maroon `#7A1530`, gold `#C9A23A`, ink `#2A1A12`. The CTA is
  "Start your free trial today." Every screen is labelled "Actual Phere screen · demonstration data".

## Story

1. Problem: the wedding budget lives in five notebooks.
2. Turn: Phere puts budget, guests and shagun on one phone.
3. Payoff: one place for the whole wedding. Start your free trial today.

## Shot list

| # | Time | Purpose | Visual | Copy | Motion | Transition |
|---|---|---|---|---|---|---|
| 1 | 0.0–3.0 | Hook: the problem | Cream ground, type only | "The wedding budget lives in *five notebooks.*" | Lines rise in 0.5 s apart; keyword lands larger in maroon italic | Type slides up and out |
| 2 | 3.0–6.0 | Budget | Phone, right; dashboard screen | "Budget, paid and pending." / "One card shows where the money stands." | Phone rises in; copy fades up | Screen wipes up |
| 3 | 6.0–9.0 | Guests | Same phone; guests screen | "Every household. Every RSVP." / "Search a family, see who is coming." | Screen slides up inside the phone | Screen wipes up |
| 4 | 9.0–12.0 | Shagun | Same phone; shagun register | "Every shagun, found by name." / "Who gave what, at which function." | Screen slides up inside the phone | Phone and copy fade |
| 5 | 12.0–16.0 | Payoff and CTA | Logo, centre | "One place for the whole wedding." / "Start your free trial today." / phere.tech | Logo scales in, lines follow | Holds to the end |

## Asset manifest

| File | Source |
|---|---|
| `assets/screens/dashboard.jpg` | Phere home dashboard, captured 2 Nov 2026 from the app's own components with demonstration data, scaled to 786 px wide |
| `assets/screens/guests.jpg` | Phere guests list searched for "Sharma", same method |
| `assets/screens/shagun.jpg` | Phere shagun register searched for "Verma", same method |
| `assets/phere-logo.png` | Official Phere logo (maroon), scaled to 900 px wide |
| `assets/fonts/*` | Instrument Serif and Outfit, SIL Open Font License (licence files beside them) |

The Phere screens and logo belong to Phere and are included only to show this example. They are not covered
by the repository's MIT license.
