# CONFORM.TOOLS Changelog

What changed in each release of the CONFORM.TOOLS desktop app. Downloads: https://github.com/tbdpost/conformtools-public/releases

## 0.7.2 - 2026-08-26

### Improved
- Lists: a timecode that does not fit its column now keeps its right-hand end (the seconds and frames) and trims the left.
- Durations show only the parts that are filled - `:12` under a second, `4:12` under a minute, `1:04:12` under an hour.
- Markers the app creates show the CONFORM.TOOLS logo in place of the brand word in every list, with the current logo.
- **Edit Index +**: the row action buttons sit between `#` and the track column, and the track column is labelled "Track".
- **Blanking Detector**: findings show a duration instead of a raw frame count.
- **Marker Batch Renderer**: marker colours are drawn as marker icons rather than dots, and durations are right-aligned.

## 0.7.1 - 2026-08-26

### Fixed
- The published build of the 0.7.0 batch: the Linux package is built and shipping again.

## 0.7.0 - 2026-08-26 (not published - superseded by 0.7.1)

### Added
- **Timeline Exchange**: the Offline tab now converts timelines entirely on your own machine - drop or browse for a file, tick the formats you want, and save one file or a whole folder.
- **DataCalc** is included with the app, so it keeps working on installs that are locked off the network.
- Every findings list in the app is now the same table: numbered rows, sortable and resizable columns, a single click to jump the playhead, and a double click to edit a cell.
- **Blanking Detector**: strictness is three presets - Strict, Standard and Relaxed - each still adjustable by hand.
- Settings is grouped by what each section answers, and large temporary renders now default to a media folder rather than a system one.

### Improved
- **Copy Grades**: the source clip that shares the most frames with a destination clip wins, instead of the first one that overlaps at all - and a grade Resolve refused to copy is reported as an error rather than a success.
- Tools follow the timeline that is open in DaVinci Resolve: switch timelines and the tool reloads, instead of showing the previous one (or switching Resolve back).
- Menus, colour pickers and dropdowns open where you clicked, at the right width, and stay inside the window at any UI scale.
- **Edit Index +**: auto-refresh rescans in place on a schedule you choose (15 s to 5 min, or off) and keeps your scroll and selection; a parameter parked on a single keyframe is now visible and searchable.
- **Aligner**: one **Tracks & Reference** list - pick the reference and the tracks to process in the same place.
- A whole-timeline blanking scan no longer demands tens of gigabytes of free space for a pass that writes nothing.
- The app is named CONFORM.TOOLS throughout - window title, installers, tray - and every installer now carries the product's branding.
- Markers the app places are named for the app and the tool, with the detail in the note; markers you write yourself are left exactly as you typed them.
- Offline Timeline Exchange conversions run on the same conversion engine as the website, on your machine, with the slower fallback used only where it is needed.
- Floating controllers switch tools from a row of icons, name themselves in the title bar and no longer waste a strip of empty space.
- Columns can be dragged to resize and double-clicked to fit in every table.

### Fixed
- Timeline Exchange's Offline tab showed a blank page in every installed build; it now opens.
- **Marker Utility**: Delete All and Flip All (and the batch name / note edits) now include clip markers instead of silently skipping them.
- Results rows say where they go in timecode, and clicking one lands on the right frame - **Node Stack Transfer** used to send the playhead an hour past the clip.
- **Blanking Detector**: reveals in the middle of a keyframed move are caught, findings are per frame range, and each marker lasts exactly as long as the problem does.
- **Edit Index +**: the CSV export and the table agree on source timecode, and the timecode column headers actually sort.
- The Resolve render plugin is labelled macOS only and is no longer offered where it cannot work.

## 0.6.0 - 2026-08-22

### Added
- **Edit Index +**: ranges and lists can be typed the way you think them (`61..64`, `61-64`, `in 5,6,8`), the table handles thousands of clips smoothly, tracks can be shown or hidden, columns can be pinned and saved as presets, several properties can be set in one queued operation, the batch queue can be reordered and saved, and Undo restores far more (flags, keywords, comments, colour group, cache).
- **Aligner**: choose which video tracks to process, with All / None / Invert / Deselect empty and a Skip empty tracks toggle, remembered per timeline.

### Fixed
- Windows: machines that still could not connect to DaVinci Resolve now connect.
- **Aligner**: the success / error / mismatch marker colours you choose are actually applied.

## 0.5.0 - 2026-08-21

### Added
- **Edit Index +** searches and batch-edits any clip parameter - every edit sizing, compositing and retime property, plus generic property and metadata fields.
- **All Clips Timeline**: choose where a new timeline's settings come from - the project's own settings, or a match of the source timeline.

