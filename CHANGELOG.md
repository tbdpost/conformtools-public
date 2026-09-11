# CONFORM.TOOLS Changelog

What changed in each release of the CONFORM.TOOLS desktop app. Downloads: https://github.com/tbdpost/conformtools-public/releases

## 0.8.1 - 2026-09-10

### Added
- **Reconformer: Drop in VFX** (beta, Indie and up; Drop in is Pro, free in beta). Pick the timeline and a bin of finished comps, and every comp is matched to its plate on the cut - by the shot id in its name, then by source timecode - with nothing rendered. What is left can be found by the picture (the subject of a green-screen plate survives the composite) or placed at the playhead by hand. Drop in puts every matched comp on a new video track over its plate, handles trimmed, the plate's reframe carried when the sizes agree, a marker on each; Disable plates switches the plates off underneath, and Undo takes it all back.
- **Resolve Renamer** now has every step the Image Sequence Renamer has: Remove Characters (a number of characters from the start, the end, or a position), Insert Text at a position from either end, Add Date / Time, wildcards in Find & Replace, a Match Case toggle on Regex Replace, Capitalize Words, and a step size for Sequential Numbering. Two items that would end up with the same name are marked in the preview and left alone.
- **Image Sequence Renamer**: Remove Characters, Insert Text, Add Date / Time, Whole Word and Wildcards on Find & Replace, and Capitalize Words - all on the name part, never the frame number or the extension.
- **Reconformer: Conform from media** (beta, Indie and up). Rebuild a cut from the media itself: pick the reference cut and a bin or a string-out of the footage, and every shot is found in the source by eye - the same clip used twice, a repeated take, a speed change, nothing - with its pan, tilt, zoom and flip measured in the same pass. A reframed shot is still found, look-alike takes are told apart, a reframe cut hidden inside continuous footage is found and cut, and black between cuts is left empty. Build the conformed timeline (Pro, free in beta) with the reference kept on a disabled track above for difference mode; what was learned about a source is kept per project and reused by later conforms.

### Fixed
- Utilities: a long tool name no longer overlaps the version badge on its card.
- **Reconformer**: a reframe on the second half of a through edit is carried. When the old cut razored a shot mid-take and reframed one piece, and the new cut carries that shot as one clip, the rebuilt timeline is now cut at the same frames and each piece keeps its own sizing; the change list shows the pieces as Split, and Undo splits joins them back. A through edit under a dissolve or on a retimed clip is left whole, and the summary says why.

## 0.8.0 - 2026-09-08

