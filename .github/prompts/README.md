# Predefined prompts for workflows

These prompts are used by the **Vendor issue to PR** workflow.

## Flow

1. **Predefined prompt** – The prompt in this folder (e.g. `vendor-onboard-prompt.md`) describes the task for the Gemini CLI (what file to edit, structure to follow).
2. **GitHub issue** – The issue (from the Vendor onboarding request form) defines the **fields to be updated** (vendor name, request URL, tracking, etc.).
3. **run-gemini-cli** – Runs the Gemini official CLI with: **predefined prompt** + **issue-derived data** (parsed vendor JSON). The workflow replaces `{{VENDOR_JSON}}` in the prompt with the vendor from the issue.
4. **Commit and push** – Any file changes from the CLI are committed and pushed to the feature branch.
5. **Create PR** – A PR is opened from the feature branch to the base branch.

## Vendor onboarding prompt

Supports **onboard a new vendor** (add to the list) or **update an existing vendor** (match by `name`, update in place). The prompt instructs the Gemini CLI to: if a vendor with the same name exists, update it; otherwise append a new entry.

## Placeholders

- `vendor-onboard-prompt.md`: use `{{VENDOR_JSON}}` where the workflow should inject the parsed vendor JSON from the issue.
