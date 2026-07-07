# Changelog

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
