This repository contains the open-source uptime monitor for [mitchind.ch](https://mitchind.ch) (Predivo GmbH), powered by [Upptime](https://github.com/upptime/upptime). Public page: https://status.mitchind.ch (repo `Predivo-GmbH/status-site-mitchind`).

## [📈 Live Status](https://status.mitchind.ch): <!--live status--> **Wird eingerichtet**

<!--start: status pages-->
<!--end: status pages-->

## How this repo is built

Copied from `Predivo-GmbH/status-predivo` per `standards/status-page-standard.md` (decision D13 in
`Familienausfluege-Schweiz/docs/DECISIONS.md`, D-032, 30.10.2026). Two checks, every ~5 minutes:

| Slug | Check | Proves |
|---|---|---|
| `website` | `https://mitchind.ch/`, text `mitchind` | our page, not a host error page |
| `signin` | `https://skuxvafzccztuxcinhvz.supabase.co/auth/v1/health` with the public key (secret `MITCHIND_SUPABASE_ANON`), text `GoTrue` | the sign-in service answers |

`MITCHIND_SUPABASE_ANON` is added by hand to the `SECRETS_CONTEXT` allow-list in `uptime.yml`,
`response-time.yml` and `setup.yml` (Upptime's template update cannot push workflow files here).

## Not finished yet (30.10.2026)

The Statuspage page for mitchind does not exist yet, so `statuspage.json` has no `page_id` and the
workflows **Statuspage sync**, **Status update** and **Component description** are switched off.
Switch them on only after: the page exists, the two components and the group `mitchind` are created,
`statuspage.json` maps `website` and `signin`, and the repo secret `STATUSPAGE_API_KEY` is set.
Then run both drills (`Statuspage sync` and `Status update` with `drill=true`).
