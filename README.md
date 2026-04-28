# Adopt Me Korea — Website

This is a small static site scaffold for the "Adopt Me Korea Server" landing page.

Preview locally

- Open `index.html` in your browser, or run a simple local server:

```powershell
# from the project folder
python -m http.server 8000
# then open http://localhost:8000
```

What I added

- `index.html` — homepage
- `styles.css` — responsive styles
- `script.js` — mobile nav + smooth scroll
- `logo.svg` — placeholder logo
 - `logo.jpg` — primary favicon and header logo (place a JPEG named `logo.jpg` in the project root to be used as the site logo and favicon).
 - `logo.svg` — optional fallback vector icon (kept for browsers that prefer SVG). If you don't have `logo.jpg`, the site will use `logo.svg` where supported.

Next steps (optional)

- Replace placeholder links (Discord invite) with real links.
- Add images/screenshots of your server and staff bios.
- Deploy to GitHub Pages, Netlify, or Vercel for hosting.

Realtime servers and players

- This scaffold includes a simulated "Live Servers" section that updates every 3 seconds. The simulation code lives in `script.js` and populates the server cards.
- To replace simulation with a real API, call `window.RealtimeServers.setData([{id:'asia',players:120,ping:45}, ...])` with the latest data from your backend or monitoring endpoint.

Example (replace with your endpoint):

```js
fetch('/api/server-status')
	.then(r=>r.json())
	.then(data=>{
		// data should be an array of objects {id, players, ping}
		window.RealtimeServers.setData(data);
	})
```

Deployment to Vercel

1. Create a repository (GitHub/GitLab/Bitbucket) and push this project.

```powershell
git init
git add .
git commit -m "Initial site"
git branch -M main
git remote add origin <your-git-repo-url>
git push -u origin main
```

2. Go to https://vercel.com, sign in, and "Import Project"; connect your Git provider and choose this repo. Vercel auto-detects static sites and will deploy.

3. Add your custom domain in the Vercel project settings -> Domains. Vercel will show the DNS records you need to add at your domain registrar — follow those instructions. For a root domain you'll usually add A/AAAA records or change nameservers; for a subdomain you can add a CNAME pointing to the provided Vercel target.

4. (Optional) You can also deploy directly from your machine with the Vercel CLI:

```powershell
npm i -g vercel
vercel login
vercel --prod
```

The included `vercel.json` file configures the project as a static site. If you want, I can set up the GitHub repo for you and enable Vercel deployment.

