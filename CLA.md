# Project Whitehole Individual Contributor License Agreement (CLA)

Thank you for your interest in contributing to **Project Whitehole** ("the Project"), maintained by Vishwas Singh and Shweta Vishwakarma ("the Maintainers").

In order to clarify the intellectual property license granted with Contributions from any person or entity, the Maintainers must have a Contributor License Agreement ("CLA") on file that has been agreed to by each contributor. This agreement protects both you and the project's ecosystem.

---

### 1. Definitions
* **"You" (or "Contributor")** means the individual or legal entity entering into this Agreement.
* **"Contribution"** means any source code, documentation, point-cloud parsing logic, cryptographic routines, or modifications submitted by You for inclusion in Project Whitehole.
* **"Submit"** means any form of electronic communication sent to the repository (e.g., Pull Requests, Git commits, issue comments).

### 2. Grant of Copyright License
Subject to the terms and conditions of this Agreement, You hereby grant to the Maintainers a perpetual, worldwide, non-exclusive, no-charge, royalty-free, irrevocable copyright license to reproduce, prepare derivative works of, publicly display, publicly perform, sublicense, and distribute Your Contributions and such derivative works.

### 3. Grant of Patent License
Subject to the terms of this Agreement, You hereby grant to the Maintainers and to recipients of software distributed by the Maintainers a perpetual, worldwide, non-exclusive, no-charge, royalty-free, irrevocable patent license to make, have made, use, offer to sell, sell, import, and otherwise transfer the Work.

### 4. Dual-Licensing & Commercialization Rights
You acknowledge that the primary open-source license for Project Whitehole is **GNU Affero General Public License v3.0 (AGPL-3.0)**. You expressly grant the Maintainers the unrestricted right to sublicense or dual-license Your Contributions under commercial, proprietary, or alternative open-source terms without requiring additional consent or royalty disbursements.

### 5. Contributor Representation
You represent that You are legally entitled to grant the above license. If Your employer has rights to intellectual property that You create, You represent that You have received permission to make Contributions on behalf of that employer.

---

### How to Sign
To agree to these terms, comment directly on the Pull Request:

4. Press `Ctrl + S` to save.

---

### Step 2: Create `.github/workflows/cla.yml`

1. In the VS Code left sidebar, create a new folder structure:
   - Create a folder named `.github`
   - Inside `.github`, create a folder named `workflows`
2. Inside `.github/workflows/`, create a new file named `cla.yml`.
3. Paste the following GitHub Actions automated CLA verification workflow:

```yaml
name: "Contributor License Agreement (CLA)"

on:
  issue_comment:
    types: [created]
  pull_request_target:
    types: [opened, synchronize, reopened]

permissions:
  actions: write
  contents: write
  pull-requests: write
  statuses: write

jobs:
  cla-assistant:
    runs-on: ubuntu-latest
    steps:
      - name: "Run CLA Assistant Verification"
        if: (github.event.comment.body == 'recheck' || github.event.comment.body == 'I have read the CLA Document and I hereby sign the CLA.') || github.event_name == 'pull_request_target'
        uses: contributor-assistant/github-action@v2.6.1
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          # Dedicated personal access token or automated repository secret
          PERSONAL_ACCESS_TOKEN: ${{ secrets.CLA_BOT_TOKEN || secrets.GITHUB_TOKEN }}
        with:
          path-to-signatures: '.vault/legal/signatures.json'
          empty-commit-flag: false
          white-list: 'dependabot[bot],VishwasSingh,shweta-vishwakarma'
          # Path to the canonical agreement
          path-to-document: 'https://github.com/${{ github.repository }}/blob/main/CLA.md'
          custom-notsigned-prcomment: 'Thank you for contributing to Project Whitehole! All contributors must agree to our Contributor License Agreement before PRs can be merged. Please read [CLA.md](https://github.com/${{ github.repository }}/blob/main/CLA.md) and reply with: `I have read the CLA Document and I hereby sign the CLA.`'
          custom-pr-sign-comment: 'I have read the CLA Document and I hereby sign the CLA.'
```text
I have read the CLA Document and I hereby sign the CLA.
