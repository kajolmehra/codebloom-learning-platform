# Public portfolio security policy

This repository is a sanitized case study and does not contain a deployable application.

## Intentionally excluded

- Production or staging source code
- Environment files and credentials
- OAuth client files, API keys, tokens, or private certificates
- Database dumps, logs, exports, or backups
- Real names, email addresses, phone numbers, or student information
- Client logos, licensed media, internal URLs, and infrastructure details
- Raw screenshots captured from authenticated environments

## Before every push

1. Review `git status` and the complete diff.
2. Confirm that every visual uses fictional or explicitly approved data.
3. Search tracked files for the private project name, domains, emails, phone numbers, and secret-like values.
4. Check image metadata and crop out browser tabs, bookmarks, notifications, and operating-system details.
5. Never weaken `.gitignore` to add a private export or raw capture.

If sensitive material is committed, treat it as exposed: remove it from history and rotate the affected credential at its source.

