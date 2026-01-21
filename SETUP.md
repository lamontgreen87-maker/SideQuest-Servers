# Setting Up the Server Registry on GitHub

## Step 1: Create the GitHub Repository

1. Go to https://github.com/new
2. Repository name: `SideQuest-Servers`
3. Description: "Community registry of public SideQuest servers"
4. Set to **Public**
5. Click "Create repository"

## Step 2: Push Your Registry Files

```bash
cd c:\dc\server-registry
git init
git add .
git commit -m "Initial server registry"
git branch -M main
git remote add origin https://github.com/YOUR-USERNAME/SideQuest-Servers.git
git push -u origin main
```

## Step 3: Enable GitHub Pages

1. Go to your repo → Settings → Pages
2. Source: **Deploy from a branch**
3. Branch: **main** / **(root)**
4. Click **Save**

Wait 1-2 minutes for deployment.

## Step 4: Update Web Client

Your registry URL will be:
```
https://raw.githubusercontent.com/lamontgreen87-maker/SideQuest-Servers/main/servers.json
```

Update the web client to use this URL (see instructions below).

## Step 5: Add Your RunPod URL

Edit `servers.json` and replace `"https://your-runpod-url.cloud"` with your actual RunPod URL.

Commit and push:
```bash
git add servers.json
git commit -m "Add official server URL"
git push
```

## Web Client Update

Replace the registry URL in `web_client/index.html`:

**Find this line** (around line 710):
```javascript
const res = await fetch('servers.json');
```

**Replace with:**
```javascript
const res = await fetch('https://raw.githubusercontent.com/lamontgreen87-maker/SideQuest-Servers/main/servers.json');
```

## Testing

1. Open your web client
2. You should see the server browser with your official server
3. Click to connect → Should work!

## Maintenance

**Approving server submissions:**
1. Review PRs on GitHub
2. Check that:
   - JSON is valid
   - Server URL is accessible
   - Description is appropriate
3. Merge the PR

The web client will automatically fetch the updated list!
