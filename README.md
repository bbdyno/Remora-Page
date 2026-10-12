# Remora Page

Static landing, pricing, privacy, terms and support pages for Remora (App Store title: "Remora - SSH Client"), in English and Korean.

Plain HTML and one CSS file. No build step, no scripts, no trackers, no web fonts. Nothing here is deployed or published yet.

## Pages

| Page | English | Korean |
| --- | --- | --- |
| Landing | `index.html` | `ko/index.html` |
| Pricing | `pricing/index.html` | `ko/pricing/index.html` |
| Privacy Policy | `privacy/index.html` | `ko/privacy/index.html` |
| Terms of Use | `terms/index.html` | `ko/terms/index.html` |
| Support / FAQ | `support/index.html` | `ko/support/index.html` |

Shared assets: `assets/site.css` (dark by default, light via `prefers-color-scheme`) and `assets/favicon.svg`.

All links are relative and directory-style (`pricing/`, `../ko/`), so the site works from any base path. To preview locally, serve the folder (for example `python3 -m http.server`) instead of opening files directly, because `file://` does not resolve a folder to its `index.html`.

Header, navigation and footer are repeated by hand in all ten files. A change to one needs the same change in the others.

## TODO before publishing

Each page lists its own TODOs in an HTML comment at the top of the file.

1. **Contact email.** Set to `della.kimko@gmail.com` in `privacy/`, `terms/`, `support/` and their `ko/` versions.
2. **Effective date.** Set to October 12, 2026 in `privacy/`, `terms/` and their `ko/` versions. Update it when the text changes.
3. **Terms review.** Have `terms/index.html` and `ko/terms/index.html` reviewed. They state no governing law or jurisdiction. Decide whether to keep custom terms or rely on Apple's standard EULA.
4. **Privacy policy review.** Have both versions checked, including the Korean one against local requirements for a 개인정보 처리방침.
5. **App Store link.** The "Coming soon to the App Store" buttons are disabled placeholders (`href="#"`, class `store-button`, `aria-disabled="true"`, `tabindex="-1"`) in `index.html`, `pricing/index.html` and their `ko/` versions. After release, set the real URL, remove the two attributes, change the label, and reword the "not released yet" notes next to them.
6. **Pricing and free limits.** Prices are shown as planned ($2.49 / month, $19.99 / year, $39.99 lifetime). The free version is described as limited to 3 hosts, 1 session at a time and 3 snippets, with unlimited hosts, session tabs and snippets, port forwarding, jump hosts, OpenSSH config import, automatic reconnect, additional themes and iCloud sync in Pro. Confirm the prices and the free/Pro split at release, in `index.html`, `pricing/index.html`, `support/index.html` and their `ko/` versions.
7. **Support steps.** The FAQ describes adding a host, importing a key, pasting a long command (paste key on the key row, command editor in the terminal's More menu) and syncing in general terms. Check the wording against the shipped app UI, and check the Apple subscription-cancel steps against the current OS.
8. **Site URL.** Once the public URL is known, add `canonical` and `og:url` tags, and make the `hreflang` alternate links absolute (they are relative for now).
