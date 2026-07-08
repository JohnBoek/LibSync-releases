# Changelog

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
