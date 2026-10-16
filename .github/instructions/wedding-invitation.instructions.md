---
description: "Use when creating, designing, editing, translating, or hosting the Amith G and Soumya M S wedding invitation: the invitation website (index.html, assets/), the 9:16 card (card.html), calendar (.ics) files, music, or GitHub Pages. Holds the confirmed event facts, approved wording, the traditional South Indian / Kannada design system, website behaviour, and the quality checklist."
applyTo: ["index.html", "card.html", "assets/**", "calendar/**", "audio/**"]
---
# Amith G and Soumya M S: Traditional Wedding Invitation

The project is a small static website, ready for GitHub Pages. It has two pages:

- **`index.html`** is the invitation as a modern, app-like website. It opens with temple doors and then shows a live countdown, a ceremony timeline with add-to-calendar, the venue with a map, bottom dock navigation, and background music (on by default).
- **`card.html`** is the classic 9:16 animated card, with browser printing available for a physical copy.

## 1. Confirmed facts (single source of truth)

Copy these exactly. Never change, round, or "correct" them, and never add facts that are not listed here.

| Ceremony | Kannada | Day & date | Time | Machine time (IST) |
|---|---|---|---|---|
| Reception | ಆರತಕ್ಷತೆ | Wednesday, 25th November 2026 | 7:00 PM onwards | `2026-11-25T19:00:00+05:30` |
| Muhurtham (wedding) | ಶುಭ ಮುಹೂರ್ತ | Thursday, 26th November 2026 | 8:00 AM â€“ 9:00 AM | `2026-11-26T08:00:00+05:30` to `2026-11-26T09:00:00+05:30` |

- **Groom**: Amith G, son of Smt. Manjula S (mother) & Sri. Shamaprasad S (father)
- **Bride**: Soumya M S, daughter of Smt. Rekha L (mother) & Sri. Lakshman Rao (father)
- **Couple**: Amith G and Soumya M S, always in this order.
- **Venue (both ceremonies)**: Gayatri Kalyana Mantapa, Gayatri Circle, Chitradurga â€“ 577501
- **Map link**: <https://www.google.com/maps/search/?api=1&query=Gayatri+Kalyana+Mantapa%2C+Gayatri+Circle%2C+Chitradurga+-+577501>

**Not provided, so do not invent:**

- gotra
- grandparents' or other relatives' names
- panchanga details (samvatsara, masa, tithi, nakshatra, lagna)
- RSVP contacts
- dress codes
- meal timings
- end time for the 25 November reception
- photos
- a wedding hashtag

Leave these out or ask the user. Once the user confirms a new fact, add it to this section. Never leave placeholder text such as "[Name]" on a finished page.

## 2. Wording

- English is the main language. Use Kannada for the invocation, shloka, title, ceremony names, and sign-off. Wrap Kannada in `lang="kn"`.
- The card also comes in an **English** version (`card.html?lang=en`, section 5) for guests who don't read Kannada. It writes the invocation, shloka, and title in English letters and leaves out the other Kannada lines:
  - `à¥¥ Sri Ganeshaya Namah à¥¥` (the à¥¥ marks use the Kannada font)
  - `Vakratunda Mahakaya Suryakoti Samaprabha à¥¤` / `Nirvighnam Kuru Me Deva Sarvakaryeshu Sarvada à¥¥`
  - `Shubha Vivaha` (title)
  - The ceremony names appear in English only, and the closing line "Eagerly awaiting your gracious presence" takes the Kannada sign-off's place.
- Keep the tone formal, warm, and reverent. Don't use slang, emojis, or hashtags.
- Use these Kannada strings verbatim. Don't write new Kannada sentences unless the user has reviewed them:
  - `à¥¥ à²¶à³à²°à³€ à²—à²£à³‡à²¶à²¾à²¯ à²¨à²®à²ƒ à¥¥`: Salutations to Lord Ganesha (invocation)
  - `à²µà²•à³à²°à²¤à³à²‚à²¡ à²®à²¹à²¾à²•à²¾à²¯ à²¸à³‚à²°à³à²¯à²•à³‹à²Ÿà²¿ à²¸à²®à²ªà³à²°à²­ à¥¤` / `à²¨à²¿à²°à³à²µà²¿à²˜à³à²¨à²‚ à²•à³à²°à³ à²®à³‡ à²¦à³‡à²µ à²¸à²°à³à²µà²•à²¾à²°à³à²¯à³‡à²·à³ à²¸à²°à³à²µà²¦à²¾ à¥¥`: Ganesha shloka
  - `à²¶à³à²­ à²µà²¿à²µà²¾à²¹`: Auspicious wedding (title)
  - `à²¤à²®à³à²® à²†à²—à²®à²¨à²¾à²­à²¿à²²à²¾à²·à²¿à²—à²³à³`: "Eagerly awaiting your arrival" (traditional sign-off)
