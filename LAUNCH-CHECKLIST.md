# Before launch: confirm with the owner

Anything that isn't verified yet is already in `index.html`, but it's hidden or left out. Search the file for `data-confirm` and `OWNER CONFIRM`.

| Item | Where in index.html | How to turn it on |
|---|---|---|
| 24/7 emergency availability | Emergency section, `data-confirm="emergency-24-7"` | Remove `hidden` |
| Business hours (24/7) | Contact list, `data-confirm="hours"` | Remove `hidden`, or edit the hours text |
| Email `Leonise12@yahoo.com` | Contact list, `data-confirm="email"` | Remove `hidden`; also add `"email"` to the JSON-LD |
| More cities (Kissimmee, Clermont, Davenport…) | Service area list (comment) | Add `<li>` items and `areaServed` entries in the JSON-LD |
| 25+ years, licensed / insured / bonded | About, `data-confirm="experience-credentials"` | Remove `hidden`; add the FL license number if one applies |
| Google reviews, rating and profile URL | `#reviews` section, `data-confirm="reviews"` | Add genuine reviews with their exact wording, then remove `hidden` |
| Naming the technician "Alex" | Reviews | Only with the owner's OK |
| Request form destination | `FORM_ENDPOINT` in the `<script>` at the bottom | Set the URL. The button turns on by itself |
| What happens after a call or request (scheduling, diagnostic fee) | Emergency step 03 (comment) | Add the confirmed process; don't promise a response time |
| Services offered and equipment limits | Services section | Remove or edit cards as needed |
| Privacy / Terms links | Footer (comment) | Add the links |
| Real logo or photos | `img/` and the brand mark | Swap in the files. The current images are AI-generated illustrations |
| Site URL | JSON-LD, og:image | Add `"url"` and make og:image an absolute URL |

Cleanup on the old site: the About and Electrical pages contain an unrelated external recipe link. Remove it.

## Handyman services (added later)

| Item | Where in index.html | What to confirm |
|---|---|---|
| The full handyman list | `#handyman` section, plus the "Handyman services" catalog in the JSON-LD | Each item is work the company currently does. Delete the ones it doesn't |
| Electrical, plumbing and roof work | `#handyman` cards 04–06 | Florida needs a state license for many of these jobs. Confirm what the company is licensed for, or narrow the wording (for example "minor repairs") |