### Changed
- The app is organised around three pillars: **Timeline Exchange**, **Conform Connect** and **Utilities**, with every tool under Utilities in a DaVinci Resolve group and a General group.

### Fixed
- Windows: "Resolve is offline" forever, and a crash on first launch.
- **All Clips Timeline**: audio is genuinely removed when asked, image sequences no longer land as a freeze frame, offline media is included by default, compound and nested clips no longer abort a run, and "Include still images" off really excludes stills.
- Generated timelines inherit output, timeline and input gamma correctly when separate colour space and gamma is enabled.
- **Marker Batch Renderer**: no longer reports an error after a successful Add to Queue, and the marker colour is filled in for you.
- **Marker Utility**: Move / Copy / Swap target a specific track, so one marker becomes one clip marker rather than three or four.
- **Edit Index +** loads timelines noticeably faster, and the Search button honours numeric and true/false filters.

## 0.4.2 - 2026-07-16

### Fixed
- **All Clips Timeline** no longer refuses to run on projects with custom SDI monitoring settings.

## 0.4.1 - 2026-07-14

### Fixed
- Every tool that creates a timeline now inherits the current timeline's exact settings, verified after the fact - a timeline that cannot be made to match is deleted rather than left wrong.
- Batch operations report failures honestly instead of counting silently skipped clips as successes.
- Long-running tools can be cancelled and leave truthful state behind (partial timelines removed, track states restored).

## 0.4.0 - 2026-07-10

### Added
- **Conform Connect**: Point to Media, folder access, saving and drag-and-drop now work inside the app.
- Timeline conversion is built into the app and runs entirely on your machine.

### Fixed
- Dropping a timeline file onto the online **Timeline Exchange** tab now works.

## 0.3.3 - 2026-07-06

### Changed
- Every paid tier unlocks the full DaVinci Resolve toolset - Indie, Pro and Studio, and their trials, all get every current tool.

### Fixed
- Linux: sign-in works again.
- Subscriptions: signed-in users who were briefly shown as free tier (2026-07-04 to 2026-07-06) resolve correctly again - no app update required.

## 0.3.2 - 2026-07-03

### Fixed
- Windows: the startup crash loop is gone - the app starts and reports a Resolve compatibility problem instead of dying.
- Tier limits are enforced wherever a tool is launched, including from the system tray.
- Offline licences include the full toolset again.

### Changed
- Subscription tiers realigned across the toolset.

## 0.3.1 - 2026-07-02

### Added
- **All Clips Timeline**: an Include offline media option.
- **Marker Utility**: a target-track selector for Move / Copy / Swap.

### Fixed
- Windows: no more crash at launch with older DaVinci Resolve installs - the mismatch is detected and reported.
- **All Clips Timeline**: options that silently did nothing now work, a clip that hangs Resolve is skipped and named instead of wedging the app, created timelines inherit colour settings, and compound clips no longer abort a run.
- **Marker Batch Renderer**: markers load as soon as the page opens, and the tool preselects the colour with the most durational markers.
- **Marker Utility**: the constant refresh and flicker on Linux is fixed, and opening the tool no longer hammers Resolve with repeated reads.

## 0.3.0 - 2026-06-17

### Added
- Licence-enforced network policy: an airgapped licence keeps the online parts of Timeline Exchange and Conform Connect from reaching out, and a fully siloed licence takes everything offline. Settings shows the active policy.
- Settings: an export location for Timeline Exchange and Conform Connect exports, with an Open button and an Open Folder After Export toggle.
- Settings: a default Timeline Exchange mode (Auto, Online or Offline).
- **Edit Index +**: an offline-media indicator and a way to find clips whose source file is missing.

### Fixed
- Exports are easy to find: they save to your chosen folder, the folder opens when an export finishes, and a notification offers Show File and Open Folder.
- The macOS Help menu reliably shows its entries.
- **Conform Connect**: no restart needed when Resolve was not running at launch - click the status pill to retry.

### Removed
- Smart Ingest, Gallery Manager and Project Setup have been removed for now to keep the app light.

## 0.2.12 - 2026-06-05

### Fixed
- Linux: the app installs and launches cleanly on Rocky Linux 9 / RHEL 9.

## 0.2.11 - 2026-06-02

### Fixed
- **Marker Batch Renderer**: filenames honour where the marker name sits in your naming convention, and the case transform applies to the marker name too.
- **Unused Media**: offline or missing media is reported as skipped with a count and a list, and a failed move no longer looks like a success.
- The macOS Help menu shows its entries.

## 0.2.10 - 2026-05-16