- Approved English copy:
  - Lead: "With the blessings of the Almighty and our elders, we joyfully invite you and your family to the auspicious wedding of"
  - Couple block, one centred line each: "Amith G" / "son of Smt. Manjula S & Sri. Shamaprasad S" / "&" / "Soumya M S" / "daughter of Smt. Rekha L & Sri. Lakshman Rao". Keep the mother-first order the family gave. Don't write the parents' names in Kannada unless the family has reviewed the spelling.
  - Closing: "Eagerly awaiting your gracious presence" followed by "With love & regards, the families of Amith G and Soumya M S"
- Website strings set in `assets/app.js`:
  - Countdown end states: "The Muhurtham is happening now" (Thursday, 26th November, 8:00â€“9:00 AM IST), then "Thank you for your blessings".
  - Status chips, from the day before each ceremony: "Tomorrow", "Today Â· in Xh Ym", "Today", "Happening now", "Completed". Before that a ceremony shows no chip: the family asked to drop "In N days", and the countdown already shows the days left.
- Website interface copy (section titles, button labels, hints) may be reworded, but it must never add facts.
- Formats: write dates as "Thursday, 26th November 2026" and times as "8:00 AM â€“ 9:00 AM" (en dash, uppercase AM/PM). Spell the city "Chitradurga".

## 3. Design system: traditional South Indian (Kannada), shared by both pages

**Palette** (CSS custom properties)

| Token | Hex | Use |
|---|---|---|
| `--maroon` | `#6B0F1F` | silk frame, headings, Muhurtham plaque, dark sections |
| `--maroon-deep` | `#4A0A14` | strong text on ivory, QR code, `theme-color` |
| `--gold` | `#C9973A` | rules, line-art, borders |
| `--gold-light` | `#F0D58C` | text and ornaments on maroon |
| `--turmeric` | `#E8A317` | small accents, focus ring |
| `--marigold` | `#EE7F1A` | marigold flowers |
| `--leaf` | `#2F6B2F` | mango leaves |
| `--ivory` / `--sandal` | `#FFF8EA` / `#F3E2BF` | paper, light sections, and vignette |
| `--ink` | `#3B1F14` | body text |

**Typography** (Google Fonts, always with fallbacks)

| Role | Font |
|---|---|
| Couple's names (the largest text) | Great Vibes |
| Headings, labels, and the Chi. / Chi. Sow. honorifics (caps, letter-spaced) | Cinzel |
| Body, including the parents' lines (italic for the lead line and for "son of" / "daughter of") | Cormorant Garamond |
| Kannada | Tiro Kannada â†’ Noto Serif Kannada â†’ Nirmala UI |
| Website controls only (buttons, chips, dock, toast) | system UI font (`--f-ui`) |

**Motifs**: hand-built inline SVG in gold line-art with limited colour. Don't use photos, clip-art, or emojis.

- Mango-leaf **thorana** with marigolds across the top, plus hanging **temple bells**
- **Lord Ganesha** line-art with a dotted prabhavali (halo) above the invocation
- Maroon **silk** with a Kanjeevaram/Mysore-silk **zari temple border** (gold triangles). On the website the border is a strip between sections.
- **Kalasha** (pot, coconut, mango leaves) on both sides of the Muhurtham
- Ceremony icon: diya for Reception
- **Rangoli/kolam** corner fans and a faint **mandala** watermark behind the names
- Carved **temple doors** for the website intro
- Western wedding motifs (rings, champagne, doves) don't fit this theme. Don't use them.

**Hierarchy**: names > Muhurtham > ceremonies > venue > ornament text.

