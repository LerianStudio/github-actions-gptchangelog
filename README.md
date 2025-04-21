# 📝 Generate Changelog Action

This GitHub Action automates changelog and release notes generation using [`gptchangelog`](https://github.com/lerian-studio/gptchangelog) and OpenAI GPT-4o. It also signs the changelog commit using a GPG key.

---

## 🚀 Features

- Generates `CHANGELOG.md` and `RELEASE_NOTES.md` using GPT
- Custom changelog template support
- Automatically updates GitHub Releases
- GPG-signed changelog commits

---

## 🛠️ Usage

### 1. Reference the action in your workflow:

```yaml
jobs:
  generate-changelog:
    runs-on: ubuntu-latest
    steps:
      - uses: LerianStudio/github-actions-gptchangelog@main
        with:
          OPENAI_API_KEY: ${{ secrets.OPENAI_API_KEY }}
          GH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          LERIAN_CI_CD_USER_GPG_KEY: ${{ secrets.LERIAN_CI_CD_USER_GPG_KEY }}
          LERIAN_CI_CD_USER_GPG_KEY_PASSWORD: ${{ secrets.LERIAN_CI_CD_USER_GPG_KEY_PASSWORD }}
          LERIAN_CI_CD_USER_NAME: ${{ secrets.LERIAN_CI_CD_USER_NAME }}
          LERIAN_CI_CD_USER_EMAIL: ${{ secrets.LERIAN_CI_CD_USER_EMAIL }}