### Added
- A Help menu (Documentation, Submit Feedback, Acknowledgements) and an Acknowledgements page listing the open-source software the app is built on.
- **Unused Media**: per-drive filter chips, live progress during a move, and per-file error details.

### Fixed
- The "Close to System Tray" preference is honoured.
- Dropdown menus line up with their trigger at UI scales other than 100%.
- Windows: Copy link works in the transfer view, and sign-in persists across app restarts.
- Your session refreshes when the app regains focus, so the next click into a tool no longer looks logged out.
- **Unused Media**: files that share a name are no longer silently overwritten, and an unwritable destination fails fast with a clear message.

## 0.2.9 - 2026-04-27

First stable release of the 0.2.x line.

### Added
- **Marker Batch Renderer**: a much larger built-in codec, colour space, gamma and asset-type list, plus an "Add custom…" option on every dropdown that saves with your naming preset.

### Fixed
- **Marker Batch Renderer**: point markers always render as a single frame, and the colour picker only lists colours that exist on the timeline (refreshing when you switch back to the app).
- Windows: the installers no longer crash on launch.

## 0.2.8-beta - 2026-04-25

### Added
- **Node Stack Transfer** - new tool: copy or swap grades between node-stack layers, group graphs, the timeline grade and named colour versions, across the timeline or just the playhead clip, with per-transfer verification.
- **Clip Renamer** - new tool: batch rename media pool clips and timelines with find and replace, regex, case changes, trimming and sequential numbering, all shown in a preview before you apply.
- **Image Sequence Renamer** and **Clip Renamer**: multi-level undo (roll back any of the last 20 batches, surviving a restart), a Swap Fields button, and matching regex support.

### Changed
- Plan tiers: many tools moved down to Indie.
- **Image Sequence Renamer** and **Clip Renamer** share one multi-step pipeline, presets, live preview and undo.

### Fixed
- **Aligner**: near-zero values are written as exact zero, and a clip aligned on its own now matches what Align All produces.
- **Marker Batch Renderer**: render jobs are no longer pinned to the first frame of the timeline at one frame long.
- Windows: the installers ship complete, and the standalone installer is published with each release.

## 0.2.7 - 2026-04-25

### Fixed
- Linux: sign-in works on RHEL, Rocky and Fedora.
- The sign-in error message now names the real causes instead of blaming your network.

## 0.2.6 - 2026-04-24

### Fixed
- Linux: sign-in works on Rocky 9 / RHEL 9.
- Linux: signing out no longer immediately signs you back in.

### Changed
- Debug Mode and the Resolve connection diagnostics are hidden by default - triple-click the "About & Support" heading to reveal them - and the offline status pill shows a short instruction instead of a diagnostics dump.

## 0.2.5 - 2026-04-23

### Fixed
- Linux: sign-in works on distributions whose certificate store lives outside the usual location.

## 0.2.4 - 2026-04-18

### Added
- **Grade Tracer** - new tool: trace grades onto the open timeline by pulling source clips from other timelines in the project (and from other indexed projects and databases), with two apply modes, markers on every clip that fails, and CSV / JSON diagnostics for hand-off.
- **Edit Index +**: filter by transition type and transition duration, with a Trans column showing what runs into and out of each clip.

### Changed
- **Edit Index +**: the collapsed search builder summarises the active filters in plain language, and the collapsed batch panel offers the common actions directly.

### Fixed
- **Edit Index +**: a keyword, comment, scene, shot or take edit refreshes every row for the same source clip, and failed writes are surfaced instead of swallowed.

## 0.2.3 - 2026-04-17

### Fixed
- Linux: auto-update works on every Linux install type.
- Linux: Google sign-in returns to the app automatically instead of asking you to paste a callback URL.

### Changed
- New brand icons for Timeline Exchange, Conform Connect, Utilities, Settings and Feedback throughout the app.
- Sign-in falls back to manual paste sooner, with a clear message when the sign-in service cannot be reached.

## 0.2.2 - 2026-04-16

### Added
- Sign-in: an inline error with a Retry button, and a banner when the sign-in service is blocked by a proxy or firewall.

### Fixed
- Linux: a launch failure is fixed, and launchers show the real app icon instead of a placeholder.
- Sign-in no longer spins forever after an intermittent network error.

## 0.2.1 - 2026-04-16

### Fixed
- An update download no longer appears to run twice when you navigate away, and an update cannot be installed twice at once.
- The tray menu stays in sync with the sidebar.

### Changed
- Linux: further work on blank-window issues, plus startup logging that identifies the exact build in support logs.

## 0.2.0 - 2026-04-15