- Every date, time, address, and parent's name must stay readable on a phone. On the card that means at least 2.6% of the card width; the decorative shloka can be smaller.
- Use `--gold` text only when it is large or sits on maroon. Small text on ivory uses `--ink`, `--maroon-deep`, or `--gold-deep`.

**Motion** (gentle and devotional, never flashy, and alive on every screen):

- Ambient loops on both pages:
  - mango leaves sway and temple bells swing
  - the Ganesha halo glows softly and the diya flame flickers
  - the mandala turns slowly and sparkles twinkle beside the names
  - a sparse shower of marigold, rose, jasmine, and turmeric petals falls (pushpa vrishti). The petals stay behind the text and never block clicks.
- On the website, every section keeps something moving (see section 4), so no screen looks static on a phone.
- Animate only `transform` and `opacity`. Never move or fade text after its entrance; the one exception is each new countdown number dropping into its tile.
- Every guest gets the full motion, including phones that ask for reduced motion. Many Android battery savers and "Remove animations" switches ask for it without the guest choosing, and the invitation then looked frozen. Don't add a pause-animations button; the family doesn't want one.

## 4. Website: `index.html`

**Files**:

- `index.html`: markup plus inline SVG art.
- `assets/app.css`
- `assets/app.js`: vanilla, no dependencies.
- `assets/favicon.svg`

There are no frameworks and no build step. The only external resources are Google Fonts and the Google Maps embed. All paths are relative, so the site works under any GitHub Pages repository name.

**Sections, top to bottom**:

1. **Intro** (`#intro`, a modal dialog):
   - Two carved maroon temple doors under a thorana, with an arched plaque: Ganesha, invocation, à²¶à³à²­ à²µà²¿à²µà²¾à²¹, names, and the date.
   - The plaque has a single **Open invitation** button. That tap swings the doors open, starts the music (it is on by default), and the site rises in.
   - The doors play on every fresh visit and again on a reload. They are skipped when the guest comes back within the same tab (the back button, or returning from the card; `sessionStorage['sws-opened']`), for links with a `#section` hash, and when JavaScript is off.
2. **Home** (`#home`):
   - Thorana and bells, a slowly turning mandala, Ganesha, the invocation, à²¶à³à²­ à²µà²¿à²µà²¾à²¹, and the names (`h1#hero-title`).
   - The date and venue, then a live **countdown** to the Muhurtham.
   - **View events** and **Directions** buttons, with petals falling behind.
3. **Couple** (`#couple`): the shloka and lead line, then arch cards for the groom and bride (honorific, name, and parents) joined by an "&" medallion.
4. **Celebrations** (`#events`):
  - A Day 1 timeline (Reception) and the Day 2 Muhurtham plaque with kalashas.
   - Every ceremony has an **Add to calendar** menu (Google Calendar or `.ics`) and, from the day before, a live status chip. From 480 px wide the chip and the button share a line, with the button on the right under its menu, even when there is no chip. On phones the chip sits above the button.
  - An "Add all ceremonies" link downloads the combined `.ics`.
5. **Venue** (`#venue`): the address, **Get directions**, **Copy address**, the map QR code, and an embedded Google Map.
6. **Footer**: the Kannada sign-off and the English closing.
7. **Dock**: fixed bottom navigation (Home, Couple, Events, Venue) with a scrollspy, plus the music toggle when the audio file exists. The hero and footer reserve `--dock-space` so the dock never covers content.

**Behaviour** (`assets/app.js`):

- **Countdown**: counts down to 16 Nov 2026, 9:00 AM IST (`Date.UTC(2026, 10, 16, 3, 30)`) and ticks every second. When it reaches zero it shows the end states from section 2.
- **Status chips**: read each card's `data-start` and optional `data-end` (ISO times from section 1). Calendar days are counted in IST, so "Today" and "Tomorrow" stay right for guests abroad. Until the day before its ceremony a chip stays empty, and `.chip:empty` hides it. Chips refresh every 30 s.
- **Calendar menus**: `<details class="cal">`, one open at a time. A menu closes on an outside click, on Escape (focus returns to its button), or after a choice.
- **Copy**: uses the Clipboard API with a fallback, then shows a toast (`role="status"`).
- **Progressive enhancement**:
  - A head script adds `html.js`, and also `opened` when the doors should be skipped.
  - `app.js` sets `window.SWS_READY` and adds `revealed` when the site is shown.
  - If `app.js` hasn't started after 6 s, `js` is removed and the plain page shows.
  - Controls that need JavaScript carry `.js-only`.