### Added
- **Reconformer** (beta, Indie and up): compare two cuts frame for frame, see every change on a map and in a list with conform vocabulary, then rebuild the new cut with the old version's grades, sizing and markers - with a per-clip choice of whose sizing wins and the previous cut kept on a disabled history track.
- **Proxy Leak Detector** (beta, Indie and up): scores every shot against its source and marks the suspects.
- Master QC: a Reports button reopens any earlier QC run - findings, decisions and the HTML report - so a job can be picked up again after other work, without rendering again.
- Master QC: record a decision on any finding straight from its Status cell, in one click - fixed, artistic intent, best available, won't fix, not an issue, or your own words - with a note. Filter the list to all, open or resolved findings. Decided findings stop counting against the verdict, are listed in the report's Reviewed section, keep their markers in a review colour, and the decision survives re-running the QC.
- Master QC markers now land on the clip they concern: picture findings on the video clip, audio findings on the picture clip they are linked to, and the timeline for conform findings and anything without a clip under it.
- **Master QC**: a report editor. Give the report your own title, facility, client, project code, prepared-by, logo, notes and extra fields; switch every section on or off and put them in any order; choose whether evidence pictures are included, whether only issues are listed, the lowest severity to show, how many rows each check may take, which shots are tabled, timecode or frame numbers, page breaks, a dark or light page, and the paper size. The preview updates as you type; apply it to the filed report, print it to PDF, or save a copy anywhere. Save the layout as a named preset, and export or import presets between machines.
- **Master QC**: pixel defects. Dead, stuck and hot pixels - and single-pixel-wide dead lines - are found on every render by default and shown on a map of the frame with a list underneath: where each sits, what colour it is stuck at, how many shots it was seen in, and the frame it was first spotted on.
- **Aligner**: every result now carries evidence - the reference, the clip before, and the clip after alignment shown as a blend and as a difference - so you can see it landed without re-rendering. Click a thumbnail to enlarge; arrow keys step through the clips.
- **Aligner**: undo a whole run. Every aligned clip's sizing goes back the way it was, and the markers the run placed are removed.
- **Aligner**: export the results as a CSV.
- **Aligner**: retry any clip from the list. Each row has a Retry action that measures that one clip again a different way - one step per click, with the clip put back to its original sizing before each attempt and the row saying which attempt produced the result.
- **Aligner**: undo any single clip from its row; the run-wide Undo is still there.
- **Aligner**: build keyframes for an animated shot (Pro). An Animated row can be turned into keyframed sizing: a sized timeline takes the original's name, with the original kept as "… (before sizing)". This replaces the separate Sizing Match page.
- **Master QC**: one workspace. Findings are filtered by lane chips - picture, motion, shot, graphics, pixels, PSE, audio, conform, leader - that switch on, off or solo, each with a line explaining what it covers; the timeline can be scrubbed and drags the playhead with it; the findings list is taller, every timecode copies to the clipboard on click, and a Columns menu shows the What-to-do and Fix columns.
- **Master QC**: a pixel defect takes you to its frame, boxes the defect in its own colour on the pulled frame and shows it magnified with a swatch of the pixel's colour; a PSE event takes you to its frame and suggests a resolution.
- **Master QC**: pixel defects are grouped per shot - one finding lists every pixel in the shot, each magnified in the preview and ringed on the frame; the report shows each shot's own thumbnail with just its defects marked.
- **Master QC**: the report editor can set the filmstrip's tile size and density.
- **Settings**: the offline license opens from the Account card, the acknowledgements live under About & Support, and the tool preferences sit with Appearance & Window.
- **Master QC**: the HTML report is always the printable light page, records which DaVinci Resolve and render-plugin versions produced it, and lists a dead line once rather than once per pixel.
- **Blanking Detector**: auto-fix during a full scan (Advanced Settings). Each flagged clip gets the smallest zoom or reposition that clears the blanking as it is found, and the marker says what was adjusted. Off unless you switch it on.
- **Copy Grades**: source and destination are picked on one track list, low to high with V1 first, the way the Aligner picks its reference. Picking a role on the other role's track swaps them.

### Improved
- Master QC, Proxy Leak Detector and Reconformer keep their working data in the app's private data folder; only the HTML report is filed in your Movies folder (or your chosen scratch location), and earlier reports move over on their own.
- Aligner: a shot that moves is written as keyframes that reproduce the move frame-accurately, with no more keyframes than it needs; the render plugin is used whenever it is installed, with an automatic fallback when it is not; a drift that left most keyframed clips un-keyframed on 23.976 fps timelines is fixed.
- Reconformer: a change map with editing vocabulary (moved, slipped, trimmed, split, replaced, inserted, deleted, retimed, reframed, regraded), inline sizing decisions, a scrubbable preview, and A / B defaulting to the open timeline and the next one.
- While a tool is in beta, its Pro actions are open to Indie subscribers.
- The app grows to a working size when Master QC, Reconformer or Edit Index + starts a job (Settings toggle).
- Scrubbing the QC timeline shows the frame under the playhead (filmstrip, or the movie itself for a single-clip timeline). Needs render plugin 1.4.8.
- Aligner: re-aligning a clip keeps the sizing it already carried, the reference's crop is followed, heavy punch-ins are found, and Align All builds a <timeline>_ALIGNED copy with the moving shots keyframed.
- Master QC leaves preview: it is available to every Indie subscriber (still marked beta while it settles).
- Aligner with the render plugin: a clip the first pass cannot settle is measured again in the same run, so every clip ends aligned, animated, stabilised or an honest error - never a silent mismatch. Burned-in graphics and subtitles no longer throw a match off, short shots are judged on what they have, and sources that sit at a very different zoom from the reference are matched (needs render plugin 1.4.7).
- Aligner: shots that were stabilised are called out, runs are faster, and the results list is taller.
- Master QC: audio findings show the loudness trace around the moment; Enlarge opens at a third, click expands, click again closes, and next/previous wrap around; pixel callouts are squares; a successful auto-fix marks the finding Fixed; the blanking fix corrects a pan before it scales.
- Master QC: Enlarge fills the preview; the report filmstrip is laid out like Resolve's Lightbox with a timecode per row and a columns slider; the aspect check lists every aspect found; the Advanced settings choose whether markers go on the timeline (default) or on the video and audio clips; old reports can be deleted from the Reports list.
- The Master QC report is set in the conform.tools typeface and carries the CONFORM.TOOLS wordmark; a Pro report can carry your own logo and facility details instead.
- Blanking Detector: auto-fix during scan lives in Advanced Settings; fixing a clip turns its markers to the resolved colour; the results columns are sized sensibly; every list can be sorted by its # column.
- A Master QC fix or render puts DaVinci Resolve back on the page you were working on.
- Master QC: findings read shorter and never repeat the clip or check name; several dead pixels on one shot are one finding listing every pixel; every pixel finding has a timecode and a frame; a timeline gap is never reported as clipping or black.
- The Master QC timeline playhead follows the pointer exactly at every UI scale, can be grabbed anywhere along its line, and the hover preview never hides behind the next section.
- Tools still being finished carry a BETA badge; truncated table cells show their full text on hover; every Master QC control has a tooltip.
- **Aligner**: every clip is matched away from its cut, where dissolves, flash frames and head handles live, so a transition no longer spoils the match.
- **Aligner**: Verify now catches a wrong orientation. When the aligned picture only lines up with the reference mirrored, the flip is undone instead of pan and tilt being "corrected" on a mirrored picture, and a clip whose verification does not land is matched again and kept only when that lands closer.
- **Aligner**: sub-pixel precision is now opt-in and stricter - it is kept only when it lands a better match than the first measurement. Switch it on next to Detect animated moves when you want it.
- **Aligner**: when a clip is refused as a mismatch, or cannot be measured at all, the result says why in plain words - for example a stretched or anamorphic zoom, or a frame too flat or dark to read.
- **Master QC**: a missing slate is a warning, not a failure, and the expected slate fields are shown against what was read from it.

