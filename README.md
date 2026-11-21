# Portfolio v2 — Rizki Jack

Rebuilt static portfolio, replacing the live rizkijack.pages.dev design.
Single self-contained `index.html` (inline CSS, tiny copy-to-clipboard script only),
plus `assets/cv-rizki-jack.pdf` (CV v14).

## Design

"Broadsheet CV": newspaper-style masthead with dateline, numbered sections
(00 Main goal, 01 Experience, 02 Skills, 03 How I work, 04 Projects,
05 Background and availability, 06 Hire me), sticky left-hand section labels,
hairline rules, facts strip as a bordered table, projects as meta-left /
text-right entries. Fraunces (serif display) + Inter (body). Paper white
#FBFAF7, near-black ink, one muted accent — deep green #1D4D2B used only for
the availability dot, section numbers, and "Core" tags. No shadows, no rounded
corners, no gradients, no emoji, no images, no testimonials, no filler.

Template patterns borrowed (layout ideas only, no assets/text copied):
- Wix "Creative CV" / Personal Website templates: one-page CV, sections
  About–Experience–Skills–Projects–Contact, downloadable resume button.
- WordPress.org "CV Resume Portfolio" / "Resume Kit": structured sections,
  two-column label/content layout, minimalist grid.
- WordPress.org "Prime Portfolio Resume": project showcase with meta
  (kind/year/links) beside the description, skills blocks.

## Content

Same facts as the live site (verified against /tmp/rizkijack-home.html),
updated to CV v14 where the CV changed: Skills now 24 items in three groups
(Web3 & Community, Website & Development [new], Administration & Technical),
and the hero lede adds the v13 sentence "I also build websites — I coded a
WordPress theme from scratch and tested it on a local install." All links
verified against the original (24 hrefs; only the old font stack, styles.css,
and favicon data-URI differ, intentionally).

## Known gaps

- Project images and the header profile photo from the old site could NOT be
  re-downloaded: rizkijack.pages.dev is unreachable from this VM right now
  (curl HTTP 000, cbx NS_ERROR_NET_RESET; other hosts work). The rebuild is
  therefore text-only by design. If the images are wanted back, re-add the
  originals from the previous deployment at deploy time.
- "Website design" is marked Core in the new Website & Development group —
  judgement call, matches his current Freelancer headline direction.

## Verify locally

    cd ~/workspace/portfolio-v2 && python3 -m http.server 8090
    # then open http://127.0.0.1:8090/ (cbx screenshots in screenshots/)

## Deploy (parent step — NOT done here)

Wrangler is unauthenticated on this VM (`wrangler whoami` → not logged in).
Deploy needs Cloudflare login first, then e.g. `wrangler pages deploy .`
against the existing project, or push to the connected repo if the Pages
project is Git-backed.