**Accessibility**:

- **While the intro is up**: `#app` is `inert`. Tab reaches **Open invitation** first, and Escape also opens the invitation. After opening, focus moves to the names heading (`tabindex="-1"`).
- **Structure**: sections are labelled landmarks, dock links use `aria-current`, and decorative SVGs are `aria-hidden`. The countdown digits are hidden from screen readers, which hear one static sentence instead.
- **Targets and focus**: tap targets are at least 44 px, and the focus ring is a 3 px turmeric outline.

**Motion (website)**:

- **Doors**: swing open slowly, over about 4 s, and the site is ready after 4.3 s (`app.js` timers 900, 3600 and 4300 ms). The family asked for an unhurried opening; a much longer one would keep guests waiting.
  - Each door has its own `perspective()` inside its transform. WebKit (Safari and every iPhone browser) ignores a parent's perspective here and would squash the doors flat.
  - The depth is `--door-depth: clamp(480px, 125vw, 1800px)`, so the swing looks equally deep on phones and desktops.
- **Hero**: items rise in sequence (`html.revealed` with `[data-rise]` and `--i`).
- **Sections**: reveal on scroll (`[data-reveal]` with an optional `--delay`). In Celebrations, each day title, ceremony card, the Muhurtham plaque, and the "Add all" link reveal one by one.
- **Scrolling**: dock and button links scroll smoothly (`html.smooth-scroll`, added on `load`). Deep links such as `â€¦/#venue` jump straight to the section, so they don't animate past the hero or stop short when web fonts load.
- **Ambient loops**: as listed in section 3, plus one or more in every section:
  - **Intro**: a soft ring pulses around **Open invitation**.
  - **Home**: each new countdown number drops into its tile.
  - **Section ornaments**: they breathe gently.
  - **Couple**: the medallions turn, and a ring ripples out from the "&".
  - **Celebrations**: a light travels down the timeline, and the timeline dots ripple. The Reception diya flickers. The kalashas float and the Muhurtham plaque glows.
  - **Venue**: the pin bounces.
  - **Drifts**: `.drift` layers (filled by `app.js` from `data-count`) send petals down the ivory sections and diya sparks up the maroon ones and the footer, behind the content (`.section > .container` sits above them).

**Shared artwork**:

- The blocks between `<!--@NAME-->` and `<!--/@NAME-->` markers (`MANDALA`, `INTRO-THORANA`, `HERO-THORANA`, `QR`) are copies of art from `card.html`.
- The Ganesha, kalasha, and icon symbols live in the sprite at the top of `index.html`.
- When artwork changes, update both pages.

## 5. Card: `card.html`

- **Self-contained**: one page with inline CSS, inline SVG, and a small inline script for the music button. A fixed "Invitation" link returns to `index.html`.
- **Artboard**: 9:16, designed at 540 Ã— 960 CSS px. It scales with container query units (`cqw`), so the card looks the same on every screen.
- **Layout**: a single portrait card on one centred axis, from top to bottom:
  1. Thorana and bells
  2. Ganesha, invocation, and shloka
  3. à²¶à³à²­ à²µà²¿à²µà²¾à²¹ and the lead line
  4. Names (hero): a small "Chi." / "Chi. Sow." beside each name (the name itself stays on the centre axis), with that person's parents on the line below
  5. Muhurtham plaque (second hero): maroon with gold text, a kalasha on each side
  6. "Wednesday, 25th November 2026", then three ceremony columns in time order: icon, English name, Kannada name, time
  7. Venue with the map QR code and link
  8. Kannada sign-off and English closing
- **Entrance**: the card fades and settles in, the thorana drops in, and the sections rise in one after another from top to bottom.
- **English version**: adding `?lang=en` to the URL (the head script adds `html.lang-en`) shows the English card from section 2.
  - Elements with class `kn` are hidden, and `.en-only` elements appear: the English invocation, shloka, and title, plus a second diamond so the plaque reads "â—† Muhurtham â—†". Everything else is shared, so a change to the card changes both versions.
  - Without `?lang=en` the card is exactly the Kannada + English card.
