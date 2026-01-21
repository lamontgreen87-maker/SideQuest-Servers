# Contributing a Server

Thank you for wanting to add your SideQuest server to the registry!

## Requirements

Your server must:
- ✅ Be publicly accessible (or have clear access instructions)
- ✅ Be running a recent version of SideQuest backend
- ✅ Have a stable URL (no frequent changes)
- ✅ Be online and functional

## Submission Process

### 1. Fork This Repository
Click the "Fork" button at the top-right of this page.

### 2. Edit `servers.json`
Add your server entry to the `servers` array. Use this template:

```json
{
  "id": "your-unique-id",
  "name": "Your Server Name",
  "description": "Brief description of your server (200 chars max)",
  "url": "https://your-server-url.com",
  "pricing": "Free|Paid|Freemium|Subscription",
  "status": "online",
  "owner": "Your Name or Team",
  "tags": ["tag1", "tag2", "tag3"],
  "passwordProtected": false
}
```

**Field Guide:**
- `id`: Unique identifier (lowercase, hyphens only, e.g., "rpg-haven-premium")
- `name`: Display name (50 chars max)
- `description`: What makes your server special (200 chars max)
- `url`: Full URL including https://
- `pricing`: Choose one: "Free", "Paid", "Freemium", "Subscription"
- `status`: Should be "online"
- `owner`: Your name or organization
- `tags`: 2-5 relevant tags (e.g., "beginner-friendly", "hardcore", "rp-heavy")
- `passwordProtected`: true if requires password, false otherwise

### 3. Validate Your JSON
Make sure your `servers.json` is valid:
```bash
# Use an online validator or:
cat servers.json | jq .
```

### 4. Submit a Pull Request
- Commit your changes with message: `Add [Your Server Name] to registry`
- Push to your fork
- Create a Pull Request to this repo
- In the PR description, include:
  - Server URL
  - Brief description
  - Confirmation that you own/operate the server

### 5. Wait for Review
We typically review PRs within 24-48 hours. We'll check:
- JSON is valid
- Server is actually online
- Description is appropriate
- No duplicate entries

## Updating Your Server Info

To update your server's information:
1. Edit `servers.json` in your fork
2. Submit a new PR with changes
3. Title: `Update [Your Server Name]`

## Removing Your Server

Create a PR removing your entry with title: `Remove [Your Server Name]`

## Questions?

Open an [issue](https://github.com/lamontgreen87-maker/SideQuest-Servers/issues) if you need help!
