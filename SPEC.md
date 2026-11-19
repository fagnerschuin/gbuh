# GODBLESS US HANDYMAN LLC · call-first AC service site

## 0. Brief
A one-page site: Hero, Emergency, Services, Common problems, Request service, Service area, About, Contact, Footer.
Homeowners in Winter Park and Orlando whose AC is struggling, many on a phone in a warm house.
Aesthetic: plain-spoken, cool and calm, trustworthy, local.
Signature: **the phone number is the headline-scale type.** In the hero it sits at display size under the H1 and can be tapped. On mobile, a fixed bottom call bar keeps it one tap away on every screen.
Honesty rule: publish only what the sources support. Unconfirmed items (email, 24/7 hours, extra cities, reviews, years in business, licensing) ship as `hidden` blocks marked `data-confirm`. The owner turns each on after checking it. The form stays visibly "not yet connected" until `FORM_ENDPOINT` is set.

## 1. Stack
Single `index.html` with inline CSS and JS, no libraries. Images are local WebP files in `img/`. Icons are inline SVG.

## 2. Fonts
Inter Tight 400/500/600 handles display, UI and body. Instrument Serif italic 400 is for accent words only (1–3 per heading).
`https://fonts.googleapis.com/css2?family=Instrument+Serif:ital@1&family=Inter+Tight:wght@400;500;600&display=swap`

## 3. Tokens
--bg #F6F4EF (paper) · --ink #0E2230 (navy, matches the polos in the imagery) · --ink-2 rgba(14,34,48,.72) · --muted rgba(14,34,48,.56) · --line rgba(14,34,48,.12) · --card #FFFFFF · --deep #0E2230 (dark sections), with text #F6F4EF at 100/78/56 · --accent #0B63C4 (coolant blue). The accent appears only on the primary CTA fill, the status dots and the icon strokes in the issue list. White on the accent = 5.6:1.
Selection: rgba(11,99,196,.22). Focus ring: 3px solid #0B63C4 with a 3px offset (on dark: #8CC4FF).

## 4. Layout
Container max 1240px; gutters 20 / 32 / 48px. Section padding clamp(72px, 10vw, 136px).
Radius: 28px for media frames, 20px for cards, pill for buttons.
Card shadow: 0 1px 2px rgba(14,34,48,.06), 0 8px 24px rgba(14,34,48,.06).

## 5. Nav
Sticky top, 72px tall, bg rgba(246,244,239,.86) + blur(14px), with a bottom hairline after scrollY > 8.
Wordmark: "GODBLESS US" in 15px/600 at +0.04em tracking, then "HANDYMAN LLC" in 10.5px/500 at +0.22em and 56% opacity on a second line. A 28px navy circle carries an inline SVG snowflake/fan glyph.
Links: Services · AC problems · Service area · About · Contact (14px/500, underline grows from the left).
Right: a solid accent pill "Call (407) 456-1329" (14px/600, 12×20px padding).
Under 960px: a 44px burger opens a full-width sheet with the links at 28px. It closes on link click, Esc and resize, and locks body scroll while open.

## 6. Hero (grid 5fr / 7fr, gap 48px, min-height calc(100dvh - 72px) capped at 860px)
Left column, vertically centred:
- Eyebrow: a 6px accent dot, then "Residential AC service · Winter Park & Orlando, FL" (12.5px/500, +0.14em, uppercase, muted).
- H1: "Warm house? / Let's get it *cooling* again." — clamp(40px, 5.6vw, 80px)/1.0, −0.035em, weight 500. "cooling" is set in Instrument Serif italic in the accent colour.
- Sub: "AC repair, maintenance, replacement, mini-split and duct cleaning for homes in Winter Park and the Orlando area. Call to talk to us about what your system is doing." 17px/1.55, ink-2, max 34rem.
- Phone block (the signature): the label "Call or text" (12px label, muted), then "(407) 456-1329" as a `tel:` link at clamp(36px, 4.6vw, 60px)/1, −0.03em, weight 500, with tabular numerals and a 2px underline at 20% that turns accent on hover.
- CTA row: a primary accent pill "Call now" (phone icon) and a ghost pill "Request service" that links to #request.
Right column: a 28px-radius frame at 4/5 aspect (desktop) holding condenser-repair.webp with object-position 70% 50%. A small paper caption chip in the bottom-left corner reads "Illustrative image".
Mobile: a single column with the image first at 4/3 aspect and object-position 75% 50%, then the copy. The H1 is 40px.