### Fixed
- Edit Index +: the search builder's operator and colour menus no longer close or ignore a click when the table refreshes underneath them.
- Turning off Show Dev Features in Settings now hides every development-only control.
- Aligner with the render plugin: with DaVinci Resolve left on the Deliver page, the reference could be analysed in place of the clips and everything looked matched. That is fixed, and an identical-looking result is never reported as a match.
- Aligner: pan and tilt land exactly on sources whose size differs from the timeline; a failed retry no longer worsens the pose; a wrong-scale result with the render plugin is fixed.
- Master QC: a dissolve is no longer reported as an edit without a picture change.
- **Master QC**: red and blue stuck pixels are now caught, not only bright or dark ones.
- **Master QC**: far fewer false pixel defects - a specular highlight on a locked-off shot or a one-pixel graphic line is no longer reported.
- **Master QC**: the timeline playhead lands exactly under the pointer at every interface scale; the "Copied" hint on a timecode is no longer cut off.

### Changed
- The render plugin bundled for offline installs is the signed 1.4.8 build.
- Master QC no longer reports the black frames of a timeline gap as clipping, illegal blacks, a freeze or a black-frame finding. A gap is noted once, as a gap.
- **Subscriptions**: Master QC is an Indie tool. Batch QC, non-default spec packs, the white-label report and keyframe sizing are Pro.
- The DaVinci Resolve render plugin is now version 1.4.6 and installs from the app, including on machines without internet access. In Resolve it has no settings panel, and everything it produces is simply named CONFORM.TOOLS - in the Deliver page it shows as CONFORM.TOOLS. It now checks audio as well as picture, reports per shot, finds pixel defects far faster, and is what the Aligner uses when it is installed.

## 0.7.10 - 2026-09-05

### Fixed
- **Free trial**: the app now honours your free trial. A new account, or one whose trial we have extended for you, used to open with every tool locked even though the website showed the trial running; the app now unlocks the same tools for the same days, and Settings shows when the trial ends.

## 0.7.9 - 2026-09-02

