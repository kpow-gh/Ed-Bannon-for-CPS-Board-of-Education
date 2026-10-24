# Hero video: install steps (Option B)

The headshot in the homepage hero is replaced by the 30-second campaign ad:
the wide version on computers and tablets, the tall version on phones
(700px wide or less).
The ad itself is unchanged; it has only been compressed for the web.

## What happens on the page

- The frame first shows the **"Vote Ed Bannon" card** (a still image), while the video loads.
- The video then autoplays **silently, starting on the card** (about 5 seconds),
  and loops back to the beginning of the full ad.
- **Sound on** restarts the ad from the beginning with audio.
- **❚❚** pauses and resumes it.
- Visitors whose device is set to reduce motion, and phones in Low Power Mode,
  see the card still with a ▶ button instead of autoplay.

## Files

| File | What it is |
|---|---|
| `ed-bannon-ad-wide.mp4` | Wide ad for computers and tablets: 1280×720 with audio, 3.4 MB |
| `ed-bannon-ad-poster-wide.jpg` | Wide "Vote Ed Bannon" card still |
| `ed-bannon-ad-tall.mp4` | Tall ad for phones: 720×1280 with audio, 3.5 MB |
| `ed-bannon-ad-poster-tall.jpg` | Tall "Vote Ed Bannon" card still |
| `ed-bannon-ad-captions.vtt` | Captions, converted from the uploaded caption file |
| `hero-video-block.html` | Code for a Custom HTML block |
| `hero-video.css` | CSS to add at the end of Additional CSS |

## Steps

1. **Upload the media.** In WordPress, go to **Media → Add New** and upload
   all five media files: `ed-bannon-ad-wide.mp4`, `ed-bannon-ad-poster-wide.jpg`,
   `ed-bannon-ad-tall.mp4`, `ed-bannon-ad-poster-tall.jpg` and
   `ed-bannon-ad-captions.vtt`. Open each one and copy its **File URL**.

2. **Add the video block.**
   1. Go to **Pages → Home - New → Edit**.
   2. Click Ed's headshot in the hero. To confirm it's the right block, open
      **List View** (the ≡ icon at the top left): the selected Image should be
      inside the group named `hero-image-wrap`.
   3. With the headshot selected, open the block's **⋮** menu and choose
      **Add before**. Add a **Custom HTML** block.
   4. Paste the contents of `hero-video-block.html` into the Custom HTML block.
   5. Replace the five URLs (each ends in the matching file name) with the
      File URLs you copied in step 1.
   6. Select the headshot image again, then choose **⋮ → Delete**.
      Leave the skyline, the "Education starts with Ed!" note and the stars alone.
      They move automatically: the note goes under the video with the stars
      beneath it, and the skyline moves into the open space in the
      middle of the text, just above the buttons.
   7. Put the note on one line: click into the "Education starts with Ed!"
      text, select all of it (Ctrl+A, or Cmd+A on a Mac, while the cursor is
      in the note), and type `Education starts with Ed!` so there are no line
      breaks.

3. **Add the CSS.** Go to **Appearance → Editor → Styles**, open the **⋮** menu,
   then **Additional CSS**. Scroll to the very bottom and paste in all of
   `hero-video.css`.

4. **Save** and check the homepage on a computer and on a phone. Then tap
   **Sound on** to confirm the audio plays.

**To undo:** delete the Custom HTML block, re-add the headshot image
(`Header-Image-Ed-Bannon.png`, CSS class `hero-headshot-composite`), and remove
the HERO-VIDEO-2026 CSS section.

**If the video never starts:** WordPress may have stripped the `<script>` part
of the block. This happens when the account isn't a full Administrator.

## Captions

Captions are already switched on in the block code. Upload
`ed-bannon-ad-captions.vtt` under **Media → Add New** along with the video, and put its
File URL in the `<track …>` line.

They appear in a navy strip under the video, so they never cover the ad's own
on-screen text. To fix a typo later, edit the `.vtt` file in any text editor and
upload it again. If the captions file can't be found, the strip hides itself.

**If WordPress won't accept the .vtt upload,** don't rename it to another file
type: some browsers then won't show the captions. Ask for help instead.
