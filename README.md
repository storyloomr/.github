# Storyloomr Organization Label Management

This repository contains the centralized label taxonomy and synchronization workflows for all Storyloomr repositories.

## 🏷️ Label Taxonomy

Our organization uses a consistent labeling system across all repositories to improve issue tracking, project management, and collaboration.

### Label Categories

#### Type Labels (Issue/PR Classification)

- `type: bug` - Something is broken
- `type: feature` - New capability
- `type: chore` - Maintenance or refactor
- `type: docs` - Documentation change
- `type: design` - UX/UI or visual design

#### Status Labels (Workflow State)

- `status: backlog` - Needs review
- `status: ready` - Groomed and ready to pick up
- `status: blocked` - Waiting on dependency
- `status: in progress` - Actively being worked
- `status: testing` - In validation/QA
- `status: approved` - Approved for merge/release

#### Priority Labels (Impact and Urgency)

- `priority: p0-urgent` - Sev-critical
- `priority: p1-high` - High impact
- `priority: p2-medium` - Medium impact
- `priority: p3-low` - Low priority

#### Area Labels (Component/Service Ownership)

- `area: frontend` - Frontend web applications
- `area: mobile` - Mobile applications (iOS/Android)
- `area: auth` - Authentication and authorization
- `area: content` - Content management and delivery
- `area: media` - Media processing and storage
- `area: search` - Search functionality and indexing
- `area: analytics` - Analytics and metrics collection
- `area: infra` - Infrastructure and deployment
- `area: gateway` - API gateway and routing
- `area: kafka` - Event streaming and messaging
- `area: redis` - Caching and session storage
- `area: observability` - Monitoring, logging, and tracing

#### Security Labels

- `security: vuln` - Vulnerability or exposure
- `security: audit` - Security review task

#### Community Labels

- `good-first-issue` - Beginner-friendly
- `help-wanted` - Maintainers seeking help

## 🔧 Setup Instructions

### Prerequisites

1. **Create a Personal Access Token (PAT)**:

    - Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
    - Generate new token with these scopes:
        - `repo` (Full control of private repositories)
        - `admin:org` → `write:org` (Write org and team membership, create projects)
    - Copy the token value

2. **Configure Repository Secret**:
    - Navigate to this repository's Settings → Secrets and variables → Actions
    - Click "New repository secret"
    - Name: `BOT_TOKEN`
    - Value: Your PAT from step 1

### Initial Setup

After configuring the secret, run the workflow manually to seed all repositories:

```bash
# Navigate to Actions tab in GitHub UI, select "Manage Organization Labels"
# Click "Run workflow" → Set dry_run to false → Run workflow
```

## 📋 How to Use

### Making Label Changes

1. **Edit the configuration**:

    ```bash
    # Edit manage-your-labels.yml to add/modify/remove labels
    vim manage-your-labels.yml
    ```

2. **Test your changes** (dry run):

    ```bash
    # Run workflow with dry_run = true to preview changes
    gh workflow run manage-your-labels.yml -f dry_run=true
    ```

3. **Apply changes**:

    ```bash
    # Run workflow normally to apply changes
    gh workflow run manage-your-labels.yml
    ```

### Adding New Repositories

Add the repository name to the `repositories` list in `manage-your-labels.yml`:

```yaml
repositories:
    - storyloomr-fe-reader
    - storyloomr-new-repo # Add new repos here
```

### Performing Dry Runs

Before making changes, always perform a dry run:

1. **Via GitHub UI**:

    - Go to Actions → Manage Organization Labels
    - Click "Run workflow"
    - Set `dry_run` to `true`
    - Click "Run workflow"

2. **Via CLI**:

    ```bash
    gh workflow run manage-your-labels.yml -f dry_run=true
    ```

3. **Manual dry run** (check current labels):

    ```bash
    # List current labels on a specific repo
    gh api repos/storyloomr/storyloomr-svc-content/labels --jq '.[].name' | sort
    ```

### Cleaning Up Non-Standard Labels

⚠️ **CAUTION**: This will remove labels not defined in the configuration.

