# CasaPerfecto Privacy Policy

Effective 9 October 2026.

CasaPerfecto is a website that helps renters compare apartments by commute time, budget and public safety data. This policy describes what happens to the information you enter.

## Summary

- Everything you enter stays in your browser on your device.
- CasaPerfecto has no accounts, no server-side storage, no cookies, no analytics and no advertising.
- The site makes no requests to any third party while you use it.

## What you enter and where it stays

| Information | Why it is used | Where it is kept |
| --- | --- | --- |
| Your gross salary and roommates' salaries | To calculate your rent ceiling | Your browser only |
| Workplace location | To calculate commute times | Your browser only |
| Commute, unit type and must-have choices | To shade the map and rank listings | Your browser only |
| Listings you add, with notes | To compare costs | Your browser only |
| Language and appearance | To display the site | Your browser only |

By default this information is kept in session storage, which your browser clears when you close the tab. If you turn on **Remember on this device**, it is kept in local storage until you delete it. You can also set a passphrase, which encrypts the saved data with AES-GCM using a key derived from your passphrase. The passphrase itself is never stored.

## Calculations

Commute times, budget ceilings and rankings are calculated in your browser. The map, routing data, safety data, fonts and code are downloaded from the CasaPerfecto site itself. The page's Content Security Policy blocks requests to any other site.

## Share links and exports

**Share link** builds a link that holds your choices after the `#` sign. Browsers do not send that part of a link to any server. Salary and listings are left out unless you turn on **Include salary and listings**. Anyone you send the link to can read what it contains.

**Export as JSON** saves a file to your device. CasaPerfecto never sees it.

## Hosting

The site is hosted on GitHub Pages. Like any web host, GitHub receives technical information when your browser requests the site's files, such as your IP address and browser type. This is governed by the [GitHub Privacy Statement](https://docs.github.com/en/site-policy/privacy-policies/github-general-privacy-statement). CasaPerfecto does not receive or use these logs.

## Browser extensions

Extensions you install can read pages you visit, including what you type into CasaPerfecto. This is outside CasaPerfecto's control.

## Deleting your data

Open **Settings** and choose **Delete all data**, or clear this site's data in your browser settings.

## Children

CasaPerfecto is not directed at children and collects no information from anyone.

## Changes

Changes to this policy are made as commits to this repository, so every version and its date are public.

## Contact

Open an issue at [github.com/arieltyson/CasaPerfecto-privacy/issues](https://github.com/arieltyson/CasaPerfecto-privacy/issues).