## 7. Sections
- **Emergency** (dark --deep band): The H2 is "AC not working? *Here's what to do.*" A three-step row follows: 01 Call (407) 456-1329 · 02 Tell us what you're noticing · 03 Share your address area. The safety note reads: "If you smell burning or see water near electrical parts, switch the system off at the thermostat before you call." The 24/7 line is hidden behind `data-confirm`. No image: type only.
- **Services**: The H2 is "What we *work on*". There are five cards in a 6-column grid with spans 3/3 on the top row and 2/2/2 below. Each card has a 3/2 image, a "01" index, an H3 and a 2-sentence body. The cards are Repair = refrigerant-gauges, Maintenance = coil-cleaning, Installation & replacement = condenser-replacement, Ductless & mini-split = minisplit-install, Air-duct cleaning = air-handler-filter.
- **Common problems**: The H2 is "Signs it's time to *call a technician*". A two-column layout puts a sticky image (minisplit-check) on the left and a 7-row numbered list on the right. Each row has a 20px accent stroke icon, a title (18px/600) and a one-line description. The disclaimer reads "This list helps you describe what you're seeing. It isn't a diagnosis."
- **Request service**: The H2 is "Request *service*". The left column has the call card. The right column has a form with name, phone, email, city/ZIP, a service select and a message. While FORM_ENDPOINT is empty, the submit button is disabled and a status chip says "Online requests aren't connected yet. Please call (407) 456-1329."
- **Reviews**: an `hidden` section (`data-confirm="reviews"`) with an empty list and comments only. It contains no made-up text.
- **Service area**: Winter Park and Orlando appear as large type (clamp(40px, 7vw, 104px)). Below them: "Near Winter Park or Orlando? Call and we'll tell you if your address is in our area." Other cities are hidden behind `data-confirm`.
- **About**: "A home-services company, focused on *air conditioning*." Two short paragraphs with no claims. The years, license and insurance lines are hidden behind `data-confirm`. Image: thermostat-homeowner.
- **Contact**: a definition list with Phone, Service area, Email (hidden) and Hours (hidden).
- **Footer**: the name, phone and area; the note "Photos on this site are illustrative, not of our staff, customers or completed jobs."; the copyright year. The legal links stay hidden until the owner supplies them.
- **Mobile call bar** (<960px): fixed bottom with safe-area padding. It has a full-width accent button "Call (407) 456-1329" and a 52px secondary "Request" button.

## 8. Motion
The hero blur-rises in this order: nav → eyebrow → H1 → sub → phone → CTA. The first item has a 0.08s delay and each later one adds 0.1s. Each step lasts 0.8s with cubic-bezier(.22,1,.36,1), from translateY(24px) + blur(8px) + opacity 0. The image settles from scale 1.06 to 1 over 1.6s.
Sections reveal once on scroll with IntersectionObserver at threshold 0.15: y 28px over 0.7s, with a 0.08s stagger between siblings. The resting state stays visible without JS (the `.js` class gates it).
Hovers: buttons darken by 8% and scale to 0.97 on :active. Card images zoom to 1.04 over 600ms.
With reduced motion, everything appears in its final state and nothing transitions.

## 9. SEO / a11y
Title: "AC Repair in Winter Park & Orlando, FL | GODBLESS US HANDYMAN LLC". There is a meta description, OG tags and a skip link.
JSON-LD `HVACBusiness` includes only the name, telephone, areaServed [Winter Park, Orlando] and the service catalog. It has no address, rating, hours or email.
Every form input has a `<label>`. Alt text describes what each image shows and does not claim the people are company staff.
