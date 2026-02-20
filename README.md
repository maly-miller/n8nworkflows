# n8n Workflows

Collection of n8n workflow JSON files for automation.

## Workflows

### n8n Version Check & Upgrade Notifier

**File:** `n8n_version_check_upgrade_notifier.json`

Automated workflow that checks the installed n8n version via SSH, compares it to the latest stable GitHub release, and sends an email notification with upgrade instructions if a newer version is available.

**Schedule:** Every Monday at 9:00 AM

**Flow:**
```
Schedule Trigger → SSH (get version) → HTTP Request (GitHub API)
  → Code (compare versions) → IF (upgrade needed?)
    → true: Gmail (send notification)
```

**Required Credentials:**
- SSH credential for server access
- Gmail OAuth2 for email notifications

## Usage

1. Import the JSON file into your n8n instance
2. Configure the required credentials
3. Update the recipient email address
4. Activate the workflow
