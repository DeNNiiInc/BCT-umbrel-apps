# HestiaCP Umbrel App - Installation Instructions

## Files Needed in Your BCT-umbrel-apps Repository

Your `BCT-umbrel-apps` repository should have this structure:

```
hestiacp/
├── umbrel-app.yml
├── docker-compose.yml
└── icon.png (or icon.svg)
```

## Steps to Add to Your Repository

1. **Copy the files** from `BCT-umbrel-apps-files/hestiacp/` to your `BCT-umbrel-apps` repository.

2. **Add the icon**: 
   - I've generated an icon for you (check the artifacts).
   - Save it as `icon.png` in the `hestiacp` folder.
   - Recommended size: 512x512 pixels.

3. **Commit and push**:
   ```bash
   cd /path/to/BCT-umbrel-apps
   git add hestiacp
   git commit -m "Add HestiaCP app"
   git push origin main
   ```

4. **Update Umbrel**:
   After pushing, Umbrel should automatically detect the changes within a few minutes.
   
   To force an immediate update, SSH into Umbrel and run:
   ```bash
   sudo systemctl restart umbrel-manager
   ```

## Troubleshooting

**App still not showing:**
- Check logs: `sudo journalctl -u umbrel-manager -f`
- Verify the icon exists and is a valid PNG/SVG
- Ensure `umbrel-app.yml` has no syntax errors
- Wait 2-3 minutes after restart for the cache to refresh

**Icon not displaying:**
- Icon must be named exactly `icon.png` or `icon.svg`
- Must be in the same folder as `umbrel-app.yml`
- Recommended size: 512x512 pixels minimum

## Current Status

Your app is located at:
`/data/umbrel-os/home/umbrel/umbrel/app-stores/denniiinc-bct-umbrel-apps-github-97b0d8f6/hestiacp`

This means Umbrel has successfully cloned your repository. If it's not showing in the UI, it's most likely missing the icon file.