1. **Set `confirmRemove: true`** in `manage-your-labels.yml`
2. **Run a dry run first** to see what will be removed
3. **Coordinate with teams** to ensure no important labels are lost
4. **Run the workflow** to clean up labels
5. **Reset `confirmRemove: false`** for normal operations

## 🔄 Automated Sync

The workflow runs automatically:

- **Daily at 3 AM UTC** via cron schedule
- **Manual trigger** available in Actions tab
- **Dry run mode** available for testing

## 🛠️ Per-Repository Fallback

If you need to sync labels for a single repository, use this workflow in the target repo:

```yaml
# .github/workflows/sync-labels.yml
name: Sync Repository Labels

on:
    workflow_dispatch:

permissions:
    contents: read
    issues: write

jobs:
    sync:
        runs-on: ubuntu-latest
        steps:
            - name: Download org label config
              run: |
                  curl -H "Authorization: token ${{ secrets.GITHUB_TOKEN }}" \
                    -o manage-your-labels.yml \
                    https://raw.githubusercontent.com/storyloomr/.github/main/manage-your-labels.yml

            - name: Sync labels
              uses: actions-automation/manage-your-labels@main
              env:
                  BOT_TOKEN: ${{ secrets.GITHUB_TOKEN }}
              with:
                  config: manage-your-labels.yml
```

## 🔍 Verification Commands

After running the workflow, verify the sync:

```bash
# Check if labels were applied to a sample repository
gh api repos/storyloomr/storyloomr-svc-content/labels --jq '.[].name' | grep "type:" | sort

# Compare label counts across repositories
for repo in storyloomr-fe-reader storyloomr-svc-content storyloomr-app-ios; do
  count=$(gh api "repos/storyloomr/$repo/labels" --jq '. | length')
  echo "$repo: $count labels"
done

# Check for missing repositories (404 errors)
gh api repos/storyloomr/storyloomr-svc-content/labels > /dev/null && echo "✅ Access OK" || echo "❌ Access denied"
```

## 🚨 Troubleshooting

### Common Issues

1. **403/404 Errors**:

    - Verify PAT has correct scopes
    - Check repository exists and is accessible
    - Ensure BOT_TOKEN secret is set

2. **Missing Labels After Sync**:

    - Check workflow logs for errors
    - Verify `manage-your-labels.yml` syntax
    - Run dry run to preview changes

3. **Repository Access Denied**:
    - Add PAT owner to repository collaborators
    - Or run fallback workflow in target repository

### Getting Help

- Check workflow run logs in Actions tab
- Validate YAML syntax with `yamllint manage-your-labels.yml`
- Test single repository access: `gh api repos/storyloomr/REPO_NAME/labels`

## 📝 Configuration Reference

### Label Properties

```yaml
- name: "label-name" # Required: Label name (use consistent naming)
  description: "Description" # Required: Clear description
  color: "hexcolor" # Required: 6-character hex color (no #)
```

### Repository Configuration

```yaml
repositories:
    - repo-name # Repository name (without organization)

confirmRemove: false # Set to true to remove non-standard labels
```

### Color Scheme

Our color scheme follows GitHub's recommendations:

- **Red** (`#b60205`, `#d73a4a`, `#d93f0b`) - Critical, bugs, urgent
- **Green** (`#0e8a16`, `#c2e0c6`, `#0b6623`) - Features, ready, approved
- **Blue** (`#0075ca`, `#1d76db`, `#0366d6`) - Docs, in progress, infrastructure
- **Yellow** (`#fbca04`) - Medium priority, design
- **Purple** (`#5319e7`, `#7057ff`) - Areas, community
- **Gray** (`#cfd3d7`, `#c5def5`) - Low priority, chores

## 📈 Extending the System

### Adding New Label Categories

1. Add labels to `manage-your-labels.yml`
2. Update this README documentation
3. Consider updating issue/PR templates
4. Notify teams of new labels

### Integration with Project Management

Labels automatically integrate with:

- GitHub Projects (filter by labels)
- Issue templates (auto-apply labels)
- PR templates (suggest labels)
- GitHub CLI (`gh issue list --label "type: bug"`)

---

**Maintained by**: DevOps Team  
**Last Updated**: September 2025  
**Questions?**: Create an issue in this repository