### Fixed
- **Aligner** no longer marks a shot green when only one frame of it lines up. A shot that moves against the reference, or that already carries transform keyframes, is reported as **Animated** in the mismatch colour with the reason in the note - aligned at one frame, the move still needs keyframes.
- **Image Sequence Renamer** no longer hangs on a large sequence. A 29,000-frame folder used to freeze the app while the preview built, and a rename or undo on a slow network mount is no longer cut off part-way.
- **Image Sequence Renamer** never overwrites a file. Two files that would end up with the same name, or a name already taken by another file in the folder, are marked in the preview (DUPE / EXISTS) and skipped when you rename; everything else still goes ahead. Before, the second file could silently replace the first.
- **Image Sequence Renamer**: undoing a swap of two names restores them; it used to be reported as already undone.

### Improved
- **Aligner**: **Reset sizing first** (on by default) wipes each clip's pan, tilt, zoom, rotation and flips before measuring, so sizing inherited from another cut can no longer throw the match off. A clip that cannot be matched is put back exactly as it was, and the result says what was reset.
- **Aligner**: the results list has a Note column and an animated count, and both new behaviours can be switched off next to Verify & refine.
- **Image Sequence Renamer**: shifts and renumbers are faster on a long sequence, and a folder is never left holding temporary files.
- **Image Sequence Renamer**: the Rename button shows how many files are being renamed while it runs, and the preview's Skipped tab lists every file the rename will leave alone with the reason.
- Every tool's results list handles very long lists without slowing the app down.

## 0.7.8 - 2026-09-01

### Fixed
- **Resolve connection**: the app now finds DaVinci Resolve when several versions are installed side by side under their own names (for example `DaVinci Resolve 20.3.1.app` inside a `DaVinci Resolve 20.3.1` folder), and connects to the one that is running. Before, only the standard install location was recognised, so those installs showed "Resolve isn't detected" on every tool.
- **Connection diagnostics** now name the Resolve install actually in use, its version, and every install found on the machine, so a report tells us at once what the app had to choose from.

## 0.7.7 - 2026-09-01

### Added
- **Blanking Detector**: black frames - frames with no picture at all - are now found and marked in their own colour. They were being measured and then reported as clean.
- **Blanking Detector**: re-run a scan and any marker whose blanking is now clean turns green, with the original finding kept in its note. **Clear Resolved** removes just those and leaves the open findings alone.
- **Mapped Mounts** (Settings): rewrite media path roots that came from another machine - `/media` becomes `/Volumes`. On by default on Linux, and available everywhere. Applied to the media in converted timelines; only whole mount points are matched, so a folder like `/mediafiles` is left alone.
- **Aligner**: a new **Verify & refine** mode checks each clip after aligning it and corrects anything still off. Slower, and the surest way to land on mismatched resolutions.
- **Marker Batch Renderer**: unlimited custom fields, offered first in the Add Field menu.
- **Marker Batch Renderer**: each field can set what joins it to the field before it, so a field can attach straight onto the marker name.

### Fixed
- **Blanking Detector** now catches a single pixel of black at an edge. At the Strict setting one pixel was being ignored and two reported, which is the wrong way round - a one-pixel edge is the most common blanking error there is.
- **Blanking Detector** now catches blanking revealed part-way through a keyframed move - an animated error on a 16:9 timeline set to 16:9 was never reported.
- **Blanking Detector**: the strictness sliders now actually reach the scan - a single-clip scan was ignoring them and running at its own default.
- **Blanking Detector** reads animated vertical zoom and animated crop correctly; both were effectively invisible before.
- **Aligner** now lands correctly when the footage, the timeline and the reference are different resolutions, and follows the timeline's own output resolution rather than the project's.
- **Aligner** adds its correction to a clip's existing reframe instead of overwriting it - a clip that had already been repositioned no longer jumps somewhere else.

### Improved
- **Edit Index +**: the tools column (Align, Fix Blanking, Navigate) can now be moved, hidden and brought back like any other column, and it saves with your column presets. It was the only column that could not be.
- **VFX Pulls**: the shot list is a real list now - sort by any column, resize columns, and drag column headers to reorder them, like every other list in the app. Custom names are edited with a double click.
- **Aligner** reports the project's mismatched-resolution handling and any per-clip Scaling override, so an odd result is explainable.
- **Marker Batch Renderer**: add, remove, rename and drag filename fields on the tool page itself - no trip to the settings page.
- **Marker Batch Renderer**: the handles preview only appears when handles are actually set.

## 0.7.6 - 2026-08-31

