# TwoShot Studio User Guide

Welcome to the TwoShot Studio! This comprehensive guide covers all keyboard shortcuts, mouse controls, and features to help you work efficiently.

---

## Table of Contents

1. [Quick Reference](#quick-reference)
2. [Studio Layout](#studio-layout)
3. [Clip Types](#clip-types)
4. [Mouse Modes](#mouse-modes)
5. [Keyboard Shortcuts](#keyboard-shortcuts)
6. [Mouse Interactions](#mouse-interactions)
7. [Context Menus](#context-menus)
8. [Timeline Controls](#timeline-controls)
9. [Preview Panel](#preview-panel)
10. [MIDI Editor](#midi-editor)
11. [Transcript](#transcript)
12. [Grid and Zoom](#grid-and-zoom)
13. [Track Management](#track-management)
14. [Clip Operations](#clip-operations)
15. [Rendering and Export](#rendering-and-export)
16. [Sharing and Collaboration](#sharing-and-collaboration)
17. [AI Features](#ai-features)
18. [Notes](#notes)
19. [Tips and Workflows](#tips-and-workflows)
20. [Cursor Indicators](#cursor-indicators)

---

## Quick Reference

### Essential Shortcuts Cheat Sheet

- `Space` — Play/Pause
- `Ctrl+Space` — Play from the start
- `Ctrl+Z` — Undo
- `Ctrl+Shift+Z` / `Ctrl+Y` — Redo
- `Ctrl+S` — Save
- `Delete` or `Backspace` — Delete selection
- `Ctrl+D` — Duplicate
- `Ctrl+C` / `Ctrl+V` — Copy / Paste
- `Ctrl+A` — Select all
- `Ctrl+G` / `Ctrl+Shift+G` — Group / Ungroup
- `Ctrl+B` — Burn selection
- `Z` — Zoom mode (click clips to zoom to bounds)
- `G` — Goto/zoom to selection (or fit all)
- `Ctrl+0` — Zoom to fit
- `Enter` — Open clip editor (MIDI or Group)
- `Tab` — Select next clip/note, or cycle visible clips in the Preview Panel
- `Ctrl+/` — Open the AI Assistant

All `Ctrl` shortcuts also work with `Cmd` on macOS.

### Mouse Mode Quick Keys

- `S` — **Select**: Select and move clips
- `T` — **Stretch**: Resize clip edges
- `X` — **Split**: Cut clips at cursor
- `C` — **Clone**: Duplicate while dragging
- `V` — **Volume**: Adjust clip volume
- `D` — **Delete**: Click to delete
- `P` — **Paint**: Draw MIDI notes (MIDI editor), or AI-generate content by drawing a region on the timeline or on the Preview Panel canvas
- `Z` — **Zoom**: Click to zoom to bounds, drag to zoom to area

---

## Studio Layout

The Studio interface has these main areas:

- **Header** — Play/pause, project title, undo/redo, mouse mode, tempo, metronome, grid controls, zoom, export, share
- **Timeline** — Horizontal tracks with clips, ruler at top, track headers on the left
- **Preview Panel** — Visual canvas showing video/image clips at the current playhead position (appears when the project contains visual clips). Has its own transport bar and a fullscreen mode.
- **Content Panel** — Contextual area below the timeline showing the MIDI editor, group clip editor, or notes sidebar depending on context
- **AI Assistant** — Opens as a right-side sidebar on desktop or a bottom-sheet popup on narrow screens. Triggered by any **Ask AI** button, by `Ctrl+/`, or by an AI notification.

### Main-View Modes

The main area shows the timeline by default but can be switched to full-area **Preview** or **Transcript** via the mode switcher pill at the bottom of the screen. The URL hash reflects the current mode:

- no hash — timeline (default)
- `#preview` — preview canvas fills the main area
- `#transcript` — transcript fills the main area (label is **Lyrics** for projects with tempo)

Clicking a mode toggles it; clicking Timeline returns to the default. Right-side sidebars hide while a main mode is active. If both Preview and Transcript are active, transcript takes the main area and preview stays in the right sidebar.

---

## Clip Types

The Studio supports five types of clips, each with different capabilities:

### Audio Clips

Audio clips contain a single audio file or sample.

**Characteristics:**
- Displays waveform visualization
- Can be trimmed, stretched, and repositioned
- Supports playback speed adjustment (percentage or tempo-sync)
- Can be transformed using AI models
- Shows source name and duration
- Supports fade in/out
- Has an **Ask AI** button (Coproducer icon) for asking the assistant about this specific clip

**Visual Indicators:**
- Waveform display
- Trim handles on edges
- Volume/gain indicator
- Mute state (dimmed when muted)
- Icon: `music_note` for tracks (with BPM, longer than 5 s) or `volume_up` for shorter sounds
- When AI is working on the clip, the Ask AI icon glows green and spins, and a shimmering status message replaces the duration label

**Context Menu Options:**
- Ask AI (open a session about this clip)
- Get Transcript — fetches a transcript for the clip's audio (hidden once transcribed)
- Transform (AI audio transformations)
- Convert to MIDI, Pitch Shift, Sync Tempo, Reset Speed/Width
- Fade, Render (Burn / Download / Share as Sound or Video)
- Unburn — rehydrates a burned clip back into its source tracks (only on clips that were burned from a multi-clip source)
- Source Audio (Change / View / Preview / Download)
- Duplicate, Split, Delete

Audio clips that were burned from project data show a small **flame icon** in their header alongside the type icon — click it (or the Open-in-fullscreen button in the clip's action bar) to unburn.

### MIDI Clips

MIDI clips contain musical note data that can be edited in the piano roll.

**Characteristics:**
- Contains note events (pitch, timing, velocity, duration)
- Editable in the MIDI Editor (double-click to open)
- Notes visualized as colored blocks
- Velocity shown as note opacity
- Can be converted to audio via "Burn to Audio"
- Supports attack and release envelope controls
- Has an **Ask AI** button alongside the open-editor button

**Visual Indicators:**
- Piano roll note blocks
- Pitch range indicator
- Note density visualization
- `piano` icon

**Context Menu Options:**
- Ask AI
- Open Editor (or double-click)
- Merge MIDI Clips, Convert to Audio clips, Export MIDI File
- Reset Width, Fade, Render
- Source Audio (the instrument sample used for playback)
- Duplicate, Split, Delete

**Editing MIDI Clips:**
1. Double-click the clip or press `Enter` with it selected
2. Use Paint mode (`P`) to add notes
3. Use Select mode (`S`) to move/edit notes
4. Use Volume mode (`V`) to adjust velocity

### Video Clips

Video clips display video content on the Preview Panel canvas, with optional audio.

**Characteristics:**
- Filmstrip visualization on the timeline (top 65%) with audio waveform below (bottom 35%); when the source has no audio (or audio has been extracted), the filmstrip uses the full clip height
- Video rendered on the Preview Panel canvas at the current playhead position
- Supports viewport (pan/zoom/scale), crop, and opacity
- Playback speed control (including tempo-sync when the video has BPM) and loop option
- Trim with cut start / cut end
- Audio can be extracted to a separate audio track and restored later
- Animated GIFs and animated WebPs dropped onto the studio are imported as video clips
- VP9 alpha-channel videos render with transparency over underlying clips on the canvas
- Has an **Ask AI** button

**Visual Indicators:**
- Filmstrip thumbnails
- Waveform for audio track (if present)
- `videocam` icon
- Ghost copies appear when the track is looped, showing where the clip will repeat

**Context Menu Options:**
- Ask AI
- Extract Audio — Extracts the video's audio to a new audio clip on the next track and silences the video itself
- Restore Audio — Re-enables audio playback from the original video
- Snapshot — Captures the current frame as a new image clip
- Fit to Canvas — Reset viewport to center at 100% scale
- Fill Canvas — Auto-scale to cover the entire canvas
- Set Canvas to *(aspect ratio)* — Sets the project canvas aspect ratio to match this clip's source dimensions
- Opacity — Quick presets (100%, 75%, 50%, 25%) + custom slider
- Reset Width — Clear trim/cut operations
- Reset Speed — Reset playback speed to 1.0x
- Render (Burn / Download / Share as Video)

### Image Clips

Image clips display a static image on the Preview Panel for a set duration.

**Characteristics:**
- Static image shown for a defined length (default 4 seconds)
- Supports viewport (pan/zoom/scale), crop, and opacity
- No audio component
- Has an **Ask AI** button

**Visual Indicators:**
- Image thumbnail on timeline
- `image` icon
- Ghost copies appear when the track is looped

**Context Menu Options:**
- Ask AI
- Fit to Canvas — Reset viewport to center at 100% scale
- Fill Canvas — Auto-scale to cover the entire canvas
- Set Canvas to *(aspect ratio)* — Sets the project canvas aspect ratio to match this image's dimensions
- Opacity — Quick presets (100%, 75%, 50%, 25%) + custom slider

### Group Clips

Group clips are containers that hold multiple tracks with clips inside them.

**Characteristics:**
- Contains nested tracks and clips
- Acts as a single unit on the parent timeline
- Can contain any combination of audio, MIDI, video, image, and other group clips
- Useful for organizing complex arrangements
- Can be ungrouped to extract contents
- Solo, mute and preview labels respect the contained content (a group with visual content can be visually soloed)
- Has an **Ask AI** button

**Visual Indicators:**
- Inline preview of the nested clips, rendered with the same look as their standalone counterparts (waveform/filmstrip/image), with proper loading placeholders
- "Group" label
- Nested content visualization

**Creating Groups:**
1. Select multiple clips (can span multiple tracks)
2. Press `Ctrl+G` / `Cmd+G` to group
3. The clips become a single group clip

**Editing Groups:**
1. Double-click the group clip or press `Enter`
2. Edit the nested timeline
3. Changes are saved to the group

**Ungrouping:**
- Select the group clip
- Press `Ctrl+Shift+G` / `Cmd+Shift+G`
- Contents are extracted back to parent timeline

---

## Mouse Modes

The Studio has 8 mouse modes that change how your cursor interacts with clips. Switch modes using the dropdown in the header or press the corresponding key. In **Fullscreen Preview**, only Select, Clone, and Delete modes are available. In full-screen **Transcript/Lyrics**, Select, Split, Delete, Paint, and Zoom are available.

### Select Mode (`S`)

The default mode for general editing.

**Capabilities:**
- **Click clip** — Select it (replaces current selection)
- **Ctrl/Cmd + Click** — Add/remove from selection (toggle)
- **Shift + Click** — Range select from last selected clip
- **Drag clip** — Move horizontally (time) and vertically (track)
- **Drag near edge** — Resize clip (within 10px of edge)
- **Click empty area** — Deselect all

### Stretch Mode (`T`)

Dedicated mode for resizing clips.

**Capabilities:**
- **Drag left edge** — Trim clip start (adjusts where playback begins)
- **Drag right edge** — Trim clip end (adjusts where playback ends)
- **Alt + Drag** — Temporarily invert the current snap state (turns snap off when it's on, and vice versa) for precise positioning

### Split Mode (`X`)

Cut clips at any point.

**Capabilities:**
- **Click on clip** — Split at cursor position
- **Red dashed line** — Shows where split will occur
- **With selection** — Only splits selected clips
- **Without selection** — Splits all clips at that position
- **Right-click** — Move playhead to clicked position (instead of splitting)

### Clone Mode (`C`)

Create copies while dragging.

**Capabilities:**
- **Ctrl/Cmd + Drag** — Create a copy and drag it to new position
- Original clip stays in place
- Works in both timeline and MIDI editor

### Volume Mode (`V`)

Adjust clip volume or MIDI velocity.

**Capabilities:**
- **Drag up** — Increase volume/velocity
- **Drag down** — Decrease volume/velocity
- **Right-click** (MIDI only) — Reset velocity to 1.0

### Delete Mode (`D`)

Quick deletion without selecting first.

**Capabilities:**
- **Click** — Delete clip/note
- **Drag** — Delete all clips/notes under cursor path
- **Right-click** — Also deletes (same as left-click)
- **Generating AI Paint clips** — Deletes/cancels the pending generation

### Paint Mode (`P`)

A drawing mode that does different things depending on where you use it.

**In the MIDI Editor:**
- **Click** — Create note at cursor position
- **Click + Drag** — Draw note with custom duration
- **Y position** — Determines note pitch
- **Snap-to-grid** — Applied automatically

**On the Timeline (AI Paint):**
- **Drag** to draw a region on the timeline. The region becomes an editable AI clip placeholder.
- An empty pseudo-track appears at the top of the timeline in most modes so you can paint a brand-new track without first creating one.
- Drop your cursor on any track to drop the placeholder there; drop on the pseudo-track to create a new track.
- Resize the placeholder by dragging its left/right edges.
- Click an existing clip in Paint mode to ask AI about that clip; drag across it to paint a region instead.
- Type a prompt in the floating chatbox attached to the placeholder, then submit. Generation begins and the placeholder shows live progress, an estimated time remaining, and a stop button.
- Cancel by clicking the stop button (or by deleting the placeholder before you submit).
- If you reload or close the project mid-generation, the placeholder reappears with live progress when the project reopens.

**On the Preview Panel canvas:**
- **Drag** on the canvas to draw a rectangular **spatial region**. This creates an AI clip whose generated content is constrained to that area of the visual frame — useful for placing AI-generated content into a specific part of the composition.

### Zoom Mode (`Z`)

Quickly zoom to specific clips or regions.

**Capabilities:**
- **Click on clip/note** — Zoom to that item's bounds
- **Click + Drag** — Draw rectangle to zoom to that region
- **Click on empty space** — Reset zoom to show all content
- **Right-click (anywhere)** — Reset zoom to show all content
- **ESC** — Exit zoom mode and return to Select mode

**Also available in any mode:**
- **Ctrl + Right-click + Drag** — Draw zoom rectangle
- **Ctrl + Right-click on clip/note** — Zoom to that item's bounds
- **Ctrl + Right-click on empty space** — Reset zoom

---

## Keyboard Shortcuts

All `Ctrl` shortcuts also work with `Cmd` on macOS. The shortcuts below work on the timeline; a subset (Space, Ctrl+S, Ctrl+Z, Ctrl+Shift+Z / Ctrl+Y, and the mouse-mode keys) also works inside Fullscreen Preview.

### Playback

- `Space` — Play/Pause
- `Ctrl+Space` — Play from the start

### File Operations

- `Ctrl+S` — Save project
- `Ctrl+Z` — Undo
- `Ctrl+Y` / `Ctrl+Shift+Z` — Redo

### Selection

- `Ctrl+A` — Select all clips
- `Ctrl+Shift+A` — Select all clips in the selected tracks
- `Ctrl+I` — Invert selection
- `Escape` — Clear selection
- `Tab` — Select next clip/note (or cycle visible clips in the Preview Panel)
- `Shift+Tab` — Select previous clip/note

### Clip Operations

- `Delete` or `Backspace` — Delete selected clips
- `Ctrl+D` — Duplicate
- `Ctrl+C` — Copy
- `Ctrl+V` — Paste
- `Ctrl+G` — Group clips
- `Ctrl+Shift+G` — Ungroup clips
- `Ctrl+B` — Burn selection to a single clip
- `Ctrl+L` — Auto-extend to next clip
- `Q` — Quantize start to grid
- `Ctrl+Q` — Quantize start *and* end to grid

### Zoom Controls

- `Ctrl+0` — Zoom to fit all content
- `Z` — Zoom mode (click clips to zoom to bounds, drag to zoom to area)
- `G` — Goto/zoom to selection (or fit all if nothing selected)
- `Ctrl+Scroll` — Zoom at cursor
- `Alt+Scroll` over the timeline — Step enabled Beats/Seconds snap values
- `Alt` + `+` / `Alt` + `-` — Step enabled Beats/Seconds snap values finer/coarser
- `Scroll on the Snap Matrix` — Step the grid value (scroll the top-level pill to step every active row, or scroll a specific row)

### Movement

- `Left Arrow` / `Right Arrow` — Move selected clips left/right by one grid step
- `Ctrl+Left` / `Ctrl+Right` — Move 10× faster
- `Up Arrow` / `Down Arrow` — Move selected clips to the previous/next track

### Track Operations

- `Shift+Delete` — Delete selected tracks
- `Shift+D` — Duplicate selected tracks
- `Shift++` (Shift + Plus) — Insert a new track below the selection
- `Shift+Up` / `Shift+Down` — Move selected tracks up/down

### Audio Controls

- `M` (with a selection) — Mute/unmute selected clips
- `M` (with no selection) — Toggle metronome
- `Shift+M` — Mute/unmute selected tracks

### Editor Navigation

- `Enter` (with a MIDI or Group clip selected) — Open the clip editor
- Double-click a clip — Open the clip editor

### MIDI Editor Shortcuts

These work inside the MIDI editor (in addition to the standard mode keys):

- `Ctrl+Up` / `Ctrl+Down` — Move selected notes up/down by one semitone
- `Q` / `Ctrl+Q` — Quantize selected notes (Ctrl+Q also quantizes the end)
- `L` / `Ctrl+L` — Auto-extend notes
- `G` — Toggle grid display (when keyboard-to-MIDI mode is off)

When **keyboard-to-MIDI** mode is active, the keyboard becomes a piano:

- `[` / `]` — Octave down / up
- `-` / `=` — Velocity down / up

---

## Mouse Interactions

### Click Behaviors

- **Click empty area** — Deselect all
- **Click clip** — Select clip (replaces selection)
- **Ctrl/Cmd + Click** — Toggle clip in selection
- **Shift + Click** — Range select to clicked clip
- **Double-click clip** — Open clip editor
- **Right-click clip** — Show context menu

### Drag Operations

- **Drag clip** — Move in time and/or to different track
- **Ctrl/Cmd + Drag** — Clone drag (create copy while moving)
- **Drag clip edge** — Trim start or end
- **Drag track header** — Reorder tracks

### Selection Box

- **Ctrl + Drag on empty** — Create selection box
- **Ctrl + Shift + Drag** — Toggle selection mode
- **Escape during drag** — Cancel selection box

### Zoom Box

- **Ctrl + Right-click + Drag** — Create zoom region
- **Release** — Zoom to that region
- **Ctrl + Right-click (no drag)** — Reset zoom to all
- **Ctrl + Right-click on clip/note** — Zoom to item bounds

**Or use Zoom Mode (`Z`):**
- **Left-click + Drag** — Create zoom region (no Ctrl needed)
- **Left-click on clip/note** — Zoom to item bounds
- **Left-click on empty space** — Reset zoom
- **Right-click** — Reset zoom

### Scroll Wheel

- **Scroll** — Pan the timeline horizontally
- **Ctrl + Scroll** — Zoom at cursor position
- **Alt + Scroll** over the timeline — Step every enabled Beats/Seconds snap value
- **Scroll on the Snap Matrix pill** — Step the value of every snap row that has grid lines enabled
- **Scroll on a Snap Matrix row** — Step only that row's value

---

## Context Menus

Right-click on clips or tracks to access context menus with additional options.

### Audio Clip Context Menu

Right-click on an audio clip to see these options:

#### Ask AI

Opens a small chatbox attached to the clip. Type a question or instruction and the assistant responds with the clip already loaded as context. While the AI is working you'll see a green spinning icon on the clip and a status message in place of the duration. Each clip has its own session, so multiple clips can be processed in parallel without interfering with each other.

#### Transform (AI Audio Processing)

Opens a submenu with AI-powered audio transformation tools. Available tools are loaded dynamically based on your audio and include:

**Music Tools:**
- **Describe new style** — Reimagine your audio with a text prompt
  - Solo Reskin — Change the style or instrument of a stem
  - Reimagine Melody — Transform a melody with a description
  - Transform humming — Convert voice/humming into a melody
  - Reimagine Song with Vocals — Remix with just a description
- **Split Stems** — Separate audio into individual instrument tracks (drums, bass, vocals, etc.)
- **Extend** — Generate continuation of your audio
  - Instrumental — Extend instrumental music
  - Song — Extend music with vocals
  - Speech — Extend spoken audio

**Vocal Tools:**
- **Cleanup Vocals** — Remove noise and enhance clarity
- **Remove reverb** — Strip reverb from audio
- **Extract Vocals** — Isolate vocals from background music
- **Change Voice** — Transform to a different voice (Male/Female/Custom voices available)
- **Transform humming** — Convert humming to melody
- **Extend Speech** — Continue speech with a script
- **Unmix Multiple Vocals** — Separate multiple voices in a recording

**Other Tools:**
- **Upscale** — Improve audio quality (available for clips between 1-180 seconds that haven't been upscaled)
- **Ask AI / Attach audio** — Send to Coproducer for AI assistance
- **Recreate AI source** — Re-run generation with different parameters (only appears if clip was AI-generated)

#### Rename

Opens a dialog to rename the audio clip.

#### Pitch Shift

Opens a window with a slider to adjust the clip's pitch from -12 to +12 semitones. Changes preview in real-time as you drag. Includes a reset button to restore original pitch.

#### Convert to MIDI

Submenu with options to convert audio to MIDI format:

- **Use as instrument sample** — Creates a MIDI clip with a single note that triggers this audio. The audio becomes the "instrument" that plays when MIDI notes are triggered. Useful for creating melodic patterns from a single sound (drum hit, synth stab, vocal chop, etc.).

- **Detect melody notes** — Uses AI to analyze the audio and transcribe detected melody into MIDI notes. The resulting MIDI clip plays back using a piano sound. Useful for extracting melodic content from recordings.

**Multi-clip selection:** When you select multiple audio clips that share the same source, "Convert to MIDI" merges them into a single MIDI pattern. Each clip becomes a note, with position and pitch preserved. Useful for converting chopped-up samples back into a playable pattern.

#### Sync Tempo

*Only appears if the source audio has tempo information and the clip isn't already synced.*

Automatically adjusts playback speed to match the project tempo based on the source audio's original BPM.

#### Reset Speed

*Only appears if clip speed has been modified (not 1x).*

Resets playback speed to normal (1x).

#### Reset Width

*Only appears if the clip has been trimmed.*

Removes any trim/cut bounds, restoring the clip to show the full source audio duration.

#### Fade

Apply volume fades to the clip:

- **Click "Fade"** — Applies 10% fade to both ends
- **Fade In** — Preset options: 5%, 10%, 25%, 50% of clip duration
- **Fade Out** — Preset options: 5%, 10%, 25%, 50% of clip duration
- **Reset Fades** — Remove all fades (only appears if fades exist)

Fades are constrained so fade in + fade out cannot exceed clip duration.

#### Render

- **Burn to Track** — Renders the clip to a new file, replacing it on the track. Useful for committing effects or consolidating. For audio clips this produces a fresh audio clip.
- **Download** — Exports the clip as a file.
- **Share as Sound** / **Share as Video** — Renders, publishes the result to your library, and copies the share link. The label and target depend on whether the clip carries visual content.

#### Source Audio

Manage the clip's underlying audio source:

- **Change Audio** — Opens import dialog to replace the source with a different audio file
- **View Audio Info** — Opens the source audio's page (if it's from TwoShot library)
- **Preview** — Plays a short preview of the source audio
- **Download** — Downloads the original source audio file
- **Recreate AI source** — Re-generate with different parameters (only for AI-generated sources)

#### Standard Operations

- **Copy** (`Ctrl+C`) — Copy clip to clipboard
- **Duplicate** (`Ctrl+D`) — Create a copy at the same position
- **Delete Clip** (`Del`) — Remove the clip

---

### Video Clip Context Menu

Right-click on a video clip to see these options:

#### Ask AI

Opens an AI session about this video clip (same model as audio clips — independent per-clip session).

#### Get Transcript

*Only on videos with an audio track. Hidden once a transcript is cached.*

Fetches a transcript for the video's audio. The transcript appears in the Transcript panel / main view.

#### Extract Audio

Extracts the video's audio track to a new audio clip on the next track and silences the video. The video clip remains and the extracted audio can be edited independently — useful for processing video audio separately (removing background noise, adding effects, etc.).

#### Restore Audio

Re-enables audio playback from the original video. The previously extracted audio clip is left in place — delete it manually if you don't want it.

#### Snapshot

Captures a frame of the video as a new image clip. Choose **Start Frame** or **End Frame** from the submenu.

#### Fit to Canvas

Resets the clip's viewport to center position at 100% scale.

#### Fill Canvas

Auto-scales the video to cover the entire canvas, handling letterbox/pillarbox based on aspect ratio differences.

#### Set Canvas to *(aspect ratio)*

Sets the project canvas aspect ratio to match this clip's source dimensions. The label shows the actual ratio (e.g. "Set Canvas to 16:9").

#### Opacity

Quick presets: 100%, 75%, 50%, 25%. Also includes a custom option with a 0–100% slider that applies instantly.

#### Reset Width

*Only appears if the clip has been trimmed.* Removes any trim/cut bounds.

#### Reset Speed

*Only appears if speed has been modified.* Resets playback speed to 1.0×.

#### Render

- **Burn to Track** — Renders the clip to a fresh video clip, replacing the original on the track.
- **Download** — Exports as a video file.
- **Share as Video** — Renders, publishes to your library, and copies the share link.

#### Standard Operations

- **Rename** — Rename the clip
- **Fade** — Same as audio clips
- **Copy** (`Ctrl+C`) — Copy clip to clipboard
- **Duplicate** (`Ctrl+D`) — Create a copy
- **Delete Clip** (`Del`) — Remove the clip

---

### Image Clip Context Menu

Right-click on an image clip to see these options:

#### Ask AI

Opens an AI session about this image clip.

#### Fit to Canvas

Resets the clip's viewport to center position at 100% scale.

#### Fill Canvas

Auto-scales the image to cover the entire canvas.

#### Set Canvas to *(aspect ratio)*

Sets the project canvas aspect ratio to match this image's dimensions.

#### Opacity

Quick presets: 100%, 75%, 50%, 25%. Custom slider available.

#### Standard Operations

- **Rename** — Rename the clip
- **Copy** (`Ctrl+C`) — Copy clip to clipboard
- **Duplicate** (`Ctrl+D`) — Create a copy
- **Delete Clip** (`Del`) — Remove the clip

---

### MIDI Clip Context Menu

Right-click on a MIDI clip to see these options:

#### Ask AI

Opens an AI session about this MIDI clip.

#### Merge MIDI Clips

*Only appears when multiple MIDI clips with the same source are selected.*

Combines all selected MIDI clips into a single clip, preserving all note positions and timing.

#### Convert to Audio clips

Explodes the MIDI clip into individual audio clips — one for each note. Each resulting audio clip:
- Is positioned at the note's start time
- Has pitch offset matching the note's pitch
- Has volume matching the note's velocity
- Has duration matching the note's length

Useful for further processing individual notes or creating variations.

#### Export MIDI File

Downloads the clip's notes as a standard `.mid` MIDI file for use in other DAWs.

#### Reset Width

*Only appears if the clip has been trimmed or has a custom length.*

Removes trim bounds and custom length, restoring the clip to its natural size based on note content.

#### Fade

Same as Audio Clips — apply fade in/out with presets.

#### Render

- **Burn to Track** — Renders MIDI to audio
- **Download** — Exports as audio file

#### Source Audio

Manage the instrument sample used for playback:

- **Change Audio** — Replace the instrument sample. Includes "Design custom instrument" option to generate a one-shot sample using AI.
- **View Audio Info** — Opens the source sample's page
- **Preview** — Plays a short preview of the instrument sample
- **Download** — Downloads the instrument sample file

#### Standard Operations

- **Copy** (`Ctrl+C`) — Copy clip to clipboard
- **Duplicate** (`Ctrl+D`) — Create a copy
- **Delete Clip** (`Del`) — Remove the clip

---

### Group Clip Context Menu

Right-click on a group clip to see these options:

#### Ask AI

Opens an AI session about this group (the assistant gets the group's contents as context).

#### Get Transcript

*Only on groups that contain audio or video clips. Hidden once all contained audio is transcribed.*

Transcribes every child audio/video clip in the group in parallel.

#### Reset Width

*Only appears if the group has been trimmed or has a custom length.*

Removes trim bounds, showing the full group content.

#### Ungroup clips

**Shortcut:** `Ctrl+Shift+G`

Extracts all clips from the group back to the parent timeline. The group container is removed and its contents become individual clips.

#### Ungroup clips with ghosts

*Only appears if tracks inside the group have looping enabled with ghost clips.*

Same as Ungroup, but also converts any ghost/looped clips into real clips before extracting.

#### Fade

Same as other clip types.

#### Render

- **Burn to Track** — Renders entire group to a single audio clip
- **Download** — Exports as audio file

#### Standard Operations

- **Copy** (`Ctrl+C`) — Copy clip to clipboard
- **Duplicate** (`Ctrl+D`) — Create a copy
- **Delete Clip** (`Del`) — Remove the clip

---

### Track Context Menu

Right-click on a track header to see options:

#### Ask AI

Opens an AI session about this track (the assistant gets the track and its clips as context). Same per-track independent session model as the Ask AI button on the track header.

#### Enable / Disable Magnetic

Toggles magnetic mode on the track. When magnetic is on, clips on this track auto-snap together end-to-end with no gaps, and deleting a clip ripples the others to close the gap. The current state is shown by the **MAGNETIC** indicator on the track header.

#### Select All

*Only appears if track has multiple clips.*

Selects all clips in this track. **Shortcut:** `Ctrl+Shift+A` (when track is selected)

#### Transform

Opens the same AI transformation menu as clips. If the track has multiple clips, you'll be prompted to burn the track first (combines all clips into one audio file for processing).

#### Rename Track

Opens a dialog to change the track name.

#### Duplicate Track

**Shortcut:** `Shift+D`

Creates a copy of the track with all its clips.

#### Order (submenu)

- **Move Track Up** (`Shift+Up`) — Move track up one position
- **Move Track Down** (`Shift+Down`) — Move track down one position
- **Insert Track Above** — Add empty track above
- **Insert Track Below** (`Shift++`) — Add empty track below

#### Delete Track

**Shortcut:** `Shift+Del`

Removes the track and all its clips.

#### Render (submenu)

The labels in this menu adjust based on whether the track contains visual content.

- **Burn Track** — Renders all clips on the track to a single clip and replaces them on the same track. Tracks containing video or images produce a single video clip; audio-only tracks produce an audio clip. Loop ghosts are baked in.
- **Download Track** / **Download Track as Video** — Exports the rendered track as a file. Pro feature.
- **Share as Sound** / **Share as Video** — Renders, publishes the result to your library, and copies a share link to your clipboard. The label switches between Sound and Video based on the track's content.

#### Looping (submenu)

*Only appears when looping is enabled on the track.*

- **Disable Looping** — Turn off track looping
- **Change Loop Interval** — Set loop length in beats
- **Burn Ghost Clips** — Convert ghost/looped clips to real clips

---

### Project Menu

Click the project title dropdown to access:

**Getting Started:**
- **New Empty Session** — Start a fresh project
- **Load Demo Session** — Load an example project
- **User Manual** — Open this guide

**Tempo:**
- **Set Tempo** — Switch the project to Music Mode. The starting BPM is inferred from clips that have tempo metadata (or 120 if none do).
- **Clear Tempo *(N BPM)*** — Drop back to Non-Music Mode. The current BPM is shown in the menu label so you can see what you're discarding.

**Video** *(only when the project contains visual clips)*:
- **Aspect Ratio** — Pick a canvas aspect ratio (16:9, 9:16, 1:1, 4:3, 4:5, 21:9, or Custom).

**Project Options:**
- **Rename Session** — Change the project name
- **Make a Copy** — Duplicate the entire project
- **Open Session** — Browse recent projects
- **Delete Session** — Permanently remove the project (asks whether to also delete the linked note)
- **Close Session** — Exit without deleting

---

## Timeline Controls

### Header Controls

The timeline header contains these controls (left to right):

1. **Play/Pause Button** — Start or stop playback. Shows a "SOLO" badge (yellow) when solo mode is active — click the badge to disable solo.
2. **Project Title** — Click to rename, dropdown for project options (including Set/Clear Tempo and Aspect Ratio).
3. **Undo/Redo** — History navigation.
4. **Mouse Mode Dropdown** — Switch between modes (S, P, T, X, C, V, D, Z).
5. **Tempo Pill** — Adjust project BPM by typing, scrolling, or pressing the arrow keys while focused. Hover the pill to reveal an X button that clears the tempo (drops to Non-Music Mode). The pill is only visible in Music Mode. Valid range: **40–500 BPM**.
6. **Metronome Toggle** — Enable/disable the click track (red when active). Music Mode only.
7. **Snap Matrix** — A magnet icon (global snap on/off; red when any snap target is enabled) and a settings icon that opens the Snap Matrix panel. Hold `Alt` to temporarily invert the snap state while dragging. See [Snap Matrix](#snap-matrix) for full details.
8. **Zoom Controls** — Zoom in/out and zoom-to-fit buttons.

**Selection Pill** (appears when 2+ clips are selected):
- Clip count display
- Mute toggle (`M`)
- Copy (`Ctrl+C`)
- Burn to audio (`Ctrl+B`)
- Group (`Ctrl+G`)
- Delete (`Del`)
- More menu: Duplicate, Auto Extend, Select All, Invert Selection, Clear Selection, Ungroup

**Right Section:**
- **Export Menu** — Render project to audio/video
- **Share Button** — Share/publish options

### Music Mode vs Non-Music Mode

**Music Mode** (tempo is set):
- Tempo pill and metronome visible in the header
- Timeline ruler shows bars and beats
- Grid options are beat-based (subdivisions from 1/4 of a beat up to multi-bar values)
- Clip positions are stored as beats
- Ideal for music production

**Non-Music Mode** (no tempo):
- No tempo or metronome in the header
- Timeline ruler shows time (seconds/minutes)
- Grid options are time-based (e.g. 100 ms, 250 ms, 500 ms, 1 s, 2 s, 5 s, 15 s, 1 min)
- Clip positions are stored as seconds
- Ideal for podcasts, video editing, sound design, ambient/field recording

**Switching modes:**
- Hover the tempo pill and click the X to clear the tempo and drop to Non-Music Mode.
- Type a BPM in the pill, or use **Set Tempo** in the project menu, to enter Music Mode.
- Enabling **Beats** in the Snap Matrix on a no-tempo project also enters Music Mode — the BPM is automatically inferred from your clips' tempo metadata (the longest tagged clip wins; falls back to 120 BPM if no clip has tempo info).

A project with no tempo can still contain tempo-synced clips — they just play at their native speed and the timeline stays time-based.

### Playhead

- **Green vertical line** shows current playback position
- **Click in ruler** to move playhead
- **Loop region** (if set) shows as highlighted area

### Solo Mode

Solo is **domain-aware**: it isolates whichever signal makes sense for the clip you soloed.

- Soloing an **audio clip** mutes other audio but leaves the visuals alone.
- Soloing a **video clip with audio** plays only that video's audio and visuals.
- Soloing a **video clip with no audio**, or an **image clip**, hides other visuals and mutes other audio.

When solo is active a yellow **SOLO** badge appears on the play button — click it to disable.

---

## Preview Panel

The Preview Panel is a visual canvas that appears when your project contains video or image clips. It shows the composited visual output at the current playhead position, plus a transport bar and a fullscreen toggle.

### Canvas

The canvas renders all visible video/image clips at the current playhead position, layered by track order and clip type. It auto-sizes to fit its container while preserving the project's aspect ratio.

**Z-order (back to front):**
1. Clips on lower tracks (higher index) render behind clips on higher tracks.
2. On the same track: video clips behind image clips.
3. Same track and type: earlier start position renders behind.

VP9 alpha videos are rendered with transparency over the underlying clips, and animated GIFs and animated WebPs play back like any other video.

While the canvas is filling its preview cache, you may briefly see a low-resolution version of a frame before it sharpens — that's intentional, not a glitch.

### Transport Bar

Along the bottom of the preview is a transport bar with:

- A **play/pause** button
- A draggable **scrubber** showing the current position
- A current/total **time display** in `mm:ss / mm:ss` form
- A **fullscreen** button on the right

The transport bar is always visible in the embedded preview. In Fullscreen Mode it auto-hides after a couple of seconds and reappears whenever you move the mouse.

### Fullscreen Mode

Click the fullscreen button in the preview to expand the canvas to fill the main area (URL hash becomes `#preview`). Click it again, use the Timeline button in the bottom mode switcher, or remove the hash to exit.

In Fullscreen Mode:

- Mouse mode is restricted to **Select**, **Clone**, and **Delete** — the other modes are unavailable.
- A small mouse-mode switcher appears beside the fullscreen button.
- The shared playback shortcuts (Space, Ctrl+Space, Ctrl+Z, Ctrl+S, mode keys) still work.
- `Tab` / `Shift+Tab` cycle through the clips visible at the playhead.
- `Delete` removes the selected clips, `Escape` clears the selection.
- In Clone mode, dragging a clip duplicates it on the canvas; hold `Ctrl`/`Cmd` during the drag to move instead.

### Scrubber (Transport Bar)

The scrubber supports more than simple seeking:

- **Hover** over the scrubber to highlight the corresponding **word** in the transcript (when a transcript is available).
- **Click** to seek. **Click and drag** past a small threshold to select a time range on the playhead — useful for looping a region or previewing a section.
- **Arrow keys** (left / right) nudge the playhead by one snap step. Focus the scrubber (tab in) or hover it first; the nudge respects your Snap Matrix settings (beats or seconds, whichever is smaller).

### Aspect Ratio

Click the aspect ratio button in the Preview Panel header to choose a canvas ratio:

- **Auto** — Derived from source video/image content or defaults to 16:9
- **16:9** — Standard widescreen (YouTube)
- **9:16** — Portrait mode (Reels, TikTok, Shorts)
- **1:1** — Square (Instagram)
- **4:3** — Classic video
- **4:5** — Instagram portrait
- **21:9** — Ultra-wide
- **Custom...** — Enter a Width:Height ratio with live preview

You can also right-click any video or image clip and pick **Set Canvas to *(aspect ratio)*** to instantly match the project canvas to that clip's source dimensions.

### Interactions

- **Click on a clip** — Select it (shows a dashed white border with corner handles)
- **Ctrl + Click** — Toggle the clip in the selection (multi-select)
- **Tab** — Cycle through visible clips at the current playhead position
- **Drag a selected clip** — Pan the clip's viewport position
- **Drag corner handles** — Zoom/scale the clip (4 handles)
- **Scroll wheel** — Zoom in/out on the selected clip
- **Right-click** — Opens the same context menu as the clip on the timeline
- **In Paint mode**: **drag** on the canvas to draw a rectangular spatial region for AI generation (see [AI Features](#ai-features))

### Cursor States

- **Default arrow** — Empty canvas
- **Pointer** — Over an unselected clip
- **Grab** — Over a selected clip (ready to drag)
- **Grabbing** — Actively dragging a clip
- **Resize arrows** — Over corner resize handles
- **Crosshair** — Paint mode

---

## MIDI Editor

Access the MIDI editor by double-clicking a MIDI clip or pressing `Enter` with one selected.

### Piano Roll

- **Vertical axis** — Pitch (notes)
- **Horizontal axis** — Time (beats)
- **Click piano keys** — Audition notes
- **Shift + Click row** — Select all notes at that pitch

### Note Editing

- **Add note** — Paint mode (`P`) + click/drag
- **Select note** — Click in Select mode
- **Move note** — Drag horizontally/vertically
- **Resize note** — Stretch mode (`T`) + drag edges
- **Delete note** — Delete mode (`D`) + click, or select + `Delete`
- **Change pitch** — Drag up/down, or use `Up`/`Down` arrows
- **Change velocity** — Volume mode (`V`) + drag up/down

### Velocity Editing

- **Volume mode** (`V`) shows velocity as note opacity
- **Drag up/down** to adjust
- **Right-click** to reset to default (1.0)

### Attack and Release

MIDI clips support envelope controls that shape how each note sounds:
- **Attack** — Fade-in time at the start of each note
- **Release** — Fade-out time after each note ends (default: 0.1s)

---

## Transcript

The Transcript feature gives you a time-aligned text view of every audio and video clip in your project. The section title is called **Lyrics** for projects with tempo and **Transcript** otherwise.

### Opening the Transcript

- **Right-side sidebar tab** — Use the mode switcher pill at the bottom of the screen. The Transcript button appears once the project has transcript content or transcription is underway.
- **Main-view mode** — Clicking Transcript while the sidebar is open (or in the main-view mode switcher) expands transcript into the main area. The URL hash becomes `#transcript` (or `#lyrics` for music projects).
- When both Transcript and Preview are active at the same time, Transcript fills the main area and Preview stays in the right sidebar.

### Requesting a Transcript

Audio, video, and group clips all have a **Get Transcript** item in their right-click menu (marked with a captions icon). The item disappears once the clip is already transcribed — transcripts are cached since audio doesn't change.

Group clips transcribe every child audio/video clip in parallel.

Videos can be transcribed even when Studio still needs to prepare their audio for transcription. If a video's audio has been extracted to a separate clip, the video itself is treated as muted in the transcript.

You can also enable **Auto-transcribe** in the transcript panel header — new clips you add are transcribed automatically. If transcription needs credits or login, Studio prompts you instead of silently failing.

### Working with the Transcript

- **Playback highlighting** — As the project plays, the current word turns green.
- **Click a word** — Jumps the playhead to that word. If the word is off-screen, the timeline scrolls (or zooms out) to frame the region.
- **Shift+click** — Range-select from the previously clicked word to this one.
- **Click and drag** — Draw a selection across words; all words in range are highlighted.
- **Section headers** group the transcript into chunks; clicking a header selects its whole section.
- **Gap breaks** appear between words that are far apart in time.
- **Copy** — A copy button in the panel header copies the transcript text to the clipboard.
- **Download** — The download button exports the transcript as plain text, SRT subtitles, WebVTT subtitles, or JSON.
- **Layout** — The layout button cycles between Mixed (one chronological transcript), Lined (new line when the source clip changes), and Grouped (one paragraph per clip).
- **Sections toggle** — Show or hide section headers when the transcript includes sections.
- **Muted words toggle** — Show all words or hide words from muted clips/tracks.

### Transcript Mouse Modes

The full-screen Transcript/Lyrics view has its own mouse-mode switcher:

- **Select** — Click a word or section to seek and frame it on the timeline; drag or Shift+click to select a range.
- **Split** — Click a word, section, or selected range to split the source clip at spoken boundaries.
- **Delete** — Click a word, section, or selected range to remove that spoken region and close the gap.
- **Paint** — Select words or a section to open an AI Paint prompt using that transcript range as context.
- **Zoom** — Click or drag over words/sections to zoom the timeline to that spoken range.

### Transcript as a Snap Target

When the project has transcribable audio or video, the Snap Matrix gains **Words** and **Sections** rows. Enable their snap toggles to pull the playhead or clip edges to word and section boundaries; enable the cursor toggle to see the nearest word or section label next to the playhead as you scrub.

Turning on word/section snap or cursor labels can start Auto-transcribe, because Studio needs word timings before it can snap to them. If transcription finishes and no words or sections are found, those rows are disabled.

Hovering the **scrubber** on the preview's transport bar also highlights the corresponding word in the transcript, so you can find a specific moment in long recordings without playing through.

---

## Grid and Zoom

### Snap Matrix

The **Snap Matrix** in the header is the single place that controls grid lines, snap targets, and on-playhead cursor labels. It's a pill with two buttons:

- A **magnet icon** — toggles all snap on/off at once. Red when any snap target is enabled, grey when everything is off.
- A **settings icon** — opens the snap matrix panel.

Hold `Alt` at any time to **temporarily invert** the current snap state while dragging.

The panel has one row per snap target, with up to four controls per row:

| Target | Snap (magnet) | Grid lines | Cursor label | Value |
|---|:---:|:---:|:---:|---|
| **Beats** | ✓ | ✓ | ✓ | Subdivisions from a quarter-beat up through multi-bar |
| **Seconds** | ✓ | ✓ | ✓ | 100 ms, 250 ms, 500 ms, 1 s, 2 s, 5 s, 15 s, 1 min, … |
| **Clip edges** | ✓ | — | ✓ | — |
| **Words** *(when the project has transcribable audio/video)* | ✓ | — | ✓ | — |
| **Sections** *(when the project has transcribable audio/video)* | ✓ | — | ✓ | — |

- **Snap** (magnet, red when on) — pulls the dragged clip or playhead toward targets of this type.
- **Grid lines** (grid icon, blue when on) — draws grid lines on the timeline. Beats and Seconds only.
- **Cursor label** (selector icon, yellow when on) — shows the nearest target's label (a word, a section name, a clip edge, or a beat/second value) next to the playhead as you scrub.
- **Value** — dropdown for Beats and Seconds. Scroll the row to step through values.

**Scroll** on the top-level pill steps every row that has grid lines on. **Scroll on a specific row** in the panel steps only that row. **Alt+Scroll** over the timeline, or **Alt** + **+** / **Alt** + **-**, steps every enabled Beats/Seconds target whether it is enabled for snap or grid lines.

Snap toggles are stored in your browser and shared across projects. Beats/Seconds values are project-aware, so each project starts with a useful default scaled to its duration. A "Reset to defaults" button restores the project-aware default (beats for music projects, seconds otherwise).

**Beats row with no tempo**: the row is dimmed but still clickable. Clicking infers a BPM from your clips (falling back to 120) and enables the toggle in one step.

**Words and Sections rows**: these appear when the project has audio or video that can be transcribed. Turning on their snap or cursor labels can start Auto-transcribe so Studio has word timings to snap to.

When snap is enabled the studio looks for the closest target on **both edges** of the dragged clip and picks whichever gives a tighter snap. Snap also applies when trimming clip edges and when adding or moving MIDI notes.

### Magnetic Tracks

Magnetic mode is **per track** and is separate from the Snap Matrix. Toggle it with the **MAGNET / MAGNETIC** indicator on the track header (or via the track context menu's Enable/Disable Magnetic item).

- When magnetic is on, clips on that track are auto-snapped together end-to-end with no gaps.
- Deleting a clip ripples the others to close the gap.
- Magnetic only kicks in when the track has more than one clip (or has loop ghosts).

### Zoom Controls

- **Zoom buttons** — Zoom in/out from the centre
- `Ctrl + Scroll` — Zoom at cursor position
- `Z` key — Enter Zoom mode (click clips to zoom to bounds, drag to zoom to area)
- `G` key — Goto/zoom to selection (or fit all if nothing is selected)
- `Ctrl + 0` — Zoom to fit all content (with a small fixed padding so clips don't touch the edge)
- `Ctrl + Right-drag` — Box zoom to region

### Loop Handle

Tracks with looping enabled show a draggable loop handle at the loop interval. Drag it left or right to change the loop length live; a tooltip displays the current interval as you drag.

---

## Track Management

### Adding Tracks

- **Shift + Plus** — Insert new track below selection
- **Drag audio** onto empty area — Creates new track with clip
- **Right-click track** > Order > Insert Track Above/Below

### Reordering Tracks

- **Drag track header** up or down
- Multiple selected tracks move together
- 5px minimum drag to activate
- Use **Shift+Up/Down** arrows for keyboard reordering

### Track Controls

Each track header has:

- A **drag handle** on the left (≡) for reordering
- An editable **track name** — click to rename
- A **shimmering AI status** that appears when an AI session is processing this track
- **Mute** / **Solo** buttons
- A **MAGNET / MAGNETIC** indicator for per-track magnetic mode
- An **Ask AI** button (Coproducer icon) — collapsed until you hover the track or AI is active. When active it glows green and spins.
- A **volume slider**
- A three-dot menu with the full track context menu

### Track Looping

Enable looping to repeat a track's content:

1. Right-click the track and enable looping
2. Set the loop interval (in beats, or "auto" to detect from clip length). You can also drag the loop handle on the track to set it interactively.
3. **Ghost clips** appear showing where the content will repeat (works for audio, video, image and group clips)
4. **Burn Ghost Clips** to convert ghosts to real clips

When you add a clip with musical content (audio with BPM longer than ~5 s, or MIDI) to an empty track, looping is enabled automatically.

### Pseudo-Track (AI Paint)

An empty pseudo-track appears at the top of the timeline in every mouse mode except Delete and Zoom. Drag on it to create a brand-new AI Paint region without first creating a track manually. If you start from another mode, Studio switches to Paint after the drag is committed so the prompt and placeholder behave like normal AI Paint.

### Deleting Tracks

- **Shift + Delete** — Delete selected tracks
- **Right-click** > Delete Track
- Clips on deleted tracks are also removed

---

## Clip Operations

### Creating Clips

- **Drag audio** from browser onto timeline
- **Import audio** via URL or file upload
- **Import video** via URL or file upload
- **Import image** via URL or file upload
- **Add Content / drag-drop placement** — Video and image items are added as new top tracks so the latest visual appears in front; audio and MIDI items are added toward the bottom.
- **Generate audio** using AI models
- **Record audio** using microphone input
- **Record video** using camera input
- **Paint MIDI** in the MIDI editor
- **AI Paint** on the timeline (Paint mode `P` on timeline)

### Editing Clips

- **Move** — Drag in Select mode
- **Resize** — Drag edges in Stretch mode
- **Split** — Click in Split mode
- **Duplicate** — `Ctrl+D` or Ctrl+Drag
- **Delete** — Select + `Delete` or Delete mode

### Grouping

- **Select multiple clips** across tracks
- **Ctrl+G** to group into single container
- **Ctrl+Shift+G** to ungroup
- **Double-click group** to edit contents

### Burn Selection

- Select clips and press `Ctrl+B` / `Cmd+B`
- Renders selected clips to a single audio or video clip, depending on whether the selection contains visual content
- Useful for:
  - Committing MIDI to audio
  - Consolidating multiple clips
  - Preparing for AI transformation
  - Reducing CPU load

### Auto-Extend

- `Ctrl+L` / `Cmd+L` extends selected clips
- Stretches right edge to meet the next clip
- Useful for filling gaps between clips

---

## Rendering and Export

### Burn Track

Renders all clips on a track into a single clip and replaces them on the same track. The output type is auto-detected:

- Tracks with audio only produce a single audio clip.
- Tracks containing video or images produce a single video clip.

Loop ghosts are baked in. The original track is reused (no muted-group wrapping), so the track's identity stays stable.

### Burn Selection

Press `Ctrl + B` to render the selected clips into a single new clip on the first affected track. Empty tracks are pruned automatically. Same audio/video auto-detection as Burn Track.

### Unburn

Burned clips can be rehydrated back into their original source clips and tracks:

- Burned audio and video clips show a **flame icon** in their header (next to the clip type icon) when they can be unburned.
- An **Open-in-fullscreen** button in the clip's action bar rehydrates the clip AND opens the new group editor in one click — mirroring how Group clips open.
- The clip's right-click menu has an **Unburn** item for the same action.

Unburning is the inverse of burning: single-clip sources inline-replace the burned clip in place; multi-clip sources create a group at the clip's position and open it for editing.

### Download / Render Dialogs

Downloads and renders go through a consistent dialog:

- **Audio downloads** show a name field, format dropdown, and quality tier.
- **Video downloads** also show:
  - **Download Type** — Video, Sequence (GIF/WebP), or Audio-only extraction.
  - **Format** — WebM/MP4/MKV/MOV for video, GIF/WebP for sequence, or MP3/FLAC/WAV/OGG for audio.
  - **Quality** — Low / Medium / High. *High requires Pro.*
  - **Resolution presets** — pre-computed from the clip sources, capped at the project's native size. *Above 720 p requires Pro.*
  - **Width × Height** — editable number inputs (linked by aspect ratio; minimum 120 px per side).
- A **"Don't show this window again"** checkbox remembers your last settings, so subsequent downloads of the same kind go straight through. When this is enabled, the export menu shows a small settings button next to the fast download action so you can reopen the dialog.

### Share as Sound / Share as Video

Available on tracks (and on individual clips) under the Render submenu. Renders the content, publishes it to your library, and copies a share link to your clipboard. The label switches between Sound and Video automatically based on whether the source contains visual content.

### Export Menu

Click the download icon in the header to export the full project:

- **Download Transcript** *(when transcript words are available)*
  - **Plain text (.txt)**
  - **SubRip subtitles (.srt)**
  - **WebVTT subtitles (.vtt)**
  - **JSON (full word-level data)**
- **Render**
  - **Full Session** — Render the entire project as one file. Becomes a video if the project contains visual content, otherwise a `.WAV` audio file.
  - **Track Stems** — Render each non-muted track as a separate file (video for visual tracks, audio for others). Pro feature.
  - **Render Selection** *(only when 2+ clips are selected)* — Render just the selected clips.
  - **Download Media** / **Download Sounds** — Downloads each underlying audio, video, and image file individually.
- **Export Project File** — Coming soon: FL Studio, Ableton Live, Logic Pro, Pro Tools.

---

## Sharing and Collaboration

### Share Link

Click the Share button in the header to copy a shareable link to your project. Recipients can view (and optionally edit) the project depending on the permission level you set.

### Manage Sharing

The **Manage Sharing** item at the top of the share menu opens a dialog where you can grant per-user access (view or edit), invite people by username/email, change visibility, and revoke access.

### Share as Sound / Share as Video / Pack

The share menu also lets you publish the project as a single Sound or Video, or — when your project contains multiple unique audio or media sources — as a **Sound Pack** or **Media Pack** that bundles them all together. Each option renders, publishes, and copies a link to your clipboard.

### Visibility

Projects (and notes) have one of three visibility states:

- **Private** — Only you (and people you've explicitly shared with) can access it.
- **Unlisted** — Anyone with the link can access it, but it isn't discoverable.
- **Public** — Listed publicly and discoverable on TwoShot.

### Session Shared By Indicator

When you open a project (or a note) that someone else shared with you, a "Shared by @username" indicator appears in the header. It shows even if you have edit access, so you always know whose work you're collaborating on.

---

## AI Features

TwoShot's AI assistant — the **Coproducer** — is woven into the studio at the project, track, and clip level. You can talk to it in a sidebar (or popup), ask it about a specific clip or track, or have it generate fresh content directly on the timeline or canvas.

### Ask AI on Clips

Every clip type — audio, MIDI, video, image, group — has an **Ask AI** button (a circular Coproducer icon) in its header. Click it to open a small chatbox attached to that clip; type a question or instruction and the assistant responds with the clip already loaded as context.

While the AI is working on a clip:

- The Ask AI icon glows green and spins.
- A shimmering status message ("Processing…", "Rendering audio…", "Generating video…", etc.) appears in place of the clip's duration label.
- A stop button is available to cancel.

Each clip's AI session is **independent**, so you can have several clips generating in parallel — they don't step on each other.

### Ask AI on Tracks

Tracks have an Ask AI button in the header (collapsed until you hover the track or AI is active). It uses the same per-track independent session model as clips, with the same green-spinning indicator and shimmer status. The track context menu also has an **Ask AI** entry.

### Audio Transformations

Right-click an audio clip and choose **Transform** to access the full library of AI audio tools — see [Audio Clip Context Menu](#audio-clip-context-menu) above for the full list. Common transformations include:

- **Split Stems** — Separate audio into individual instruments
- **Cleanup Vocals**, **Remove Reverb**, **Extract Vocals**
- **Change Voice** — Swap to a different voice
- **Reimagine** with a text prompt
- **Extend** — Generate a continuation of the audio
- **Upscale** — Improve audio quality
- **Convert to MIDI** → **Detect melody notes** — Transcribe a melody from audio

You can also right-click a track > **Transform** to apply an AI tool to the whole track (it's burned first if needed).

### AI Paint

Switch to Paint mode (`P`) and **drag on the timeline** to draw a region. The region becomes an editable AI clip placeholder.

1. Resize the placeholder by dragging its edges, then type a prompt in the floating chatbox attached to it. Add image, video, or note attachments if you like.
2. Submit. The placeholder shows live progress and an estimated time remaining.
3. Cancel with the stop button, or delete the placeholder before submitting.

The empty **pseudo-track at the top of the timeline** lets you paint a brand-new track in one move without first creating one manually. It is available in most timeline modes; dragging it starts AI Paint and then switches the mouse mode to Paint.

In Paint mode, clicking an existing clip opens an Ask AI prompt for that clip, while dragging across the clip creates a paint region.

If you reload or close the project mid-generation, the placeholder reappears with live progress when the project reopens — you don't lose anything.

### Spatial Regions in the Preview Canvas

In Paint mode you can also **drag on the Preview canvas** to draw a rectangular spatial region. The AI is told to fit its generated content into that area of the visual frame — useful for placing a generated element in a specific part of a shot or composition.

### Transcript Ranges

In the full-screen Transcript/Lyrics view, Paint mode lets you select words or sections and open an AI prompt tied to that spoken range. This is useful for replacing, extending, or illustrating a specific lyric, line, or spoken moment.

### Notifications

If you ask the AI about a second clip or track while another one is still generating, the new request runs as an independent session in parallel. When it completes, you'll get a **browser notification** with the AI's response. Clicking the notification opens that session in the assistant sidebar.

### Studio Deep Links

URLs like `/studio/<projectId>?c=<clipId>` or `?t=<trackId>` open the project and **auto-zoom** the timeline to frame the linked clip or track. The Coproducer's studio chips link this way, so clicking a chip in the assistant takes you straight to the relevant part of the timeline.

### Assistant Sidebar / Popup

The AI Assistant lives as a right-side sidebar on desktop and a bottom-sheet popup on narrow screens. Open it with `Ctrl + /`, by clicking any Ask AI button, or via a notification. Close it with the X, with `Escape`, or by clicking outside.

---

## Notes

The Notes sidebar is a rich text editor that's linked to your studio project. Each project gets a linked note automatically, and you can also browse and create notes independently of any project.

### Note Variants

A note's label and URL adapt to the kind of project it's linked to:

- **`/note/<id>`** — A plain note (default for projects with no tempo and no visual content).
- **`/lyrics/<id>`** — Used when the linked project is a music project (has tempo).
- **`/script/<id>`** — Used when the linked project contains visual content but no tempo.
- **`/notes`** — Browse all your notes.

The variant updates live from the project's content, so adding tempo to a project promotes its note from "script" to "lyrics" automatically.

### Accessing Notes

- From the studio: open the Notes sidebar to edit the linked note in place.
- From the sidebar header: click the fullscreen button to open the note as a full page.
- Standalone: browse `/notes` and open any note. If it's linked to a project, you can jump to the studio from the note.

### Features

- **Rich text editing** — Full formatting with sections and headings
- **Auto-linked to project** — Each project's note is automatically associated with it; opening one can open the other
- **Linked session resume** — When a project loads, any previous Coproducer conversation is restored silently. Open the assistant to see it.
- **Undo/Redo** — `Ctrl + Z` / `Ctrl + Shift + Z` inside the editor
- **Sharing** — Notes have the same Private/Unlisted/Public visibility model as projects, and the same "Shared by @username" indicator when someone else owns them. Sharing visibility is kept in sync between a note and its linked project.

---

## Tips and Workflows

### Speed Tips

1. **Use single-key mode switches** — `S`, `T`, `X`, `C`, `V`, `D`, `P`, `Z` are faster than the dropdown
2. **`Ctrl+D` for quick duplication** — Faster than copy/paste for repeating clips
3. **`Z` for zoom mode** — Click clips to zoom in, right-click to zoom out
4. **`G` for quick navigation** — Jump to your selection (or fit all if nothing's selected)
5. **`Tab` / `Shift+Tab`** — Navigate between clips without clicking
6. **Hold `Alt` to invert snap** — Fine-tune positioning while snap is enabled (or temporarily snap while it's off)
7. **`Tab` in the Preview Panel** — Cycle through overlapping visual clips at the playhead
8. **`Ctrl+/` opens the AI Assistant** anywhere in the studio
9. **Press `P` and drag** to AI-generate a clip directly on the timeline
10. **Hover the scrubber** to find a moment by word — the transcript highlights as you move

### Common Workflows

**Generating something with AI Paint:**
1. Press `P` to enter Paint mode, or drag on the pseudo-track at the top of the timeline
2. Drag on the timeline to draw a region
3. Type a prompt in the floating chatbox and submit
4. Watch live progress on the placeholder; cancel with the stop button if needed

**Constraining a generation to part of the frame:**
1. Press `P` to enter Paint mode
2. Drag a rectangle on the **Preview canvas** to define the spatial region
3. Type your prompt and submit — the AI fits its output to that area

**Asking AI about a specific clip or track:**
1. Click the Coproducer icon on the clip header (or the track header)
2. Type your question
3. The clip/track's AI status indicator turns green and spins; the response opens in the assistant sidebar (or arrives as a notification if you've moved on)

**Rendering a video:**
1. Either burn the visual track (track menu → Render → Burn Track) or use the header **Export → Full Session**
2. In the dialog, pick a download type/format, quality, resolution preset, or custom width × height
3. Hit Render & Download

**Navigating by lyrics / transcript:**
1. Right-click an audio or video clip and pick **Get Transcript** (or enable Auto-transcribe in the transcript panel)
2. Open the Transcript via the mode switcher pill (or expand it to the main area)
3. Click a word to jump the playhead there; Shift+click or drag to select a range
4. Turn on Words or Sections in the Snap Matrix to make the playhead snap to spoken boundaries

**Editing from the transcript:**
1. Open Transcript/Lyrics full-screen
2. Choose Split, Delete, Paint, or Zoom from the mouse-mode switcher
3. Click a word or section, or drag across a word range
4. Studio applies the action to the matching timeline region

**Recovering the source of a rendered clip:**
1. Find a burned clip that shows a flame icon in its header
2. Click the Open-in-fullscreen button in the clip's action bar (or pick Unburn from its menu)
3. The clip rehydrates into its source tracks — if it came from multiple clips, a group opens for editing

**Arranging a loop:**
1. Import your loop audio
2. Use `Ctrl+D` to duplicate
3. Position copies using arrow keys
4. Enable snap (magnet icon in the header) for tight alignment

**Editing MIDI velocity:**
1. Open MIDI clip (`Enter` or double-click)
2. Switch to Volume mode (`V`)
3. Drag notes up/down to adjust velocity
4. Right-click to reset any note to default

**Quick split and rearrange:**
1. Switch to Split mode (`X`)
2. Click to split at desired points
3. Switch back to Select mode (`S`)
4. Drag sections to rearrange

**Creating variations:**
1. Select clips to vary
2. `Ctrl+D` to duplicate
3. Move duplicates to new position
4. Edit the copies while preserving originals

**Separating stems:**
1. Import your audio
2. Right-click > Transform > Stem Separation
3. Wait for processing
4. Each stem appears as a new clip
5. Mute/solo individual stems as needed

**Preparing for export:**
1. Burn any MIDI clips to audio
2. Organize tracks logically
3. Set proper track volumes
4. Use the header **Export → Full Session** for a single mixed file, or **Track Stems** to render each track separately

**Adding video to a music project:**
1. Import video via URL or from your library
2. Place video clip on a track
3. Use Preview Panel to adjust viewport (pan/zoom) and crop
4. Set aspect ratio for your target platform (16:9 for YouTube, 9:16 for Reels)
5. Extract audio from video if you want to process it separately
6. Layer image clips for title cards, adjust length to match sections

**Non-music project (podcast, ambience):**
1. Hover the tempo pill and click the X to clear the tempo (drops to Non-Music Mode)
2. Switch the grid to **Seconds** for time-based positioning
3. Import your audio or video content
4. Position clips using the seconds grid — no BPM math needed

**Creating a visual slideshow:**
1. Set the canvas aspect ratio for your target platform (16:9 for YouTube, 9:16 for Reels, etc.)
2. Import images and place as image clips on a track
3. Set each image clip's length to match the desired display duration
4. Use viewport controls in the Preview Panel to pan/zoom each image
5. Add audio tracks underneath for music or narration
6. Export as video

### Modifier Key Summary

- **Ctrl/Cmd** — Multi-select, zoom, quick operations
- **Shift** — Range select, track operations, extend behavior
- **Alt** — Temporarily invert the current snap state while dragging
- **Right-click** — Context menu, special mode actions

---

## Cursor Indicators

The cursor changes to show what action will occur:

- **Default arrow** — Select mode
- **col-resize** — Split mode or edge resize
- **ns-resize** — Volume adjustment
- **ew-resize** — Stretch mode
- **copy** — Clone mode
- **not-allowed** — Delete mode
- **crosshair** — Paint mode (timeline or canvas), or selection box
- **cell** — Toggle selection box
- **zoom-in** — Zoom selection box
- **pointer** — Over an unselected clip in the Preview Panel
- **grab/grabbing** — Moving a clip in the Preview Panel
- **nwse-resize / nesw-resize** — Over corner resize handles in the Preview Panel

---

## Need Help?

If you can't find what you're looking for or need assistance:

1. **Use the "Ask AI" button** in the top-right corner to get personalized help
2. **The AI assistant** can help with specific tasks, answer questions about features, and guide you through workflows

---

*Last updated: April 30, 2026*
