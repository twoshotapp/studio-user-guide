# TwoShot Studio User Guide

Welcome to the TwoShot Studio! This comprehensive guide covers all keyboard shortcuts, mouse controls, and features to help you work efficiently.

---

## Table of Contents

1. [Quick Reference](#quick-reference)
2. [Clip Types](#clip-types)
3. [Mouse Modes](#mouse-modes)
4. [Keyboard Shortcuts](#keyboard-shortcuts)
5. [Mouse Interactions](#mouse-interactions)
6. [Context Menus](#context-menus)
7. [Timeline Controls](#timeline-controls)
8. [MIDI Editor](#midi-editor)
9. [Grid and Zoom](#grid-and-zoom)
10. [Track Management](#track-management)
11. [Clip Operations](#clip-operations)
12. [Rendering and Export](#rendering-and-export)
13. [AI Transform Features](#ai-transform-features)
14. [Tips and Workflows](#tips-and-workflows)

---

## Quick Reference

### Essential Shortcuts Cheat Sheet

- `Space` — Play/Pause
- `Ctrl+Z` / `Cmd+Z` — Undo
- `Ctrl+Shift+Z` / `Cmd+Shift+Z` — Redo
- `Ctrl+S` / `Cmd+S` — Save
- `Delete` or `Backspace` — Delete Selection
- `Ctrl+D` / `Cmd+D` — Duplicate
- `Ctrl+C` / `Cmd+C` — Copy
- `Ctrl+V` / `Cmd+V` — Paste
- `Ctrl+A` / `Cmd+A` — Select All
- `Z` — Zoom mode (click clips to zoom to bounds)
- `G` — Goto/zoom to selection (or fit all)
- `Ctrl+0` / `Cmd+0` — Zoom to Fit

### Mouse Mode Quick Keys

- `S` — **Select**: Select and move clips
- `T` — **Stretch**: Resize clip edges
- `X` — **Split**: Cut clips at cursor
- `C` — **Clone**: Duplicate while dragging
- `V` — **Volume**: Adjust clip volume
- `D` — **Delete**: Click to delete
- `P` — **Paint**: Draw MIDI notes (MIDI editor only)
- `Z` — **Zoom**: Click to zoom to bounds, drag to zoom to area

---

## Clip Types

The Studio supports three types of clips, each with different capabilities:

### Audio Clips

Audio clips contain a single audio file or sample.

**Characteristics:**
- Displays waveform visualization
- Can be trimmed, stretched, and repositioned
- Supports playback speed adjustment
- Can be transformed using AI models
- Shows source sample name and duration

**Visual Indicators:**
- Waveform display
- Trim handles on edges
- Volume/gain indicator
- Mute state (dimmed when muted)

**Context Menu Options:**
- Transform (AI audio transformations)
- Replace Source (swap the audio file)
- Download (export as audio file)
- Duplicate, Split, Delete

### MIDI Clips

MIDI clips contain musical note data that can be edited in the piano roll.

**Characteristics:**
- Contains note events (pitch, timing, velocity, duration)
- Editable in the MIDI Editor (double-click to open)
- Notes visualized as colored blocks
- Velocity shown as note opacity
- Can be converted to audio via "Burn to Audio"

**Visual Indicators:**
- Piano roll note blocks
- Pitch range indicator
- Note density visualization

**Context Menu Options:**
- Open Editor (or double-click)
- Duplicate, Split, Delete
- Quantize notes to grid

**Editing MIDI Clips:**
1. Double-click the clip or press `Enter` with it selected
2. Use Paint mode (`P`) to add notes
3. Use Select mode (`S`) to move/edit notes
4. Use Volume mode (`V`) to adjust velocity

### Group Clips

Group clips are containers that hold multiple tracks with clips inside them.

**Characteristics:**
- Contains nested tracks and clips
- Acts as a single unit on the parent timeline
- Can contain any combination of audio, MIDI, and other group clips
- Useful for organizing complex arrangements
- Can be ungrouped to extract contents

**Visual Indicators:**
- Multiple track preview
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

The Studio has 8 mouse modes that change how your cursor interacts with clips. Switch modes using the dropdown in the header or press the corresponding key.

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
- **Alt + Drag** — Bypass snap-to-grid for precise positioning

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

### Paint Mode (`P`) - MIDI Editor Only

Draw new MIDI notes.

**Capabilities:**
- **Click** — Create note at cursor position
- **Click + Drag** — Draw note with custom duration
- **Y position** — Determines note pitch
- **Snap-to-grid** — Applied automatically

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

### Playback

- `Space` — Play/Pause
- `Ctrl+Space` / `Cmd+Space` — Play from start

### File Operations

- `Ctrl+S` / `Cmd+S` — Save project
- `Ctrl+Z` / `Cmd+Z` — Undo
- `Ctrl+Y` / `Ctrl+Shift+Z` / `Cmd+Shift+Z` — Redo

### Selection

- `Ctrl+A` / `Cmd+A` — Select all clips
- `Ctrl+Shift+A` / `Cmd+Shift+A` — Select all in selected tracks
- `Ctrl+I` / `Cmd+I` — Invert selection
- `Escape` — Clear selection
- `Tab` — Select next clip/note
- `Shift+Tab` — Select previous clip/note

### Clip Operations

- `Delete` or `Backspace` — Delete selected
- `Ctrl+D` / `Cmd+D` — Duplicate
- `Ctrl+C` / `Cmd+C` — Copy
- `Ctrl+V` / `Cmd+V` — Paste
- `Ctrl+G` / `Cmd+G` — Group clips
- `Ctrl+Shift+G` / `Cmd+Shift+G` — Ungroup clips
- `Ctrl+B` / `Cmd+B` — Burn to audio
- `Ctrl+L` / `Cmd+L` — Auto-extend to next clip
- `Q` — Quantize to grid
- `Ctrl+Q` / `Cmd+Q` — Quantize with end

### Zoom Controls

- `Ctrl++` / `Cmd++` — Zoom in
- `Ctrl+-` / `Cmd+-` — Zoom out
- `Ctrl+0` / `Cmd+0` — Zoom to all
- `Z` — Zoom mode (click clips to zoom to bounds)
- `G` — Goto/zoom to selection (or all if nothing selected)
- `Ctrl+Scroll` / `Cmd+Scroll` — Zoom at cursor
- `Alt+Scroll` — Change grid resolution

### Movement

- `Left Arrow` — Move left by grid
- `Right Arrow` — Move right by grid
- `Ctrl+Left` / `Cmd+Left` — Move left quickly (10x)
- `Ctrl+Right` / `Cmd+Right` — Move right quickly (10x)
- `Up Arrow` / `Down Arrow` — Move to next track

### Track Operations

- `Shift+Delete` — Delete selected tracks
- `Shift+D` — Duplicate selected tracks
- `Shift++` (Shift + Plus) — Insert new track
- `Shift+Up Arrow` — Move tracks up
- `Shift+Down Arrow` — Move tracks down

### Audio Controls

- `M` (with selection) — Mute/unmute clips
- `M` (without selection) — Toggle metronome
- `Shift+M` — Mute/unmute tracks
- `S` (with exactly 1 clip selected) — Solo clip

### Editor Navigation

- `Enter` (with MIDI or Group clip selected) — Open clip editor
- `Double-click` on clip — Open clip editor

### MIDI-Specific Shortcuts

- `Up Arrow` — Pitch up 1 semitone
- `Down Arrow` — Pitch down 1 semitone
- `Ctrl+Up` / `Cmd+Up` — Pitch up 1 octave
- `Ctrl+Down` / `Cmd+Down` — Pitch down 1 octave

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

- **Scroll** — Pan timeline horizontally
- **Ctrl/Cmd + Scroll** — Zoom at cursor position
- **Alt + Scroll** — Change grid resolution
- **Scroll on grid pill** — Change grid resolution

---

## Context Menus

Right-click on clips or tracks to access context menus with additional options.

### Audio Clip Context Menu

Right-click on an audio clip to see these options:

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

- **Burn to Track** — Renders the clip to a new audio file, replacing it on the track. Useful for committing effects or consolidating.
- **Download** — Exports the clip as an audio file.

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

### MIDI Clip Context Menu

Right-click on a MIDI clip to see these options:

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

- **Burn Track** — Converts all clips to a single rendered audio clip. Original clips are preserved in a muted group.
- **Download Audio** — Export track as WAV file (Pro feature)
- **Share as Sample** — Publish track to TwoShot as a sample (copies link to clipboard)

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

**Project Options:**
- **Rename Session** — Change the project name
- **Make a Copy** — Duplicate the entire project
- **Open Session** — Browse recent projects
- **Delete Session** — Permanently remove the project
- **Close Session** — Exit without deleting

---

## Timeline Controls

### Header Controls

The timeline header contains these controls (left to right):

1. **Play/Pause Button** — Start or stop playback
2. **Project Title** — Click to rename, dropdown for project options
3. **Undo/Redo** — History navigation
4. **Mouse Mode Dropdown** — Switch between modes
5. **Tempo Control** — Adjust project BPM
6. **Metronome Toggle** — Enable/disable click track
7. **Grid Controls** — Magnet (snap) + grid size dropdown
8. **Zoom Controls** — Zoom in/out/fit buttons

### Playhead

- **Green vertical line** shows current playback position
- **Click in ruler** to move playhead
- **Loop region** (if set) shows as highlighted area

### Solo Mode

When you solo a clip (`S` with one clip selected):
- "SOLO" badge appears on play button
- Only the soloed track plays
- Click "SOLO" badge to disable

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

---

## Grid and Zoom

### Snap to Grid (Magnet Mode)

The magnet icon in the header controls snap-to-grid behavior.

- **Red magnet** — Snap enabled (clips align to grid lines)
- **Gray magnet** — Snap disabled (free positioning)
- **Hold Alt** — Temporarily override snap while dragging

When snap is enabled:
- Clip movements snap to grid lines
- Clip edges snap when trimming
- MIDI notes snap when adding or moving

### Grid Lines

Grid lines appear on the timeline to help with alignment:
- **Major lines** — Show bar boundaries
- **Minor lines** — Show beat subdivisions based on grid size
- **Grid size** affects both snap behavior and visual lines

### Grid Sizes

Available grid presets (click the grid pill to select):
- 1/4 beat (16th notes)
- 1/2 beat (8th notes)
- 1 beat (quarter notes)
- 2 beats (half notes)
- 1 bar (4 beats)
- 2 bars
- 4 bars
- 8 bars

### Changing Grid

1. **Click grid pill** — Opens preset dropdown
2. **Scroll on grid pill** — Cycle through sizes
3. **Alt + Scroll anywhere** — Change grid size

### Zoom Controls

- **Zoom buttons** — Zoom in/out from center
- `Ctrl/Cmd + Scroll` — Zoom at cursor position
- `Z` key — Enter Zoom mode (click clips to zoom to bounds, drag to zoom to area)
- `G` key — Goto/zoom to selection (or fit all if nothing selected)
- `Ctrl+0` / `Cmd+0` — Zoom to fit all content
- **Ctrl + Right-drag** — Box zoom to region

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

Each track has:
- **Name** — Click to edit
- **Mute button** — Silence track (audio still processes)
- **Solo button** — Play only this track
- **Volume slider** — Track level (0-100%)
- **Pan control** — Left/right stereo positioning

### Track Looping

Enable looping to repeat a track's content:

1. Right-click track > enable looping
2. Set loop interval (in beats)
3. **Ghost clips** appear showing where content will repeat
4. **Burn Ghost Clips** to convert ghosts to real clips

### Deleting Tracks

- **Shift + Delete** — Delete selected tracks
- **Right-click** > Delete Track
- Clips on deleted tracks are also removed

---

## Clip Operations

### Creating Clips

- **Drag audio** from browser onto timeline
- **Import audio** via URL or file upload
- **Generate audio** using AI models
- **Record** using microphone input
- **Paint MIDI** in the MIDI editor

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

### Burn to Audio

- Select clips and press `Ctrl+B` / `Cmd+B`
- Renders selected clips to a single audio file
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

Converts all clips in a track to a single rendered audio clip:

1. Right-click track > Render > Burn Track
2. Original clips are preserved in a muted group
3. Burned audio appears on top

### Download Audio

Export a track as a WAV file (Pro feature):

1. Right-click track > Render > Download Audio
2. Track is rendered and downloaded
3. Includes all clips, effects, and volume settings

### Share as Sample

Publish a track to TwoShot's sample library:

1. Right-click track > Render > Share as Sample
2. Track is rendered and uploaded
3. Link is copied to clipboard

### Export to DAW

Export your project for use in other DAWs:

**Supported formats:**
- FL Studio project (.flp)
- MIDI file (.mid)
- Audio stems (WAV files)

**How to export:**
1. Access export options from project menu
2. Select your target format
3. Download the exported file(s)

---

## AI Transform Features

TwoShot integrates AI models for audio transformation.

### Transforming Clips

1. Right-click an audio clip > Transform
2. Select a transformation model:
   - **Stem Separation** — Extract vocals, drums, bass, etc.
   - **Style Transfer** — Apply different musical styles
   - **Audio Enhancement** — Improve quality, remove noise
   - **And more...**
3. Wait for processing
4. Result replaces or adds to your clip

### Transforming Tracks

1. Right-click track > Transform
2. Track will be burned first (if needed)
3. Select transformation
4. Result appears as new clip

### Available Transformations

Common AI transformations include:
- **Stem Separation** — Split into individual instruments
- **Vocal Isolation** — Extract or remove vocals
- **Style Transfer** — Change genre or style
- **Upscaling** — Improve audio quality
- **Tempo/Pitch** — Change speed or key
- **Extend** — Generate continuation of audio

---

## Tips and Workflows

### Speed Tips

1. **Use single-key mode switches** — `S`, `T`, `X`, `C`, `V`, `D`, `P`, `Z` are faster than the dropdown
2. **Ctrl+D for quick duplication** — Faster than copy/paste for repeating clips
3. **Z key for zoom mode** — Click clips to zoom in, right-click to zoom out
4. **G key for quick navigation** — Quickly jump to your selection
5. **Tab/Shift+Tab** — Navigate between clips without clicking
6. **Alt to bypass snap** — Fine-tune positioning while snap is enabled

### Common Workflows

**Arranging a loop:**
1. Import your loop audio
2. Use `Ctrl+D` to duplicate
3. Position copies using arrow keys
4. Enable snap-to-grid for tight alignment

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
4. Use Render > Download Audio for each track

### Modifier Key Summary

- **Ctrl/Cmd** — Multi-select, zoom, quick operations
- **Shift** — Range select, track operations, extend behavior
- **Alt** — Bypass snap-to-grid, grid resolution scroll
- **Right-click** — Context menu, special mode actions

---

## Cursor Indicators

The cursor changes to show what action will occur:

- **Default arrow** — Select mode
- **col-resize (↔)** — Split mode or edge resize
- **ns-resize (↕)** — Volume adjustment
- **ew-resize (↔)** — Stretch mode
- **copy** — Clone mode
- **not-allowed** — Delete mode
- **crosshair** — Selection box
- **cell** — Toggle selection box
- **zoom-in** — Zoom selection box

---

## Need Help?

If you can't find what you're looking for or need assistance:

1. **Use the "Ask AI" button** in the top-right corner to get personalized help
2. **The AI assistant** can help with specific tasks, answer questions about features, and guide you through workflows

---

*Last updated: January 2025*
