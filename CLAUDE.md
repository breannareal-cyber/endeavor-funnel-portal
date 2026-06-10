# Endeavor Funnel Portal

Live site: https://breannareal-cyber.github.io/endeavor-funnel-portal/
Maintained by Bre (breannareal-cyber) and Sean (seanboselli-jpg). Both use Claude Code.

## How this app works

- The entire app is ONE file: `index.html` (React via CDN, no build step)
- Hosting: GitHub Pages auto-deploys from `main`. Every push to main goes live in ~1 minute
- Data: Supabase project `yosskkaifoztmcgwqxhq` (tables: companies, founders, company_investors, investors, fundings). RLS is ON; the key in index.html is the publishable key and is safe to be public
- This repo is PUBLIC. Never commit secrets, service role keys, or non-public company data into the code

## Collaboration rules (IMPORTANT, two people push to main)

1. **Always `git pull` before making any change.** The whole app is one file, so stale starts cause painful conflicts
2. **Push as soon as a change is done and verified.** Do not sit on local changes
3. **Data changes go to Supabase, never hardcoded into index.html.** Tiers, companies, founders, funding news: all SQL/dashboard edits, no code change needed
4. **Code changes: check with the other person first** (quick Slack ping) since simultaneous edits to index.html will conflict
5. If a push is rejected (non-fast-forward), `git pull --rebase` and resolve, do not force-push

## Verifying changes

- Test locally by opening index.html in a browser before pushing (sign-in and data require the live origin for OAuth redirect, but layout/JS errors show immediately)
- After pushing, check the live site in ~1 minute and confirm no console errors
