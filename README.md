# GEMS Flag Football Live

The public website for the GEMS flag football tournament. It shows live scores, pool standings, playoffs and top scorers. Anyone can view it without logging in. Referees log in to enter touchdowns, conversions and interceptions, and organisers log in to manage teams and fixtures.

## Files

| File | What it is |
|---|---|
| `index.html` | The whole website |
| `firebase-config.js` | The Firebase project settings and the organiser (admin) emails |
| `firestore.rules` | Database security rules: everyone can read, referees can score, admins can change setup |

## One-time setup

1. **Firebase settings.** Paste the `firebaseConfig` values into `firebase-config.js`, and put the organiser email(s) in `admins`.
2. **Security rules.** In Firebase, go to Firestore Database → Rules. Paste in the contents of `firestore.rules` with the same organiser email(s) in place of `ADMIN_EMAIL`, then click Publish.
3. **Logins.** In Firebase, go to Authentication → Users → Add user, and add one for each organiser and referee. Sign-up should be switched off under Authentication → Settings → User actions.
4. **Authorised domain.** In Firebase, go to Authentication → Settings → Authorized domains and add `<your-github-username>.github.io`.
5. **Hosting.** In the GitHub repository, go to Settings → Pages. Under Build and deployment, choose "Deploy from a branch", branch `main`, folder `/ (root)`. The site goes live at `https://<your-github-username>.github.io/gems-flag-football/`.

## Before the event

1. Log in on the **Referee login** tab with an admin email. The **Setup** tab will appear.
2. On the Setup tab, click **Import team spreadsheet** and choose the completed `GEMS_Flag_Football_Team_Entry.xlsx`. Check the teams, then press **Save setup**.
3. Assign referees to games in each grade's fixtures table, then save.
4. To practise, use **Fill with demo teams**. Afterwards use **Clear all scores** and import the real teams.

## Format

- 4–6 teams in a grade: one pool, full round robin. The top 4 go into the semi-finals (1st v 4th, 2nd v 3rd).
- 7–8 teams in a grade: Pool A is teams 1–4 and Pool B is the rest. The top 2 in each pool go into the semi-finals (A1 v B2, B1 v A2).
- Standings count final games only. They are ranked by league points, then point difference, then points scored.
- After the semi-finals come the final and a 3rd place game. Playoff games must have a winner, so referees keep scoring through overtime.
