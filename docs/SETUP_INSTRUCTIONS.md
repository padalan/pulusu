# Pulusu.com — Setup Instructions

## Manual Step: Add pulusu.com to Cloudflare

The CF_API_TOKEN in Infisical doesn't have zone creation permission.
Do this once in the Cloudflare dashboard:

1. Log in to [dash.cloudflare.com](https://dash.cloudflare.com) as **Nikhil@zerocopy.systems**
2. Click "Add a site" → enter `pulusu.com`
3. Select **Free** plan
4. Cloudflare will show 2 nameservers (e.g., `ada.ns.cloudflare.com`, `miles.ns.cloudflare.com`)
5. Go to **Namecheap** → pulusu.com → Domain → Nameservers → "Custom DNS"
6. Replace Namecheap nameservers with the 2 Cloudflare ones
7. Back in Cloudflare, click "Check nameservers" — propagation takes 1-24 hours
8. Once active, Cloudflare auto-provisions SSL

## After DNS is active

### Custom domain for Pages
1. CF Dashboard → Pages → pulusu-site → Custom domains → Add `pulusu.com`
2. Also add `www.pulusu.com` → redirect to pulusu.com

### Email routing (hello@pulusu.com)
1. CF Dashboard → pulusu.com → Email → Email Routing
2. Enable Email Routing
3. Add route: `hello@pulusu.com` → Forward to `Nikhil@zerocopy.systems`
4. Verify the destination email if prompted

### Analytics (Plausible)
1. Sign up at [plausible.io](https://plausible.io) (or self-host)
2. Add site: `pulusu.com`
3. Script tag is already in the layout — no code changes needed
