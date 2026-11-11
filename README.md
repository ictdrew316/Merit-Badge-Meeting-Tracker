# Merit Badge Sign-Off Log

A static GitHub Pages site. At a meeting, a leader picks a scout and a merit badge, checks the requirements the counselor signed off, and saves. Everything lands in a "Scoutbook queue" so you can enter it in Scoutbook later and tick each item off.

## Setup (about 5 minutes)
1. Create a new GitHub repository (for example `troop-signoffs`) and upload everything in this folder (`index.html`, `README.md`, and the `data/` folder).
2. Repo **Settings > Pages**: Source = "Deploy from a branch", branch `main`, folder `/ (root)`. Your site will be at `https://<user>.github.io/<repo>/`.
3. For each leader who will record sign-offs: add them as a repo collaborator (Settings > Collaborators), then have them create a fine-grained personal access token (GitHub > Settings > Developer settings > Fine-grained tokens), limited to this one repository with **Contents: Read and write**.
4. On each leader's phone or laptop: open the site > **Settings** > paste the token > **Save & connect**. The token stays in that browser only.

## Using it (at a meeting)
1. **Pick the merit badge** being worked on that night.
2. **Tap the scouts who are here.** "Select scouts already started" picks everyone with earlier sign-offs on that badge.
3. **Check requirements in the grid.** One row per requirement, one column per scout. The box at the start of a row checks it for everyone present. Gold "Pick 2 of 5" rows and orange-edged items mark choice groups; "Do all" marks groups where every part is required. Under a Pick row, each scout's cell shows how many of the required choices they have (for example 1/2, then a green check).
4. **Save.** Set the date and who signed off, then press Save. Items already logged show a gold dot (waiting for Scoutbook) or a green check (entered), so nothing is entered twice.

**Scoutbook queue tab:** lists what is waiting, by scout and badge. Enter it in Scoutbook, then tick it off ("Mark all entered" for a whole badge). **Download spreadsheet** creates an .xlsx with a "To enter in Scoutbook" sheet (one row per scout and badge, requirement numbers listed) and a "Detail by requirement" sheet. It follows the Waiting / Entered / All filter. CSV is also available.

- If a save fails (no signal), entries stay on that device and retry; the header shows how many are unsaved.
- Two leaders saving at once is safe: each save re-reads the latest file and merges.

## Notes
- Requirement text is the official text from scouting.org as of Nov 11, 2026 (143 badges). It lives in `data/requirements.json`. Re-collect it if requirements change.
- Requirement numbers like `2a(1)` are built from the page's numbering. A few badges with option groups (Athletics, Cycling, Plant Science, Golf, Multisport, Geology) use `5[A](1)` style numbers, and a few repeat a letter (shown with a trailing `'`).
- The roster in `data/signoffs.json` was seeded from your September tracker. Add new scouts in Settings.
- **Privacy:** scout names and progress are in the repository. Prefer a private repository if your plan supports Pages on private repos; otherwise consider using first names only.
