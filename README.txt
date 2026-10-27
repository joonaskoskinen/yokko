YOKKO.GG — PLAYER-FIRST RELEASE

WHAT IS FINISHED IN THE PACKAGE
English CS2-only homepage, player/team application path, secondary partnership path, anonymous founder introduction, online-first goals, support limits, Instagram/X @yokkoesports, original tactical motion background and poster, SVG mark/wordmark, social image, canonical/OG/Twitter metadata, sitemap/robots, 404, system fonts, keyboard menu, reduced-motion handling, security headers, a privacy draft, Node server endpoints, server-verified Turnstile, durable Upstash counters and Resend email delivery code.

IMPORTANT: code is prepared, not deployed. No domain purchase, DNS changes, accounts, secrets or real emails have been created. Private founder name is omitted from the marketing site. This does not eliminate legal duties to identify a data controller or disclose legally required business/operator details. Supply an appropriate public controller identity/contact in the privacy settings before enabling applications.

DEPLOY
Import this directory as a Vercel project, Framework Preset Other, no build command. Node >=22. Connect yokko.gg in Vercel and follow the provider's actual DNS instructions. Decide canonical www redirect there; all metadata here uses https://yokko.gg/. Preview deployments need their own SITE_ORIGIN and permitted Turnstile hostname.

SERVER CONFIG
Use .env.example names in Vercel, never in browser JS or a public repo. Redeploy after changes.
- Resend: verify a domain you own; use restricted sending API key. CONTACT_FROM must use that verified domain; CONTACT_TO is your inbox. PUBLIC_CONTACT_EMAIL is optional public fallback.
- Turnstile: create a managed widget for yokko.gg. Site key is public; secret remains on server. We verify success, hostname and action=contact.
- Upstash: REST URL and token. Lua EVAL atomically increments per-IP (5/15min) and global (100/24h) counters, including requests rejected later. Fail closed on service errors. Test that selected Redis service supports EVAL. The global interval starts with its first request, not midnight. Hash tags keep keys in one cluster slot. Shared networks may hit the same quota. Tune deliberately; no perfect anti-abuse guarantee.
- RATE_HASH_SECRET: use a long random secret e.g. openssl rand -hex 32. The keyed IP hash is pseudonymous, not anonymous.
- PRIVACY_CONTROLLER, PRIVACY_CONTACT, PRIVACY_RETENTION: real operator/controller details and an actually implemented retention policy. Review the privacy draft, lawful basis, processors, transfers and hosting/mail retention with your operation.
- Set CONTACT_FORM_ENABLED=true only after all setup and tests. Public config reveals only site key, public contact and privacy disclosures, never secret credentials. If missing config, form stays disabled.

FORM AND DELIVERY
The form does not promise a reply time or roster place. After acceptance, it explains the club reviews fit and contacts suitable enquiries by email. Validation: category, email, lengths, JSON/body bounds, fixed destination, origin, honeypot, Turnstile and shared rate limits. Plain-text messages, reply_to is applicant email. UUID+content digest passed as Resend idempotency key. Resend acceptance is not final delivery. Check dashboard/inbox/bounce status. Use platform firewall limits too: handler size validation occurs after hosting body parsing.

ANONYMITY AND PRIVACY
The marketing copy deliberately contains no personal founder name. You still need real controller information legally appropriate to the operation. Do not invent a registered company. Nothing here is legal certification. Never publish secrets. No automatic confirmation emails or newsletter subscriptions are sent. No application DB stores messages, but inboxes/provider services do.

VIDEO
Included assets/practice-loop.mp4 is a silent original CS-inspired tactical/radar graphic, not actual Valve match footage or a recorded game. It contains no third-party gameplay and no voice. It is intentionally subdued at 13% opacity. Poster shown until eligible. Video sources attach only >=761px without reduced-motion/data-saver preferences. It pauses when hidden. Motion control pauses CSS+video. No missing video files needed.

ANALYTICS
Deliberately not enabled: no analytics vendor or data collection policy has been chosen. This is not a broken integration. Add analytics only with matching notice and any required user choice, and update CSP. Privacy-friendly host metrics may be enabled after review; they are not claimed here.

TEST BEFORE LIVE
Generated links/IDs and JS syntax checked when Node is available. Media decoded/probed. No automated real-browser/device/accessibility audit or real Turnstile/Resend integration test has been performed. Test mobile 360/390/768, desktop 1366/1920, keyboard/focus, challenge/CSP, wrong origin, invalid input, rate limit/expiry, provider failure, duplicate retry, success, mail reply-to, and performance on a slow connection. No claim of perfect WCAG/Core Web Vitals results.

Check share.png after upload with social preview tools, HTTPS, www redirect, sitemap, and verified profile links. Social handles were provided by owner, not independently verified.
