# Changelog

## v1.2.0 (2026-09-23)

- Security: Restore now creates a rollback backup before overwriting an existing file. If that backup fails, the live file is left untouched.
- Improved: refreshed Light, Dark, and Book interfaces with clearer profile, preview, sync, orphan, options, and restore workflows.
- Improved: windows now fit compact and high-DPI work areas while keeping the important action buttons visible.
- Improved: form fields and lists expose localized accessibility labels to Windows UI Automation.
- Privacy: user-facing errors and logs no longer expose full local or network paths, file contents, or stack traces.
- Added: an illustrated user guide and expanded automated safety coverage for restore, disconnected sources, and partial multi-target failures.

## v1.1.0 (2026-09-15)

- Added: one-time licenses for one active computer, with no annual renewal or restriction to a specific AutoCAD version.
- Improved: activate and move a license through the personal link in your purchase email. A valid permanent license also works offline.
- Improved: existing registered licenses are converted automatically while keeping their original expiry date. Connect to the internet for the first start after this update; after conversion, a valid permanent license works offline.
- Security: license signatures are now checked without storing a license-creation secret in the app.

## v1.0.9 (2026-07-23)

- Improved: in the license window, "Buy license" is now the primary button. Reporting an
  activation or purchase problem is now a smaller link instead of its own button.

## v1.0.8 (2026-07-10)

- Fixed: files stored with Windows Server Data Deduplication, or OneDrive "Files On-Demand"
  placeholders, could be flagged as junctions/symlinks and skipped entirely during scanning —
  making already-synced files repeatedly show up as new/added on every sync, even though nothing
  had actually changed.
- Fixed: the main window could open too small to show the action buttons (Validate/Save/Preview/
  Run sync) once a profile with staging enabled showed its staging panel.

## v1.0.7 (2026-07-08)

- Fixed: previewing a sync with staging enabled could show misleading results (wrong file names,
  wrong change type) whenever the staging mount folder was set to an absolute path — which is the
  normal case, since the folder picker always writes an absolute path.
- Fixed: in a rare case, a staged file could be silently discarded without its content ever
  reaching its destination and without a backup being made.
- Fixed: applying read-only permissions and restoring from backup could be interrupted by a folder
  shortcut (junction/symlink) inside the target or backup folder.
- Fixed: syncing a folder that contains a junction/symlink you didn't expect could propose
  deleting files reachable only through it with no explanation — you'll now see a warning instead,
  both when previewing and when running a sync.
- Fixed: a staging folder path saved with a trailing slash could, in a rare case, cause the
  staging folder itself to be removed after promoting its last file.
- Improved: after promoting staged files into place, empty leftover folders in the staging area
  are now cleaned up automatically.

## v1.0.6 (2026-07-07)

- Fixed: backup files could end up read-only (inherited from "set read-only after sync" target
  files), which could block deleting or pruning old backups and could make restoring fail when
  overwriting a read-only file. New backups are no longer read-only, and pruning/restoring now
  clear the read-only flag on existing files as needed — including backups already on disk from
  before this fix.

## v1.0.5 (2026-07-07)

- Added: backup retention. Each sync run's backup folder only ever contained that run's changed/
  deleted files (not a full copy of everything, by design), but nothing ever cleaned up old run
  folders — they accumulated forever. New "Bewaartermijn back-ups" setting per profile (default
  30 days, 0 = keep forever) automatically prunes old backup-run folders after each successful
  sync.

## v1.0.4 (2026-07-07)

- Fixed: opening License from the menu while already licensed let you send another license
  request or open the activation window for no reason — it now shows a simple confirmation
  that you're already licensed instead.
- Added: a "Check for updates" button in Options, so you don't have to wait for the automatic
  startup check or restart the app to see if a new version is available.

## v1.0.3 (2026-07-07)

- Fixed: the orphan-files dialog (shown when "sync deletes" is off and files exist in a target
  folder that no longer exist in source) let you select two conflicting actions at once (e.g.
  Delete and Copy back) — only one is now selectable at a time, as intended.
- Fixed: choosing Delete, Copy back, or Rename for orphan files could silently do nothing if
  there were no other changes to sync — the chosen action now always runs.
- Fixed: Restore (File → Restore) could fail with "The calling thread cannot access this object
  because a different thread owns it" when clicking Preview or Restore.
- Fixed: the log panel (main window and Restore window) now automatically scrolls to the newest
  entry instead of requiring a manual scroll.

## v1.0.2 (2026-07-07)

- Fixed: closing the update dialog without clicking a button (the X button, Alt+F4, Escape) no
  longer silently postpones the update prompt for two days — you'll be asked again next launch.
- Security: license keys are now unique per Boek Solutions product, even on the same computer.
  If you have an existing license and it's no longer recognized after updating, this is expected —
  email info@boeksolutions.nl with your Machine ID for a replacement key, a one-time step.

## v1.0.1 (2026-07-07)

- Security: strengthened how license keys are generated and validated. If you have an existing
  license and it's no longer recognized after updating, this is expected — email
  info@boeksolutions.nl with your Machine ID for a replacement key, a one-time step.

## v1.0.0 (2026-07-07)

- First release: WPF port with Light/Dark/Book themes, offline licensing (14-day trial), auto-update.