### Added
- **Aligner**: when confidence at the first frame is low, alignment is retried mid-clip and the better result is kept - with the marker placed at the frame actually used.

### Changed
- **Aligner**: the reference defaults to the top track that has clips, and repeated alignments are considerably faster.
- Logs are written daily and kept for 14 days, with far more detail from every Resolve tool.

### Fixed
- **Aligner**: incorrect horizontal translation when blanking is baked into a frame, and a vertical tilt regression.
- **Marker Batch Renderer**: durational markers render their own duration instead of spanning to the next marker.
- Feedback submissions no longer fail when the attached logs are long.

### Removed
- Drive Shelf, Reconformer and Version Control removed to slim the app down.

## 0.1.16-beta - 2026-04-15

### Added
- **Image Sequence Renamer**: a complete overhaul - a multi-step pipeline (find and replace, change case, prefix, suffix, set extension, renumber, offset), a full preview of every file with before and after names, duplicate detection, a working undo, and saveable presets.

### Changed
- The sidebar's section headings are links to their pages.

## 0.1.15-beta - 2026-04-14

### Added
- Export diagnostic logs from the sign-in screen, so support can help even when you cannot sign in.

### Fixed
- Linux: "Authentication service not configured" at sign-in, and a crash when importing an offline licence.

## 0.1.14-beta - 2026-04-13

### Fixed
- The Resolve connection no longer fails to start on some machines.
- macOS: the tray icon is no longer a white square.

### Changed
- The tray icon setting is a single "Invert Tray Icon" toggle on Windows and Linux, hidden on macOS.

## 0.1.12-beta - 2026-04-10

### Added
- **Timeline Exchange**: a "Save to…" option for choosing where a downloaded file goes.
- **Marker Batch Renderer**: timeline timecode and source timecode as filename fields.
- Feedback: attach screenshots.
- A Debug Mode toggle, a back button in the header, a tray icon colour setting, and far richer Resolve connection diagnostics.

### Fixed
- Windows: a launch crash, and an update that was detected forever but never installed.
- Linux: a blank window on Rocky Linux 8 with NVIDIA drivers.
- **All Clips Timeline**: clips no longer appear frozen on their first frame when placed with handles.
- The Resolve connection works even when the application folder has been renamed.

## 0.1.11-beta - 2026-04-06

### Added
- **Unused Media** - new tool: scan every timeline for media pool clips that are not used anywhere, then move them to a bin, move the files to a folder, or delete them - with search, filtering and undo.
- **Edit Index +**: a "Has Timeline Markers" filter.
- Feedback: a tool selector that detects where you came from, with recent logs and connection diagnostics attached automatically.

### Fixed
- **Marker Utility**: clip markers on trimmed clips - navigation, flipping, deleting, editing and the record timecode shown.

### Changed
- **Marker Utility**: batch, edit and move sections follow the list filter, showing "Flip Filtered", "Apply to Filtered" and so on.

## 0.1.9-beta - 2026-04-05

### Added
- A **Blanking Detector** floating window with Scan One, Scan All, Fix Current and Fix Next.
- Floating windows switch between tools from the header and remember where you left them.
- **Marker Utility**: copy markers timeline-to-clip and clip-to-timeline, plus an All Clips / Playhead Clip toggle.
- **Aligner**: Best matching is the default, with a gear for choosing the method.

### Fixed
- Floating windows reopen after being closed, and several can be open at once.

## 0.1.8-beta - 2026-04-05

### Added
- Resolve connection diagnostics: click "Offline" in the header for step-by-step checks, with a Copy Diagnostics button in Settings.

### Fixed
- Email and password sign-in no longer hangs when you click Sign In or press Enter.
- The Settings gear works when you are not signed in.

## 0.1.6-beta - 2026-04-02

### Added
- **Marker Utility**: an All / TL / Clip scope toggle, and move operations that transfer markers between the timeline and clips.
- **Timeline Exchange**: a download notification with Reveal in Finder when an export completes.

### Changed
- Update downloads show a real progress bar with percentage and size, and a prominent Restart Now prompt when finished.

### Fixed
- Downloads from Timeline Exchange, Conform Connect and DataCalc are no longer silently blocked inside the app.

## 0.1.5-beta - 2026-03-29

### Added
- First release, with Add Handles, Aligner, All Clips Timeline, Blanking Detector, Copy Grades, DataCalc, Edit Index +, Image Sequence Patcher, Image Sequence Renamer, Marker Batch Renderer, Marker Utility and Odd Image Size Fixer.
- Signed installers for macOS, Windows and Linux, auto-update, and licence generation and validation.