### Added
- **Marker Batch Renderer**: Artist Initials fill themselves in from your account name - Brandon Thomas becomes BT - until you type your own.
- **Marker Batch Renderer**: Handles now save and load with the naming preset, so a delivery spec carries its own run-in and run-out.

### Improved
- Handle fields in **Add Handles** and **Marker Batch Renderer** have proper up/down arrows, take the up/down keys, and scrub with the mouse wheel.
- **Marker Batch Renderer**: Handles are set in frames only - the seconds option is gone. An existing setting in frames is carried over.
- **Add Handles**: the new timeline says which way the frames went - `_4FR_HANDLES` when adding, `_TRIM_4FR` when trimming - and a count of 0 is refused instead of quietly duplicating the timeline.
- **Add Handles** is called the same thing in the sidebar, the Utilities gallery and on its own page.
- **Marker Utility**: the Flip-to controls show the marker shape instead of a round dot.
- **Marker Utility** floating window: the colour list opens across the window instead of running off its edge, so you no longer have to resize the window to pick a colour.

## 0.7.5 - 2026-08-30

### Added
- **Add Handles**: a negative handle count now trims frames from the head and tail of every clip instead of adding them - the new timeline is named `_<n>FR_TRIMMED`. Clips too short to survive the trim are skipped and reported.
- **Marker Batch Renderer**: Handles can be negative too - each rendered section loses that many frames from both sides. A section shorter than the trim renders its middle frame.

### Improved
- **Marker Batch Renderer**: the Handles setting moved up beside the filename preview and output folder, where the render range is decided.
- **Marker Utility** floating window: the Flip-to control shows just the target colour (its name is in the tooltip), and picking a colour opens right at the control instead of at the top of the window.
- Every tool's list keeps its column headers solid while you scroll - rows no longer show through them.

### Fixed
- **Timeline Exchange** (offline): conversions failed on a fresh install with a "No such file or directory" error before ever reaching the converter. They work first try now.

## 0.7.4 - 2026-08-28

### Added
- **Edit Index +**: Grade Version batch action - switch the selected clips to a local or remote grade version by name, or add a new one to all of them.

### Fixed
- An offline license signs you in: with a valid license file in place the app opens straight to the dashboard, no login screen. Importing a license activates it immediately.
- **Copy Grades**: the floating window reported "Copied: 0 clips" for copies that had worked. Every Copy Grades control now reports what actually landed, and a copy Resolve accepted but could not be double-checked is reported as copied with a note instead of as a failure.
- **Edit Index +**: Copy Grades on a selection now copies (it had been failing silently with a count of 0).
- Settings: the update download bar no longer appears to run backwards before it starts filling.

### Improved
- Every track list in the app - pickers, popovers, floating windows - reads low to high: V1 first.

## 0.7.3 - 2026-08-26

### Added
- **Marker Batch Renderer**: Handles - add run-in and run-out (in frames or seconds) to every marked section you render. Remembered between sessions.
- **Marker Utility**: Edit Markers has a tick box for Name and one for Notes, so an Apply can change one without touching the other; an unticked row is greyed out. The floating window has the same.
- Every list: drag a column header onto another to move the column. The order is remembered per tool.
- **Edit Index +**: right-click the V / A / Trans / Key filter chips for a menu that says what each state does in plain words.

### Fixed
- **Edit Index +**: the batch-action pop-ups (Keywords, Marker, Group, Comments and the rest) no longer disappear when you click into their text field; Escape closes them.
- In-app feedback: reports reach the team again - they were being shelved when the attached error log was too long for the tracker.

### Improved
- **Edit Index +**: Keywords, Comments, Scene, Shot and Take cells open for editing on a double click, like every other editable cell in the app.
- **Edit Index +**: click anywhere on the Actions header to expand or collapse the panel.
- Feedback: the thank-you screen offers "Submit another report" and nothing else.

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
- A whole-timeline blanking scan no longer demands tens of gigabytes of free space.
- The app is named CONFORM.TOOLS throughout - window title, installers, tray - and every installer now carries the product's branding.
- Markers the app places are named for the app and the tool, with the detail in the note; markers you write yourself are left exactly as you typed them.
- Offline Timeline Exchange conversions give the same result as the website, entirely on your machine.
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
- **Aligner**: a clip that does not match well at its first frame is tried again further in and the better result is kept - with the marker placed at the frame actually used.

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
