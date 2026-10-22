# SDU AI Research Center — website

The website of the SDU AI Research Center at SDU University, Kazakhstan. It is plain HTML and CSS with a little optional JavaScript, and it is built for **GitHub Pages**.

## Structure

```
index.html          Home: overview, news, events, selected papers
about.html          Mission, history, organization, contact
research.html       Research areas, projects, facilities
people.html         Faculty, staff, students, alumni
publications.html   Papers with search and topic filter
news.html           News and announcements
events.html         Seminar series, reading club, conferences
join.html           Admissions, visitors, partners, open positions
404.html            Not-found page
people/
  _template/          Copy this to create a new full personal page
  _template-redirect/ Copy this to redirect to an existing homepage
  <first-last>/       One folder per member (8 members)
assets/css/style.css  All styling (change colors and fonts at the top)
assets/js/main.js     Mobile menu and publication filter
.github/            CODEOWNERS, PR template, issue template
CONTRIBUTING.md     How faculty update their pages
```

## Deploy to GitHub Pages

1. The repository is `SDU-AI-research-center/SDU-AI-research-center.github.io`. Push these files to `main`.
2. Go to **Settings → Pages → Build and deployment**. Choose **Deploy from a branch**, then `main` and `/ (root)`.
3. The site will be live at `https://sdu-ai-research-center.github.io/`.
4. Optional: to use a custom domain such as `ai.cs.university.edu`, add a `CNAME` file containing the domain and configure DNS. See the GitHub Pages docs.

The `.nojekyll` file tells GitHub to serve the files exactly as they are.

## Set up faculty self-editing

1. In the `SDU-AI-research-center` organization, create a team called `site-admins` and add the people who maintain the site.
2. Require two-factor authentication for organization members (**Settings → Authentication security**).
3. Go to **Settings → Branches → Add branch protection rule** for `main`:
   - ✅ Require a pull request before merging
   - ✅ Require review from Code Owners
4. Give each faculty member **Write** access, and add their folder to `.github/CODEOWNERS`.

With this setup, faculty can open PRs that change only their own folder and approve them themselves (as code owners). Changes to shared pages need approval from a site admin.

## Customize

- Replace the placeholder contact email `ai-center@university.edu`, and fill in the `TODO` comments (search the repository for `TODO`).
- Change the colors and fonts in the `:root` block at the top of `assets/css/style.css`.
- People and publications were collected from members' Google Scholar profiles in October 2026. Update them as new papers appear.
- `404.html` has `<base href="/">` so its links work at any missing URL. Keep it as long as the site is served from the domain root (true for `sdu-ai-research-center.github.io` and for a custom subdomain).

## Preview locally

Open `index.html` in a browser, or run:
```bash
python3 -m http.server 8000
```
Then visit http://localhost:8000.