- **Print**: uses `@page { size: 5.625in 10in; margin: 0 }` with `print-color-adjust: exact`. Print hides motion and drops the simulated paper grain for clean output.

## 6. Music (both pages)

- **When it plays**:
  - It is on by default; the family asked for this. The guest turns it off with the dock's music button or the card's round button, and that choice lasts for the visit (`sessionStorage['sws-music-off']`, shared by both pages).
  - Browsers allow sound only after a tap or key press, so on the website it starts with the **Open invitation** tap. When the doors are skipped, and on the card, it starts at once where the browser allows it (Chrome does after a tap on the previous page). Otherwise it starts with the guest's first tap or key press anywhere; a tap on the music button itself is left to the button.
  - It rests while the page is hidden (another app or tab) and carries on when the guest comes back.
  - It fades in, starts at the `data-play-from` second set on the `<audio>` element (35, because the family asked to skip the recording's slow opening; a new phrase begins there), goes back there on reaching `data-play-to` (266.5, once the last note has rung out, which skips the silent ending) or the end of the file, and fades out on pause. (It is not `data-start`: the status chips select every `[data-start]` element.)
- **The recording**: *Haratanaya Sree*, a composition of Veena Raja Rao in raga Nata, played on the veena by his daughter and disciple Veena Kinhal, from *Tribute to Veena Raja Rao* (2009, 4 min 33 s). She released it into the public domain on the [Internet Archive](https://archive.org/details/VeenaKinhalTributeToVeenaRajaRao) (it is also on Free Music Archive), so it is free to publish. `audio/haratanaya-sree.mp3` is the archive's original MP3 (MD5 `17d2ae3db528ee5489be5e212f7726f6`). It plays as background audio only; no video player is ever shown.
  - The family first wanted *Seetha Kalyana Vaibhogame*, but every recording they found is copyrighted: Phani Narayana's instrumental (Strumm Entertainment; YouTube `OhDBfhbX5L4`, `D-4bPaUMaB4`, `z6-zn6WX2DY`), Karthick Iyer's violin (`bSv6F6a_214`), Veena Srivani (`48Wpqaqtch4`), Shreya Ramaswamy's veena (`XYPFVoIrecU`), and the *Nadamohanam* nadaswaram by Blue Planet Cinema (`I1mLL6AlQXA`). Wikimedia Commons, Free Music Archive and the Internet Archive have no free recording of it except a 1975 vocal concert, which sounded too old (checked October 2026).
  - To switch to one of those, the family needs the audio file and permission from whoever owns the recording (the label, producer or artist). Then replace the file, set `src` and both `data-play-*` values on both pages (`data-play-from="0"` plays from the beginning; without `data-play-to` it plays to the end), and update the comments beside both `<audio>` elements.
  - Never download, rip, bundle, or hide-play audio from YouTube, streaming services, or film soundtracks. YouTube allows playback only in a visible player, which the family does not want.
  - No credit is shown on either page; the family asked for it to be removed, and public-domain music needs none. The source is recorded here and in the comment beside each `<audio>` element.
- **If the file is missing**: every music control hides itself, so no page ever shows a broken control.
  - Both pages detect the file with `loadedmetadata`/`error` events plus an HTTP `HEAD` check, because iOS doesn't preload audio.
- **Controls**: they use `aria-pressed` and a "Play/Pause music: Haratanaya Sree" label or title, and an equalizer animation runs while the song plays.

## 7. Calendar files (`calendar/`)

- **Files**: `reception.ics`, `muhurtham.ics`, and `amith-weds-soumya-wedding.ics` (both ceremonies).
- **Times**: in UTC (IST âˆ’ 5:30). For example, 10:30 AM IST is `20261125T050000Z`.
  - Only the Muhurtham has a `DTEND` (`20261126T033000Z`). Reception has no `DTEND`, because no end time was given.
- **Event fields**:
  - SUMMARY: "<Ceremony> - Amith G and Soumya M S's wedding"
  - LOCATION: the full venue
  - DESCRIPTION: the IST date and time, the venue, and the map link
  - UID: a stable `<ceremony>-<yyyymmdd>@amith-weds-soumya`
- **Format**: CRLF line endings, lines folded at 75 octets, and `,` and `;` escaped.
- **Google Calendar links**: `https://calendar.google.com/calendar/render?action=TEMPLATE&text=â€¦&dates=<start>/<end>&ctz=Asia/Kolkata&location=â€¦&details=â€¦`. Times are local IST; start-only ceremonies use the start time for both values.

## 8. Output, local preview, and hosting

```text
index.html  card.html  .nojekyll  .gitattributes
assets/     app.css, app.js, favicon.svg
calendar/   three .ics files
audio/      haratanaya-sree.mp3 (public domain; see section 6)
.github/     project guidance
```

- **QR code**: `assets/venue-qr.svg` is shared by the website and card and encodes the map link with a four-module quiet zone. If the link changes, regenerate this SVG with Python `segno` using `segno.make(url, error="m").svg_inline(dark="#4A0A14", border=4)` and update its description and both link targets.
- **Local preview**: run `python -m http.server 8000 --bind 127.0.0.1` in the project folder, then open <http://127.0.0.1:8000/> (website) or <http://127.0.0.1:8000/card.html> (card). Opening the files directly also works, but the music check and the share URL behave best over HTTP.
  - Python's server ignores byte-range requests, so Chrome and Edge can't seek there: they play the song from 0:00 instead of 0:35 and don't skip the silent ending. GitHub Pages supports ranges, so the live site does both in every browser.
- **GitHub Pages**:
  - Live site: <https://amith-weds-soumya.github.io/>. Repository: <https://github.com/amith-weds-soumya/amith-weds-soumya> (public).
  - Pages deploys the `main` branch from `/ (root)`, so a push to `main` goes live within a minute or two.
  - `.nojekyll` makes Pages serve the files as they are.
  - `.gitattributes` keeps the CRLF line endings that `.ics` files need, and marks the images, PDF, and audio as binary.
  - Publish only audio the family has the rights to share (see section 6).
  - `index.html` has `og:url` for rich link previews. If the site moves, update it.

## 9. Quality checklist (verify before finishing)

- [ ] Both ceremonies show the exact day, date, and time on both pages.
- [ ] The names are spelled "Amith G" and "Soumya M S". The venue and "Bengaluru â€“ 560079" are spelled exactly as in section 1.
- [ ] Each set of parents appears under the right child, spelled exactly as in section 1 with "Smt." and "Sri.", and "Chi." / "Chi. Sow." sit beside the groom's and bride's names.
- [ ] Kannada renders in a Kannada font, with no tofu boxes and no broken conjuncts.
- [ ] Text contrast follows the rules in the Hierarchy paragraph of section 3.
- [ ] Website:
  - [ ] No horizontal scrolling at 360 px or 390 px wide or on desktop, and the dock never covers content.
  - [ ] No awkward one-word line endings.
  - [ ] The countdown and chips are correct. Check them with a shifted clock before 14 Nov (no chips), on 14 Nov, on 15 Nov in the morning and afternoon, during the Muhurtham, and after it.
  - [ ] The calendar menus, the `.ics` downloads, and Copy address all work.
  - [ ] Keyboard: Tab reaches **Open invitation**, Escape opens the invitation, and focus lands on the names.
  - [ ] Every animation that runs on desktop also runs on phones, including phones set to reduce motion, and every section has visible motion.
  - [ ] Phones (360â€“412 px wide, plus landscape) show the doors turning in 3D, the garland and bells swaying, and no horizontal scrolling. Check with a WebKit (iPhone) and a Chromium (Android) engine.
  - [ ] Without the MP3, the only console errors are the expected 404s for it.
- [ ] Card: nothing overflows or touches the frame, the thorana, or the bells. The animations never appear in the PNG or PDF.
- [ ] Both card versions: the English card (`card.html?lang=en`, the `-english` files) shows no Kannada letters, and the Kannada + English card shows no English-only lines.
- [ ] Music is on by default: it starts with **Open invitation** (or the first tap when the doors are skipped, and on the card), plays as background audio with no visible player, starts at `data-play-from` (35 s), goes back there from `data-play-to` (266.5 s), toggles play/pause with a fade, and stays off for the visit once the guest turns it off. Its controls are hidden when `audio/haratanaya-sree.mp3` is missing. The recording is public domain or properly licensed, no credit text is shown, and nothing is taken from YouTube or streaming services.
- [ ] Generate card exports only when requested; visually check both language versions when generated.
- [ ] No invented facts and no visible placeholders.


