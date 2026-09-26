# Reading the clot - v26 handoff (26 Sep 2026, thread 5; includes the v10 to v25 handoffs)

## 0. Read first

v26 is built and delivered (26 Sep): the drawn film on the cup-and-pin card, "Watch it drawn (47 s)" (C99), on top of v25 (25 Sep: the clock fault fixed, C92; the launch video for the Riddell post, C93, stress-tested and remade as v3, C94). The educational video "How a TEG draws its trace": the garnet version (C95, judged "Poor", kept at his word), the Leonardo notebook page (C96, judged "Impressive"), v3 opening on the finished page (C97) and v4 with the small words raised (C98), how-a-teg-draws-its-trace-notebook-v4.mp4, the one to post. v13 is LIVE at https://gundoc9.github.io/reading-the-clot/ unless he has uploaded since; v14 to v26 (C79 to C99) are cumulative, and v26's index.html with the film file how-a-teg-draws-its-trace-app-v4.mp4 beside it are the two to upload, BEFORE the post goes out, so the link opens the app the video shows. Nothing is queued in the app.
Every gate is green on the delivered file: gate_engine 768/0, gate_build 1641/0, gate_ui 837/0 (the film at 320, 390, 820 and 1366 px), sweep 0 hard faults at 320, 360, 375, 390, 430, 768, 820, 1024 and 1366 px, overflow 0 at 320, 360 and 390 px, monkey 500 actions clean (the film among them). index.html sha256 acd4312f21d635117e3746b0d3449bb3ae60ea9922a18e7915dd95af280f7269; how-a-teg-draws-its-trace-app-v4.mp4 sha256 c81dfb6ee8d4fc756ed824f5cafe1c0684b517ebaef9b07376a9143f3d93c325.

ATTACH AT NEXT THREAD START, seven files and nothing else:
1. clot-v24-source.zip (previously delivered - re-attach). No v25 or v26 source zip was made (his 24 Sep rule: no zips); v26 is the v24 source plus apply_v25.py then apply_v26.py, both printed in section R below: run them in that order inside the unpacked src/ folder, put the film (item 7) in src/film/, and the rebuild matches the delivered index.html byte for byte (checked 26 Sep: apply_v26.py run on a copy of the v25 source reproduced every v26 source file exactly)
2. HANDOFF-clot-v2.md (standing rules, calls C1-C22, engine, gates; previously uploaded - re-attach)
3. HANDOFF-clot-v9.md (calls C23-C53, build commands; previously uploaded - re-attach)
4. HANDOFF-clot-v9-papers.md (the ten papers' numbers and the sources register; previously uploaded - re-attach)
5. HANDOFF-clot-v26.md (this file; the v10 to v25 handoffs are folded in)
6. HANDOFF-clot-papers-2.md (the papers read after v15, with their numbers; previously delivered - re-attach)
7. how-a-teg-draws-its-trace-app-v4.mp4 (the film the cup-and-pin card opens, 5.4 MB; previously delivered - re-attach), into src/film/
No PDFs. Lang 2005 and Ziegler 2019 are still unread; do not ask for them.

Delivered 26 Sep, in /mnt/user-data/outputs: index.html (v26 under its final name, 406 KB) and how-a-teg-draws-its-trace-app-v4.mp4 (the film, under its final name; both go to the repository), reading-the-clot-v26.html (the same page), the clot-repo folder (the repository's seven files), reading-the-clot-obstetric-v3.mp4 (the Riddell post's video, sha256 bcb66c4cc9e1937e4f0ef80e49ca2b522c152c48e2b604344f5e41ee94660bb1), how-a-teg-draws-its-trace-v1.mp4 (C95, 41 s, kept), how-a-teg-draws-its-trace-notebook-v2.mp4 (C96) and -v3.mp4 (C97), both superseded, how-a-teg-draws-its-trace-notebook-v4.mp4 (C98, 47.0 s, the one to post, sha256 25d2589909c8e80c06fac8a3b093d392c0757b0913f612209b0216edc22a460a), this file. The review sheets from v24 (plot, assay row) and v23 (read order) are unchanged and still valid (previously delivered - re-attach if wanted). Every v9 to v25 app file is superseded.

## C92-C94, the 25 Sep calls (his "Please create a MP4 video for the post that starts with the cover page of the app and then a live run of the obstetric card. What do you think", then "Stress test the video please")

C92. THE CLOCK FAULT (v25), found while planning the video. Since v20 the clock stopped at 300, 600 and 1200 s of
     run time, but A5, A10 and A20 are read 5, 10 and 20 min after the clotting time, so on every card the "5 min"
     stop blanked the A5 its own line said was in (the obstetric card printed no A5 at all at "5 min"; likewise A10
     at "10 min" and A20 at "20 min"). Now each stop is the taught trace's CT plus 5, 10 or 20 min (the teach series,
     else the first), the buttons read "The trace at A5 · A10 · A20 · full", and the lines open "A5 is read five
     minutes after the clotting time..." with the same sources as before. The A20 stop greys when CT + 20 min passes
     the window. State: ctl.clockKey (the stop chosen) replaces the scrub comparison. Class gate added in gate_ui:
     at each stop named for a reading, that reading prints wherever the state lists it (A5 at the A5 stop, A10 at
     the A10 stop), and the stop is at the taught CT + 5 min exactly. gate_ui's v20 rule "MCF is never printed at
     the 5-minute stop" was restated as the rule it stood for: the maximum prints exactly when the drawn curve is
     within 2% of it at the stop (a low, fast clot such as the low-platelets card's EXTEM at A10 27 mm plateaus
     inside five minutes after CT and correctly prints it). gate_build 22 checks the stops (5, 10, 20, full), the
     labels and that each line opens on its reading. README line updated; UPLOAD-STEPS commit text v25.
C93. THE LAUNCH VIDEO: reading-the-clot-obstetric-v2.mp4, 15.6 s, 468 frames, 1080x1350, H.264 High,
     yuv420p, 30 fps, faststart, tagged BT.709 primaries and matrix, sRGB transfer, limited range. v1 (same frames)
     was his "It's not the same colour as the app": encoded untagged with ffmpeg's default BT.601 matrix, which a
     phone reads as BT.709 for HD video, so the garnet showed as (129, 40, 61) against the app's (122, 31, 61),
     lighter and redder; the v1 QC decoded with ffmpeg's own BT.601 default and so matched itself. v2 converts with
     the BT.709 matrix and tags it, and the QC now decodes the way a phone does: garnet (121, 30, 60), cream within
     2 levels, whole-frame mean difference under 2 of 255. Made the way the approved checker walkthrough was (his conditions there:
     punchy, about 15 s, a band on the cover from the first frame) and NOT as a screen recording (the cannulation
     screen recording was retired as "looks amateur"): every frame is a screenshot of the delivered index.html in
     Chromium at 540x675 CSS px x2 (his locked canvas), under Playwright's fake clock PAUSED and stepped 1/30 s per
     frame, so the app's own 4.5 s opening draw runs at its own speed (an unpaused fake clock lets real time flow
     during each screenshot and the draw ran about nine times fast: caught on the first contact sheet). Run:
     0-1.6 s the cover (landing at the top, first frame fully rendered) with a garnet band over the lower third,
     "Which number falls first / in a postpartum bleed?" (Lora 500, cream), attached to the page; 1.6-2.6 s a flick
     down the landing (sine easing, a vertical smear the length the page moves in half a frame; five averaged
     sub-frames were tried first and strobed into copies); a tap on "The obstetric threshold" (a grey disc with a
     cream rim, 0.3 s, ending as the card opens); the card at the top draws its 19 mm state over 4.5 s (the same as
     the labour median, so one curve); a small scroll so the title, figure, table and chips fill the frame; tap
     12 mm (8.42 s), tap 7 mm (10.52 s), each held about 2.1 s; a scroll to the table, chips, clock row, the 7 mm
     note and What to give (13.5 s), held to 15.6 s. The credentials footer on every frame (Poppins 25 px, centred,
     cream strip with a rule). QC: spec probe, frame count 468 = 15.6 x 30, moov before mdat, first encoded frame
     matches the rendered cover, the cover static for its first 1.6 s, frame-to-frame change only in the designed
     scroll, a 12-frame contact sheet from the encoded file viewed at delivered resolution. The recorder is
     printed in section V; it needs the delivered index.html beside it.
C94. THE VIDEO STRESS TEST (his "Stress test the video please"): reading-the-clot-obstetric-v3.mp4 replaces v2,
     2.1 MB, same spec and colour pipeline. Every hold was measured from the page's own layout (census.py, section V:
     each text line's box and each chip, clock button, table row and the figure window against the frame's top edge
     and the footer's top edge) and read at phone size (a 390 pt feed: CSS px x 390 / page width; floor 8.4). v2
     failed five ways: the cover band's top edge cut the first line of the scope paragraph; the list hold cut the
     Heparin row's text at the top; the legend ("labour median", "FIBTEM") and "v25" read 7.9 pt and "What to give"
     8.3; the end hold cut a line of text at the footer and left a sliver of the figure window at the top. v3 renders
     the page 496 CSS px wide (x 1080/496 = 2.1774; the frame is still 1080x1350; the app's 404 px column is the same
     at any page width from 440 to 699, so only the zoom changed from the 540 canvas: the app is about 9% larger) and
     plan.py sets the band and every hold's scroll from the layout: band top 398.2 CSS px (midway between v25 and the
     scope paragraph), list 1425.9 (the obstetric row 58% down; row hairlines kept off the edges too), draw 0 (title,
     figure and table; 6 px clear), chips 112.3 (figure, table, key and chips, 5 px clear of the title above and the
     clock row below in all three chip states; the title is off the top for the chips), end 455.4 in the 7 mm state
     (the table down to the first line of the Liverpool paragraph; 1.8 px below the figure window, 0.8 px between two
     line boxes, the ink about 2 px clear). The width is the one free choice: the chips hold needs 580 to 601 CSS px
     of view, and the only clean end in that range is between Liverpool lines 1 and 2 (ending on the when paragraph
     needs 555 to 575); 496 gives the widest clearances (472 to 508 tried). Smallest text now 8.65 pt (legend, v25).
     The card's two scrolls now carry the flick's smear (half a frame's travel; unsmeared they jumped up to 87 frame
     px a frame). Unchanged: the timeline, taps, band words, footer, BT.709 encode. QC: census 0 faults (the layout,
     and the rendered pixels along each held edge); PSNR against the frames min 35.7 dB, mean 40.1; decoded as a
     phone, garnet (122, 31, 61) and cream within 1 level; the source frames move only in the designed windows; after
     encoding the held stretches change in at most a few hundred scattered pixels (the 11.27 s keyframe: 7 px beyond
     16 levels); seeking matches play-through at 8 frames; two decodes identical; encoded contact sheet viewed. Not
     testable here: LinkedIn's own player and re-encode. Left as is and told him: at 19 mm the FIBTEM curve is the
     labour median (A5 19, A10 22, MCF 25), so one curve shows through the draw; true to the data.

C95. THE TEG EXPLAINER VIDEO (26 Sep, his "Could you also create a short educational video that draws a normal TEG with all
     the times that starts with how TEG works with a blood sample? Let me know your process first before building", then
     "Yes / Cup and pin / App colours / Has to look visually stunning yet accurate", then "I'm not sure that much detail is
     needed... especially for the cup and pin part / The look needs to be visually stunning", then "Let's see this"):
     how-a-teg-draws-its-trace-v1.mp4, 41.0 s, 1230 frames, 1080x1350, same encode and footer as C93. Drawn frame by frame
     in Python (teg2.py: PIL shapes on a 3x canvas averaged down, text at 1x in Lora and Poppins; section W). Look, after
     the first labelled cutaway was judged not stunning: the app's garnet as the whole ground, the trace in cream like the
     app's icon, the cup seen from above as one dial-like shape (cream rim with ticks that ride the cup's turn, wine blood
     ring, cream pin with a garnet notch and a fan showing its sweep, cream fibrin threads that fill the ring as the clot
     firms), "movement exaggerated" under it. Script: the cup turns around a pin; liquid blood leaves the pin still, flat
     trace; fibrin links cup to pin; the pin swings and the trace widens; R (2 mm), K (2 to 20 mm), alpha (slope at 2 mm),
     MA (widest, platelets and fibrinogen), LY30 (share lost 30 min after MA); the trace turns solid (the icon) beside a
     table of this trace against the kaolin ranges and two QR codes (Srivastava 2013, Wells 2022). The example is the
     app's engine law (model.py, k = 1) at R 6, K 2.5, MA 64 (the midpoints of Srivastava 2013 Table 2), no lysis; every
     printed number recomputed from it (alpha 62.6 by the app's K_ALPHA 13.6 convention, drawn angle-true: the upper edge
     is half the width and sy = 2 x 13.6 x sx). The pin swings in proportion to the width (width/100 of the cup's turn).
     Facts: Srivastava 2013 (360 ul, 37 C, pin on torsion wire, 4 deg 45 min each way, each turn 10 s, straight line
     before clotting, R K alpha MA LY30 definitions, kaolin ranges R 4-8, K 1-4, alpha 47-74, MA 55-73; no LY30 range),
     Curry 2018 BSH (fibrin strands resist the movement), Wells 2022 (LY30 over 7.5%). Stress test (qc_teg.py): no string
     on another, on an edge, on the trace outline or under the pen on any second frame; each line held at 3.3 words a
     second (it first ran at 4.1 to 4.6, so the video grew from 34.5 to 41 s); the pen crossed "MA 64 mm" (label moved
     left of the arrow); smallest text 8.67 pt on a phone; ground decodes as (122, 31, 61) on a phone; both QR codes read
     from the encoded last frame; the largest frame-to-frame change is the planned 1-s turn to the closing card.

C96. THE NOTEBOOK VERSION (26 Sep). His verdict on C95: "Poor", then "No one will watch after the first 5 seconds / Use
     of fonts and appearance of subheadings is from the last century / The look is ok but nothing great / Does it teach?
     No one's going to stick around to find that out"; then "Keep the current version for now - save it. Try another
     fresh path. Parchment paper palette. Same content. But make it look like how Da Vinci drew his anatomy drawings"
     (the same message arrived twice). C95's file and source are kept unchanged (section W). Delivered
     how-a-teg-draws-its-trace-notebook-v2.mp4, 42.5 s, 1275 frames, same encode and footer text. A first build
     (notebook-v1, 41.8 s) was reviewed at full size before sending and never sent: its close-up was two-thirds empty
     sheet, the pin read as glass (the far rim and the blood's surface were drawn through it), a seam ran down the cup
     and the table's shadow was hatched over the cup; its source is in the build folder (notebook-v1-source).
     The page (leo.py, section X): an old sheet taller than the frame (made once at 3x: mottling, edges browned
     unevenly, fibres, rust spots; tide-line water stains were tried and read as dirt, removed); iron-gall ink and red
     chalk with left-handed hatching running down to the right, PEN AND WASH (a thin brown wash in the shadows of both
     studies and a red one where the blood is, going on at 1.7 to 3.2 s once the pen has set the forms down); the cup
     from the side as a solid (contour hatching, cast shadow kept off the cup, reflected light at the shadow edge) with
     the pin hanging on its wire and standing in front of the far rim; "the same cup, from above" as a dial (red ring,
     fibrin threads in ink, notch and sweep, "the turn, drawn larger than life"); "blood" written outside the ring on a
     leader. Frame 0 (the thumbnail) is the whole page in red chalk, inked over in the first 3 s. Notes written word by
     word in Crimson Pro Italic beside the drawings, word gaps 1.2 x a space (italic f's reach into the gap), the closing
     note broken after "middle of". The camera: a log-space zoom about one fixed point (the move reads as leaning in),
     5x on the start of the trace for R, K and alpha, starting only once the last page note has gone (15.4 s, 1.3 s
     long, 0.7 s added to the whole); in the close-up the page labels step aside, the words are 42 px, R and K sit on a
     ruler just under the trace (not the axis) and the note is at the top left; back out for MA and LY30; down to the
     foot (camera y 1390) for the table (40/38 px) and two QR codes at 4 px a module. Same script and numbers as C95.
     Fonts: Crimson Pro only (no Greek alpha, so "alpha"); period faces could not be fetched (the font repository and
     the npm package were both refused by the network). Stress test (qc_leo.py, final encode): no string on another,
     on an edge, on the trace or under the pen in 383 frames at rest (the overlap test now measures ink, not boxes: "of
     fibrin" had boxes meeting through italic f overhangs with 10 px of clear sheet between the letters); notes at 2.8
     to 3.3 words a second; smallest text 8.67 pt on a phone, close-up words 15.2 pt; decoded as a phone the frames hold
     (PSNR 39 to 47 dB, same mean colour); both QR codes read from the encoded last frame; the largest frame-to-frame
     change is the planned pan down the page.

C97. NOTEBOOK v3 (26 Sep). His verdict on v2: "Impressive", then "Anything you would improve? Any value add in leaving
     the labels on the drawing in the final scene?". Claude proposed three changes (all five names on the final trace;
     the last page held about 3 s longer; the side view moving); he said "Yes to all 3", adding "When I post this video
     on LinkedIn, I want it to open at the correct frame... I don't want a blank looking page as the first thing people
     see". Delivered how-a-teg-draws-its-trace-notebook-v3.mp4, 47.0 s, 1410 frames, same encode and footer. Changes
     from v2: (1) the video opens on the finished page (cover(): both studies inked and washed, the whole trace with its
     five names, no notes), held 1.0 s and dissolving by 1.5 s into the red chalk sketch, then the story as before
     (story time = video time - 1.5). LinkedIn's default thumbnail is a video's first frame, with a custom upload
     possible but no frame picker (Emily Binder on X, 2026: https://x.com/emilybinder/status/2032183753141862814), so
     no upload step is needed. The chalk underdrawing is stronger (0.42 to 0.6) so the start never reads as a blank
     page. (2) At the close the numbers leave the drawing ("MA 64 mm", "LY30 0%" fade at +0.1 to +0.6 s) and the five
     names come on where each is read (+0.8 to +1.4 s): R and K on a ruler under the start of the rise (YM + 90), alpha
     on the tangent at 2 mm with its arc, the word inside the angle with the hatching cleared softly round it, MA and
     LY30 above the trace; the table keeps the numbers. (3) The last page holds to 45.5 s of story (was 42.5).
     (4) The side study moves: a graduated collar round the cup's wall (fixed edges, 36 ticks every 10 degrees, long
     every 30) rides the turn; a curved double arrow under the cup; a notch on the pin's top face follows the turn once
     the clot grips; a twist mark on the wire comes on as the trace passes 2 mm. Side-view angles are negated (seen
     from the front, the same turn runs the other way round). Stress test (qc_leo.py, final encode): no string on
     another, on an edge, on the trace or under the pen in 414 frames at rest including the cover (the test now ignores
     the mask drawn to clear paper round "alpha"); notes at 1.8 to 3.3 words a second; decoded as a phone the frames
     hold (PSNR 39 to 47 dB, same mean colour); the first frame carries ten times the ink of the chalk start; both QR
     codes read from the encoded last frame; the largest frame-to-frame change is the planned pan down the page.

C98. NOTEBOOK v4 (26 Sep). He asked "Any room for improvement?" and "What is the value add in incorporating this video into
     the app itself?"; Claude named one improvement (the smallest words, about 9 pt on a phone, raised to about 11 pt) and
     the film in the app one tap away (value: the cup-and-pin card explains the mechanism in words, the film shows it;
     costs: 11.7 MB against 0.4 MB, so a lighter separate copy loaded only on a tap and one extra file to upload; the
     parchment look against the app's garnet and cream, kept apart by opening full screen; its second half repeats "The
     five numbers on the trace"). He said "Go for both". Delivered how-a-teg-draws-its-trace-notebook-v4.mp4, 47.0 s:
     axis numbers, the labels by both studies, "pin", "blood", the QR labels and the footer credit raised from 24-28 px
     to 30-31 px (the smallest now 30 px, 10.8 pt on a phone 390 pt wide); "the turn, drawn / larger than life" moved
     to a place found clear of the dial and its arrow at the new size (right-aligned at x 1054, baselines 486 and 520);
     "60" centred on its tick like the other numbers, "min" after it. qc_leo.py now measures the smallest word from
     the fonts actually drawn and checks every word against the drawing itself (ink under a word, from a render
     without words, 83 frames); stress test green: no layout fault in 414 frames at rest, notes 1.8 to 3.3 words a
     second, colour holds (PSNR 39 to 47 dB), both QR codes read, the largest change the planned pan.

C99. THE FILM IN THE APP (v26, 26 Sep). "Watch it drawn (47 s)", a button under the title of "The trace: cup, pin and
     resonance" (cards.py film=dict on that card only, FILM = how-a-teg-draws-its-trace-app-v4.mp4). The film is the v4
     frames encoded at CRF 23 (5.4 MB, H.264 High 4.0, yuv420p, faststart), a separate file beside index.html that
     loads only when the button is tapped (preload none, no src until then); it opens in a full-screen layer over the
     page (opaque, the title and a 44 px close button lined up with the picture above it, the picture 4:5 at the
     largest size the screen holds), plays inline with the phone's own controls (playsinline, so it works from the
     home-screen icon, where a plain link to the file would leave no way back), and closes by its button, by Escape
     or by a tap outside, stopping the download and handing focus back to the button. A browser that cannot play
     H.264 is told so in one line (the container's Chromium cannot, so its playback was checked with a test-only VP9
     copy; Safari on the phone, iPad and Mac plays H.264). build.py copies the film beside the page and into
     clot-repo and hashes it; gate_build checks the one card, the name, the size (8 MB cap), codec, faststart and the
     label against the file's duration; gate_ui checks nothing loads before the tap and the layer at 320, 390, 820
     and 1366 px; monkey taps the film and closes it. README and UPLOAD-STEPS name the seventh file. The scope line
     "Nothing leaves your device" stays true: the film is fetched from the same site, nothing is sent.

## 5. Open, for him

1. Upload v26's index.html and how-a-teg-draws-its-trace-app-v4.mp4 over the live site (Add file > Upload files, pick
   both, Commit changes; they carry C79 to C99), then one Post Inspector run, BEFORE the post goes out. The post: the Riddell 2026 caption is at v3 (25 Sep,
   no heading, the Anyway ending replaced; his "I don't know how you're using the voice sheet" stands, see
   writing-voice) and unapproved; the first comment (paper, declarations, app address, the postpartum read order)
   stands; the video is reading-the-clot-obstetric-v3.mp4 (v2's colour, stress-tested, C94), verdict pending.
2. His phone verdicts on the plot (with its assay row) and the read order; whether the read-order questions are
   too easy with the legend showing.
3. The OBS2 57 v 55 query (C81; check Collins 2017, S9, before changing either; the card says 55); the accent
   (garnet provisional); the four ILLUSTRATIVE traces, all labelled.

## R. Rebuilding v26 from clot-v24-source.zip (apply_v25.py then apply_v26.py inside the unpacked src/ folder, then python3 cards.py and the build)

```python
# apply_v25.py - run inside the unpacked clot-v24-source src/ folder: turns the v24 source into v25 (C92, the clock stops at A5, A10 and A20)
def patch(p, pairs):
    s = open(p, encoding='utf-8').read()
    for old, new in pairs:
        assert s.count(old) == 1, (p, s.count(old), old[:80]); s = s.replace(old, new)
    open(p, 'w', encoding='utf-8').write(s)
patch('template.html', [
("clock.appendChild(el('span', 'cl', 'The trace at'));\n        DATA.clock.forEach(function(ck){ var b = el('button', 'cbtn', ck.label); b.setAttribute('aria-pressed', 'false'); b.addEventListener('click', function(){ if (b.disabled) return; stopAuto(); ctl.scrub = ck.t == null ? null : ck.t; ctl.clockStop = ck.t == null ? null : ck.t; draw(); }); cbs.push(b); clock.appendChild(b); });",
 "clock.appendChild(el('span', 'cl', 'The trace at'));\n        var clockT = function(ck){ if (ck.m == null) return null; var st = states[si], ti = st.series.findIndex(function(s_){ return s_.teach; }); if (ti < 0) ti = 0; var sp = st.series[ti] && st.series[ti].p; return (sp && sp.CT != null ? sp.CT : 0) + ck.m * 60; };   // A5, A10 and A20 are read 5, 10 and 20 min after the clotting time of the trace being taught, so each stop is that trace's CT plus the minutes (v25; v20 stopped at 300, 600 and 1200 s of run time and blanked the reading its own line announced)\n        DATA.clock.forEach(function(ck, k){ var b = el('button', 'cbtn', ck.label); b.setAttribute('aria-pressed', 'false'); b.addEventListener('click', function(){ if (b.disabled) return; stopAuto(); var t = clockT(ck); ctl.scrub = t; ctl.clockStop = t; ctl.clockKey = t == null ? null : k; draw(); }); cbs.push(b); clock.appendChild(b); });"),
("        ctl.clockSync = function(){ var st = states[si], win = (st.ymax ? card.figure : card.figure).window; var diagram = !!st.diagram; clock.style.display = diagram ? 'none' : ''; cline.style.display = diagram ? 'none' : '';\n          var atStop = DATA.clock.some(function(ck){ return ck.t != null && ctl.scrub === ck.t; });\n          DATA.clock.forEach(function(ck, k){ var on = ck.t == null ? !atStop : ctl.scrub === ck.t; cbs[k].classList.toggle('on', on); cbs[k].setAttribute('aria-pressed', on ? 'true' : 'false'); cbs[k].disabled = ck.t != null && ck.t >= win; });\n          var cur = DATA.clock.filter(function(ck){ return ck.t != null && ctl.scrub === ck.t; })[0]; cline.textContent = cur ? cur.line : ''; };",
 "        ctl.clockSync = function(){ var st = states[si], win = card.figure.window; var diagram = !!st.diagram; clock.style.display = diagram ? 'none' : ''; cline.style.display = diagram ? 'none' : '';\n          var key = ctl.clockKey != null && ctl.clockStop != null ? ctl.clockKey : null;\n          DATA.clock.forEach(function(ck, k){ var on = ck.m == null ? key == null : key === k; cbs[k].classList.toggle('on', on); cbs[k].setAttribute('aria-pressed', on ? 'true' : 'false'); var t = clockT(ck); cbs[k].disabled = t != null && t >= win; });\n          cline.textContent = key != null ? DATA.clock[key].line : ''; };"),
("b.addEventListener('click', function(){ stopAuto(); si = i; ctl.clockStop = null; if (ctl.scrub",
 "b.addEventListener('click', function(){ stopAuto(); si = i; ctl.clockStop = null; ctl.clockKey = null; if (ctl.scrub"),
("ctl = { param: knob.param || null, value: null, scrub: null, sync: null, clockStop: null }; card._ctl = ctl;",
 "ctl = { param: knob.param || null, value: null, scrub: null, sync: null, clockStop: null, clockKey: null }; card._ctl = ctl;"),
])
patch('cards.py', [
('''CLOCK = [
  {"t": 300, "label": "5 min", "line": "At five minutes the clotting time and A5 are in. The FIBTEM A5 carries the obstetric decision (Curry 2018 BSH), and the A5 predicts the maximum (Wells 2022)."},
  {"t": 600, "label": "10 min", "line": "At ten minutes A10 is in, the trigger the cardiac and paediatric algorithms use (Karkouti 2016, Nakayama 2015, Faraoni 2015). A bleed of 100 ml a minute has lost nearly a litre in the wait (Milewski 2025)."},
  {"t": 1200, "label": "20 min", "line": "At twenty minutes A20 is in and the maximum is close; lysis needs the 30 minute index (Larsen 2011)."},
  {"t": None, "label": "full", "line": ""},
]''',
'''CLOCK = [   # m: minutes after the clotting time of the trace being taught (v25)
  {"m": 5, "label": "A5", "line": "A5 is read five minutes after the clotting time. The FIBTEM A5 carries the obstetric decision (Curry 2018 BSH), and the A5 predicts the maximum (Wells 2022)."},
  {"m": 10, "label": "A10", "line": "A10 is read ten minutes after the clotting time and is the trigger the cardiac and paediatric algorithms use (Karkouti 2016, Nakayama 2015, Faraoni 2015). A bleed of 100 ml a minute has lost nearly a litre in the wait (Milewski 2025)."},
  {"m": 20, "label": "A20", "line": "A20 is read twenty minutes after the clotting time, when the maximum is close; lysis needs the 30 minute index (Larsen 2011)."},
  {"m": None, "label": "full", "line": ""},
]'''),
])
patch('gate_build.py', [
("ok([ck['t'] for ck in DATA.get('clock', [])] == [300, 600, 1200, None], 'the clock does not stop at 5, 10, 20 minutes and full')",
 "ok([ck.get('m') for ck in DATA.get('clock', [])] == [5, 10, 20, None] and [ck['label'] for ck in DATA.get('clock', [])] == ['A5', 'A10', 'A20', 'full'], 'the clock does not stop at A5, A10, A20 and full')\nok(all(ck['line'].startswith(ck['label'] + ' is read') for ck in DATA.get('clock', []) if ck['line']), 'a clock line does not open on the reading its stop is named for')"),
])
patch('gate_ui.py', [
("        labels = pg.evaluate(\"[...document.querySelectorAll('#card .clock .cbtn')].map(b => b.textContent)\")\n        ok(labels == ['5 min', '10 min', '20 min', 'full'], c['id'] + ' clock stops (%s)' % labels)\n        if labels != ['5 min', '10 min', '20 min', 'full']: continue",
 "        labels = pg.evaluate(\"[...document.querySelectorAll('#card .clock .cbtn')].map(b => b.textContent)\")\n        ok(labels == ['A5', 'A10', 'A20', 'full'], c['id'] + ' clock stops (%s)' % labels)\n        if labels != ['A5', 'A10', 'A20', 'full']: continue\n        sidx = 1 if c['diag0'] else 0\n        tct, tstate = pg.evaluate(TEACH_CT, [c['id'], sidx])"),
("        ok(pg.evaluate(\"document.querySelector('#card .clock .cbtn.on').textContent\") == '5 min', c['id'] + ' clock 5 min not active')",
 "        ok(pg.evaluate(\"document.querySelector('#card .clock .cbtn.on').textContent\") == 'A5', c['id'] + ' clock A5 not active')\n        ok(abs(pg.evaluate('window.__clot.progress()') - (tct + 300)) < 1e-6, c['id'] + ' A5 stop is not the taught trace CT + 5 min (%s v %s)' % (pg.evaluate('window.__clot.progress()'), tct + 300))\n        for key in ('A5',):   # the class rule the v20 clock broke: a stop named for a reading prints that reading wherever the state lists it\n            if key in tstate['keys']: ok(pg.evaluate(PRINTED, [key, tstate['ti']]), c['id'] + ' A5 stop does not print the A5 its line announces')"),
("        ok(pg.evaluate(\"document.querySelector('#card .clockline').textContent\").startswith('At five minutes'), c['id'] + ' clock 5 min line missing')",
 "        ok(pg.evaluate(\"document.querySelector('#card .clockline').textContent\").startswith('A5 is read'), c['id'] + ' clock A5 line missing')"),
("        ok(pg.evaluate(\"[...document.querySelectorAll('#card .clock .cbtn')][2].disabled\") == (1200 >= win), c['id'] + ' clock 20 min enabled state wrong for a %d s window' % win)",
 "        ok(pg.evaluate(\"[...document.querySelectorAll('#card .clock .cbtn')][2].disabled\") == (tct + 1200 >= win), c['id'] + ' clock A20 enabled state wrong for CT %s on a %d s window' % (tct, win))\n        if tct + 600 < win and 'A10' in tstate['keys']:\n            pg.evaluate(\"[...document.querySelectorAll('#card .clock .cbtn')][1].click()\"); pg.wait_for_timeout(40)\n            ok(pg.evaluate(PRINTED, ['A10', tstate['ti']]) and pg.evaluate(\"document.querySelector('#card .clockline').textContent\").startswith('A10 is read'), c['id'] + ' A10 stop does not print the A10 its line announces')"),
("    ok(pg2r.evaluate(\"document.querySelector('#card .clock .cbtn.on').textContent\") == '5 min' and pg2r.evaluate('window.__clot.progress()') == 300, cr['id'] + ' reduced-motion opening timer overrode a clock stop')",
 "    ok(pg2r.evaluate(\"document.querySelector('#card .clock .cbtn.on').textContent\") == 'A5' and abs(pg2r.evaluate('window.__clot.progress()') - (pg2r.evaluate(TEACH_CT, [cr['id'], 0])[0] + 300)) < 1e-6, cr['id'] + ' reduced-motion opening timer overrode a clock stop')"),
("def ok(c, m):", "TEACH_CT = \"([cid, si]) => { const st = window.__clot.cards.find(x => x.id === cid).knob.states[si]; let ti = st.series.findIndex(s => s.teach); if (ti < 0) ti = 0; const sp = st.series[ti] && st.series[ti].p; return [sp && sp.CT != null ? sp.CT : 0, { ti: ti, keys: (st.compare || []).concat(st.readouts || []) }]; }\"\nPRINTED = \"([key, ti]) => { const rows = [...document.querySelectorAll('#card .readouts tr')]; const row = rows.find(tr => tr.children[0] && tr.children[0].textContent === key); if (row) return !!(row.children[ti + 1] && row.children[ti + 1].textContent.trim()); return [...document.querySelectorAll('#card .readouts span')].some(s => s.textContent.startsWith(key + ' ') && s.querySelector('b') && s.querySelector('b').textContent.trim()); }\"\ndef ok(c, m):"),
])
patch('stress.py', [("for k, lab in ((0, '5 min'), (1, '10 min')):", "for k, lab in ((0, 'A5'), (1, 'A10')):")])
patch('repo/README.md', [("- On every card, the trace at 5, 10 and 20 minutes with the calls each stop allows,", "- On every card, the trace at A5, A10 and A20 (5, 10 and 20 minutes after the clotting time) with the calls each stop allows,")])
s = open('repo/UPLOAD-STEPS.md', encoding='utf-8').read(); assert s.count('Reading the clot v24') == 2; open('repo/UPLOAD-STEPS.md', 'w', encoding='utf-8').write(s.replace('Reading the clot v24', 'Reading the clot v25'))
# the maximum-firmness clock check restated as a rule: printed exactly when the drawn curve is within 2% of its maximum at the stop
p = 'gate_ui.py'; s = open(p, encoding='utf-8').read()
a = s.index("        ok(pg.evaluate(\"[...document.querySelectorAll('#card .readouts td, #card .readouts b')]"); b = s.index("\n", a)
assert 'still prints a maximum firmness the run has not reached' in s[a:b]
s = s[:a] + ("        mreach = pg.evaluate(\"([cid, si, ti]) => { const st = window.__clot.cards.find(x => x.id === cid).knob.states[si]; const p = st.series[ti] && st.series[ti].p; if (!p || p.points || p.MCF == null) return null; return ENGINE.firmness(window.__clot.progress(), p) >= 0.98 * p.MCF; }\", [c['id'], sidx, tstate['ti']])\n"
             "        if mreach is not None and 'MCF' in tstate['keys']: ok(pg.evaluate(PRINTED, ['MCF', tstate['ti']]) == mreach, c['id'] + ' A5 stop prints the maximum firmness %s the curve reaches 98%% of it' % ('before' if not mreach else 'only after'))   # printed exactly when the drawn curve is within 2% of its maximum at the stop (v25; v20 asserted it was never printed, which a clot that plateaus inside five minutes after CT breaks)") + s[b:]
open(p, 'w', encoding='utf-8').write(s)
print('v24 source patched to v25')
```

Then, for v26 (mkdir film, put the re-attached how-a-teg-draws-its-trace-app-v4.mp4 in it, run apply_v26.py, then python3 cards.py and the build):

```python
# apply_v26.py - run inside the v25 src/ folder: turns v25 into v26 (C99, the drawn film on the cup-and-pin card).
# The film is a separate file beside index.html (src/film/<name>), opened from a button under the card title into a
# full-screen layer that plays inline; nothing loads until the button is tapped.
def patch(p, pairs):
    s = open(p, encoding='utf-8').read()
    for old, new in pairs:
        assert s.count(old) == 1, (p, s.count(old), old[:80]); s = s.replace(old, new)
    open(p, 'w', encoding='utf-8').write(s)

patch('cards.py', [
('SECTIONS = ["The trace", "The defects, each with what to give", "The evidence"]',
 'SECTIONS = ["The trace", "The defects, each with what to give", "The evidence"]\n'
 'FILM = "how-a-teg-draws-its-trace-app-v4.mp4"   # the drawn film the cup-and-pin card opens (v26): a file beside index.html, loaded only when tapped'),
('  sources=["S2", "S3", "S4", "S5", "S28"], related=["The five numbers on the trace", "Two names for one curve"],\n',
 '  sources=["S2", "S3", "S4", "S5", "S28"], related=["The five numbers on the trace", "Two names for one curve"],\n'
 '  film=dict(src=FILM, title="How a TEG draws its trace", secs=47, label="Watch it drawn (47 s)"),\n'),
])

patch('template.html', [
('@media (prefers-reduced-motion: reduce){ .chip,.row{transition:none} }',
 '.filmbtn{display:inline-flex;align-items:center;gap:8px;margin-top:10px;min-height:44px;padding:8px 15px 8px 12px;border:1px solid var(--accent);border-radius:22px;font-family:var(--sans);font-size:13.5px;color:var(--accent)}.filmbtn svg{width:14px;height:14px;flex:none}\n'
 '.film{position:fixed;inset:0;z-index:50;background:#1B1612;display:flex;align-items:center;justify-content:center;padding:max(12px,env(safe-area-inset-top)) 12px max(12px,env(safe-area-inset-bottom))}.film[hidden]{display:none}\n'
 '.filmbox{width:min(100%,calc((100vh - 132px) * 0.8));width:min(100%,calc((100dvh - 132px) * 0.8))}   /* as wide as a 4:5 film that fits the height, so the bar lines up with it */\n'
 '.film video{display:block;width:100%;height:auto;background:#EAD9B7;border-radius:4px}\n'
 '.filmbar{display:flex;justify-content:space-between;align-items:center;gap:12px;margin:0 0 10px;color:#EFE9DC;font-family:var(--sans);font-size:13px}\n'
 '.filmx{flex:none;min-width:44px;min-height:44px;display:inline-flex;align-items:center;justify-content:center;color:#EFE9DC;border:1px solid rgba(239,233,220,.55);border-radius:22px}.filmx svg{width:16px;height:16px}\n'
 '.filmnote{color:#D8D0C0;font-family:var(--sans);font-size:12.5px;margin:10px 0 0;min-height:19px;text-align:center}\n'
 '@media (prefers-reduced-motion: reduce){ .chip,.row{transition:none} }'),
("var head = el('div', 'cardhead'); head.appendChild(el('h1', null, card.title)); if (card.twin) { var tw = el('div', 'twin'); tw.innerHTML = 'TEG name: <b>' + esc(card.twin) + '</b>'; head.appendChild(tw); } root.appendChild(head);",
 "var head = el('div', 'cardhead'); head.appendChild(el('h1', null, card.title)); if (card.twin) { var tw = el('div', 'twin'); tw.innerHTML = 'TEG name: <b>' + esc(card.twin) + '</b>'; head.appendChild(tw); }\n"
 "    if (card.film) { var fb = el('button', 'filmbtn'); fb.innerHTML = '<svg viewBox=\"0 0 16 16\" aria-hidden=\"true\"><path d=\"M4.5 2.5l9 5.5-9 5.5z\" fill=\"currentColor\"/></svg><span>' + esc(card.film.label) + '</span>'; fb.addEventListener('click', function(){ openFilm(card.film, fb); }); head.appendChild(fb); }   // v26: the drawn film, one tap away\n"
 "    root.appendChild(head);"),
("  /* ---------- sources ---------- */\n",
 "  /* ---------- film: the drawn TEG, a file beside the page, loaded only when asked for (v26) ---------- */\n"
 "  var filmEl = null, filmFrom = null;\n"
 "  function filmKey(e){ if (e.key === 'Escape') closeFilm(); }\n"
 "  function openFilm(film, from){\n"
 "    if (!filmEl) {\n"
 "      filmEl = el('div', 'film'); filmEl.hidden = true; filmEl.setAttribute('role', 'dialog'); filmEl.setAttribute('aria-modal', 'true'); filmEl.setAttribute('aria-label', film.title);\n"
 "      var bar = el('div', 'filmbar'); bar.appendChild(el('span', 'filmt', film.title + ' \\u00b7 ' + film.secs + ' s'));\n"
 "      var x = el('button', 'filmx'); x.setAttribute('aria-label', 'Close the film'); x.innerHTML = '<svg viewBox=\"0 0 16 16\" aria-hidden=\"true\"><path d=\"M3 3l10 10M13 3L3 13\" stroke=\"currentColor\" stroke-width=\"1.8\" fill=\"none\"/></svg>'; x.addEventListener('click', closeFilm); bar.appendChild(x);\n"
 "      var v = document.createElement('video'); v.setAttribute('playsinline', ''); v.setAttribute('controls', ''); v.setAttribute('preload', 'none'); v.width = 1080; v.height = 1350;\n"
 "      var nt = el('p', 'filmnote', '');\n"
 "      v.addEventListener('waiting', function(){ nt.textContent = 'Loading'; }); v.addEventListener('playing', function(){ nt.textContent = ''; }); v.addEventListener('error', function(){ if (!filmEl.hidden) nt.textContent = v.error && v.error.code === 4 ? 'This browser cannot play the film.' : 'The film did not load. Check the connection and try again.'; });\n"
 "      var box = el('div', 'filmbox'); box.appendChild(bar); box.appendChild(v); box.appendChild(nt); filmEl.appendChild(box);\n"
 "      filmEl.addEventListener('click', function(e){ if (e.target === filmEl) closeFilm(); });   // a tap outside the film closes it\n"
 "      document.body.appendChild(filmEl);\n"
 "    }\n"
 "    filmFrom = from || null; var fv = filmEl.querySelector('video'); filmEl.querySelector('.filmnote').textContent = '';\n"
 "    fv.src = film.src; filmEl.hidden = false; document.addEventListener('keydown', filmKey);\n"
 "    var pr = fv.play(); if (pr && pr.catch) pr.catch(function(){});\n"
 "    filmEl.querySelector('.filmx').focus();\n"
 "  }\n"
 "  function closeFilm(){\n"
 "    if (!filmEl || filmEl.hidden) return;\n"
 "    var fv = filmEl.querySelector('video'); fv.pause(); fv.removeAttribute('src'); fv.load();   // stop the download as well as the picture\n"
 "    filmEl.hidden = true; document.removeEventListener('keydown', filmKey); filmEl.querySelector('.filmnote').textContent = '';\n"
 "    if (filmFrom && document.body.contains(filmFrom)) filmFrom.focus();\n"
 "  }\n\n"
 "  /* ---------- sources ---------- */\n"),
("figure: figure, progress: function(){ return current && current._ctl ? current._ctl.scrub : null; } };",
 "figure: figure, progress: function(){ return current && current._ctl ? current._ctl.scrub : null; }, film: { open: function(){ var c = cards.filter(function(x){ return x.film; })[0]; if (c) openFilm(c.film, null); }, close: closeFilm } };"),
])

patch('build.py', [
("for f in ['template.html', 'engine.js', 'cards.py', 'claims.json', 'fit.json', 'resolve.js', 'fonts.css', os.environ.get('CLOT_CARDS', 'cards.json')]:   # the inputs that shape the HTML\n    h.update(read(f).encode('utf-8'))",
 "for f in ['template.html', 'engine.js', 'cards.py', 'claims.json', 'fit.json', 'resolve.js', 'fonts.css', os.environ.get('CLOT_CARDS', 'cards.json')]:   # the inputs that shape the HTML\n    h.update(read(f).encode('utf-8'))\n"
 "FILMS = [c['film']['src'] for c in json.loads(cards)['cards'] if c.get('film')]   # v26: the film beside the page\n"
 "for fm in FILMS: h.update(open(os.path.join(SRC, 'film', fm), 'rb').read())"),
("open(OUTFILE, 'w', encoding='utf-8').write(html)\n",
 "open(OUTFILE, 'w', encoding='utf-8').write(html)\n"
 "for fm in FILMS: shutil.copy(os.path.join(SRC, 'film', fm), os.path.join(os.path.dirname(os.path.abspath(OUTFILE)), fm))   # the page finds it by a relative name\n"),
("    shutil.copy(os.path.join(OUT, 'clot-icon-180.png'), repo); shutil.copy(os.path.join(OUT, 'reading-the-clot-card.png'), repo)\n",
 "    shutil.copy(os.path.join(OUT, 'clot-icon-180.png'), repo); shutil.copy(os.path.join(OUT, 'reading-the-clot-card.png'), repo)\n"
 "    for fm in FILMS: shutil.copy(os.path.join(SRC, 'film', fm), repo)\n"),
])

patch('gate_build.py', [
("print('gate_build:', P, 'pass,', F, 'fail')",
 "# 13. the film (v26): one card carries it, the file sits beside the page, is held back until tapped, and its label tells the truth\n"
 "films = [c for c in cards if c.get('film')]\n"
 "ok(len(films) == 1 and films[0]['id'] == 'trace', 'the film is not on the cup-and-pin card alone')\n"
 "for c in films:\n"
 "    fm = c['film']; fp = os.path.join(os.path.dirname(os.path.abspath(path)), fm['src'])\n"
 "    ok(re.fullmatch(r'[a-z0-9-]+-v\\d+\\.mp4', fm['src']) is not None, 'film name %s is not a versioned lower-case .mp4' % fm['src'])\n"
 "    ok(os.path.exists(fp), 'film file not beside the page: ' + fp)\n"
 "    if os.path.exists(fp):\n"
 "        mb = os.path.getsize(fp) / 1e6; ok(mb <= 8.0, 'film is %.1f MB, over 8 MB' % mb)\n"
 "        pr = json.loads(subprocess.run(['ffprobe', '-v', 'error', '-show_entries', 'stream=codec_name,pix_fmt,width,height:format=duration', '-of', 'json', fp], capture_output=True, text=True).stdout)\n"
 "        st = pr['streams'][0]; dur = float(pr['format']['duration'])\n"
 "        ok(st['codec_name'] == 'h264' and st['pix_fmt'] == 'yuv420p' and (st['width'], st['height']) == (1080, 1350), 'film stream is not H.264 yuv420p 1080x1350 (%s)' % st)\n"
 "        d = open(fp, 'rb').read(); ok(d.find(b'moov') < d.find(b'mdat'), 'film is not faststart, so it would not start until fully downloaded')\n"
 "        ok(round(dur) == fm['secs'] and fm['label'] == 'Watch it drawn (%d s)' % fm['secs'], 'film label %r does not match its %.1f s' % (fm['label'], dur))\n"
 "ok(\"setAttribute('preload', 'none')\" in html and 'fv.src = film.src' in html, 'the film is not held back until tapped')\n"
 "print('gate_build:', P, 'pass,', F, 'fail')"),
])

patch('gate_ui.py', [
("    b.close()\nok(not errors, 'script errors: ' + '; '.join(errors)[:300])",
 "    # the film (v26): a button on the cup-and-pin card only; nothing loads until it is tapped; it opens over the page, fits the\n"
 "    # screen at 4:5, plays inline with controls, and closes by its button, by Escape or by a tap outside, handing focus back\n"
 "    fcards = pg.evaluate('window.__clot.cards.filter(c => c.film).map(c => c.id)'); ok(fcards == ['trace'], 'film on %s' % fcards)\n"
 "    for c in cards:\n"
 "        pg.evaluate('window.__clot.openCard(%s)' % json.dumps(c['id'])); pg.wait_for_timeout(30)\n"
 "        ok(pg.evaluate(\"document.querySelectorAll('#card .filmbtn').length\") == (1 if c['id'] == 'trace' else 0), c['id'] + ' film button count')\n"
 "    for w, h in ((320, 568), (390, 844), (820, 1180), (1366, 768)):\n"
 "        pgf = b.new_page(viewport={'width': w, 'height': h}, has_touch=True); reqs = []\n"
 "        pgf.on('request', lambda r: reqs.append(r.url))\n"
 "        pgf.goto('file://' + html); pgf.wait_for_timeout(150); pgf.evaluate(\"window.__clot.openCard('trace')\"); pgf.wait_for_timeout(100)\n"
 "        ok(not any(u.endswith('.mp4') for u in reqs) and pgf.evaluate(\"!document.querySelector('.film video') || !document.querySelector('.film video').getAttribute('src')\"), 'film loaded before it was asked for at %d px' % w)\n"
 "        fb = pgf.locator('#card .filmbtn').bounding_box(); ok(fb and fb['height'] >= 44 and fb['x'] >= 0 and fb['x'] + fb['width'] <= w, 'film button target at %d px (%s)' % (w, fb))\n"
 "        pgf.locator('#card .filmbtn').click(); pgf.wait_for_timeout(200)\n"
 "        st = pgf.evaluate(\"(() => { const f = document.querySelector('.film'), v = f && f.querySelector('video'), x = f && f.querySelector('.filmx'); if (!f || f.hidden) return null; const r = v.getBoundingClientRect(), rx = x.getBoundingClientRect(); return { src: v.getAttribute('src'), inline: v.hasAttribute('playsinline'), controls: v.hasAttribute('controls'), vw: r.width, vh: r.height, vl: r.left, vt: r.top, vr: r.right, vb: r.bottom, xw: rx.width, xh: rx.height, xr: rx.right, xt: rx.top, xb: rx.bottom, focus: document.activeElement === x }; })()\")\n"
 "        ok(st is not None, 'film did not open at %d px' % w)\n"
 "        if st:\n"
 "            fsrc = pgf.evaluate(\"window.__clot.cards.find(x => x.id === 'trace').film.src\")\n"
 "            ok(st['src'] == fsrc and st['inline'] and st['controls'], 'film element at %d px (%s)' % (w, st))\n"
 "            ok(st['vl'] >= 0 and st['vt'] >= 0 and st['vr'] <= w + 0.5 and st['vb'] <= h + 0.5 and st['vw'] >= min(w - 40, 300), 'film does not fit a %dx%d screen (%s)' % (w, h, st))\n"
 "            ok(abs(st['vw'] / st['vh'] - 1080 / 1350) < 0.02, 'film box is not 4:5 at %d px (%s)' % (w, st))\n"
 "            ok(st['xw'] >= 44 and st['xh'] >= 44 and st['xr'] <= w and st['xt'] >= 0 and st['xb'] <= st['vt'] + 1 and abs(st['xr'] - st['vr']) <= 2 and st['focus'], 'close button target, place or focus at %d px (%s)' % (w, st))\n"
 "        pgf.keyboard.press('Escape'); pgf.wait_for_timeout(80)\n"
 "        ok(pgf.evaluate(\"document.querySelector('.film').hidden && !document.querySelector('.film video').getAttribute('src')\"), 'Escape did not close and unload the film at %d px' % w)\n"
 "        ok(pgf.evaluate(\"document.activeElement === document.querySelector('#card .filmbtn')\"), 'focus did not return to the film button at %d px' % w)\n"
 "        pgf.locator('#card .filmbtn').click(); pgf.wait_for_timeout(80); pgf.locator('.film .filmx').click(); pgf.wait_for_timeout(80)\n"
 "        ok(pgf.evaluate(\"document.querySelector('.film').hidden\"), 'close button did not close the film at %d px' % w)\n"
 "        pgf.locator('#card .filmbtn').click(); pgf.wait_for_timeout(80); pgf.mouse.click(4, h - 4); pgf.wait_for_timeout(80)\n"
 "        ok(pgf.evaluate(\"document.querySelector('.film').hidden\"), 'a tap outside the film did not close it at %d px' % w)\n"
 "        ok(pgf.evaluate(\"document.documentElement.scrollWidth <= document.documentElement.clientWidth\"), 'sideways scroll with the film at %d px' % w)\n"
 "        pgf.close()\n"
 "    b.close()\nok(not errors, 'script errors: ' + '; '.join(errors)[:300])"),
])

patch('monkey.py', [
("    sels = ['.row',", "    sels = ['.filmbtn', '.row',"),
("        sel = random.choice(sels)\n",
 "        if pg.evaluate(\"() => { const f = document.querySelector('.film'); return !!f && !f.hidden; }\"):   # the film covers the page: the only moves are its close button or Escape\n"
 "            if random.random() < 0.5: pg.evaluate(\"document.querySelector('.film .filmx').click()\")\n"
 "            else: pg.keyboard.press('Escape')\n"
 "            pg.wait_for_timeout(20)\n"
 "            if pg.evaluate(\"!document.querySelector('.film').hidden\"): broken.append('%d: the film did not close' % i)\n"
 "            continue\n"
 "        sel = random.choice(sels)\n"),
])

patch('repo/README.md', [
("- Nothing leaves the device: one HTML file with its two typefaces embedded, nothing fetched from elsewhere, no tracking.",
 "- A drawn film on the cup-and-pin card, \"Watch it drawn (47 s)\": the TEG cup turning, fibrin joining it to the pin and the trace widening, as a separate file that loads only when tapped.\n"
 "- Nothing leaves the device: one HTML file with its two typefaces embedded and the film beside it, nothing fetched from elsewhere, no tracking."),
("Files: `index.html` (the app), `clot-icon-180.png` (home-screen icon), `reading-the-clot-card.png` (link preview), `SOURCES.md`, `LICENSE`.",
 "Files: `index.html` (the app), `how-a-teg-draws-its-trace-app-v4.mp4` (the film), `clot-icon-180.png` (home-screen icon), `reading-the-clot-card.png` (link preview), `SOURCES.md`, `LICENSE`."),
])

s = open('repo/UPLOAD-STEPS.md', encoding='utf-8').read()
assert s.count('Reading the clot v25') == 2
s = s.replace('Reading the clot v25', 'Reading the clot v26')
old = "You need the six files in this folder: index.html, clot-icon-180.png, reading-the-clot-card.png, README.md, SOURCES.md, LICENSE."
assert s.count(old) == 1
s = s.replace(old, "You need the seven files in this folder: index.html, how-a-teg-draws-its-trace-app-v4.mp4, clot-icon-180.png, reading-the-clot-card.png, README.md, SOURCES.md, LICENSE.")
old = "Pick the six files from the Files app"
assert s.count(old) == 1
s = s.replace(old, "Pick the seven files from the Files app")
old = "To update the live site with this version: on the repository page tap Add file > Upload files, pick index.html from this folder (it replaces the old one), write"
assert s.count(old) == 1
s = s.replace(old, "To update the live site with this version: on the repository page tap Add file > Upload files, pick index.html (it replaces the old one) and how-a-teg-draws-its-trace-app-v4.mp4 from this folder, write")
open('repo/UPLOAD-STEPS.md', 'w', encoding='utf-8').write(s)
print('v25 source patched to v26')
```

## V. The video (plan.py, record.py, census.py and qc.py, in one folder beside the delivered index.html)

```
python3 plan.py index.html plan.json 496            # the zoom and every hold's scroll, from the page's own layout
python3 record.py index.html frames plan.json       # resumable: frames on disk are skipped; run with nohup in the background, or rerun after a time limit
ffmpeg -framerate 30 -i frames/f%04d.png -vf "scale=out_color_matrix=bt709:out_range=tv:flags=accurate_rnd+full_chroma_int+full_chroma_inp,format=yuv420p" -c:v libx264 -preset slow -crf 16 -profile:v high -colorspace bt709 -color_primaries bt709 -color_trc iec61966-2-1 -color_range tv -movflags +faststart+write_colr -r 30 out.mp4
python3 census.py index.html plan.json frames      # must end FAULTS 0
python3 qc.py out.mp4 frames plan.json             # decodes the way a phone does (BT.709, limited range); never encode untagged
```

```python
#!/usr/bin/env python3
# plan.py <html> <plan.json> [W ...]: the framing of every hold, chosen from the page's own layout so that no line of text
# and no small box (chip, clock button, table row, figure window) is cut by the frame edges. With several widths it
# reports each and keeps the one with the widest clearances.
import sys, json
from playwright.sync_api import sync_playwright
HTML, OUT = sys.argv[1], sys.argv[2]; WS = [int(w) for w in sys.argv[3:]] or [500]
FW, FH, FOOT, PHONE_W, FLOOR = 1080, 1350, 64, 390, 8.4
JS = """() => { const root = document.querySelector('.screen.on'); const out = { lines: [], boxes: [] };
  const tw = document.createTreeWalker(root, NodeFilter.SHOW_TEXT); let n;
  while ((n = tw.nextNode())) { const t = n.textContent.trim(); if (!t) continue; const pe = n.parentElement; const cs = getComputedStyle(pe); if (cs.display === 'none' || cs.visibility === 'hidden') continue;
    let k = 1; const svg = pe.closest('svg'); if (svg && svg.viewBox && svg.viewBox.baseVal && svg.viewBox.baseVal.width) k = svg.getBoundingClientRect().width / svg.viewBox.baseVal.width;
    const fs = parseFloat(pe.getAttribute('font-size') || cs.fontSize) * k; const rg = document.createRange(); rg.selectNodeContents(n);
    for (const r of rg.getClientRects()) { if (r.width < 1 || r.height < 1) continue; out.lines.push({ t: t.slice(0, 48), top: r.top + scrollY, bot: r.bottom + scrollY, fs: fs, cls: (pe.getAttribute('class') || pe.tagName) }); } }
  root.querySelectorAll('.chip, .cbtn, .row, .win, .iv, tr, .top .back, .ivw, .note').forEach(e => { const r = e.getBoundingClientRect(); if (r.height > 0) out.boxes.push({ t: (e.textContent || '').trim().slice(0, 30), cls: String(e.className || e.tagName), top: r.top + scrollY, bot: r.bottom + scrollY }); });
  out.docH = document.documentElement.scrollHeight; return out; }"""
SOLID = ('chip', 'cbtn', 'win', 'TR', 'back')      # boxes that must never be cut; rows and the What-to-give box may run off an edge
def margin(y, m):
    """clearance in CSS px between an edge at y and the nearest text line or solid box it would cut (negative = cuts)"""
    c = 1e9
    for l in m['lines']: c = min(c, max(l['top'] - y, y - l['bot']))
    for b in m['boxes']:
        if b['cls'].split()[0] in SOLID or b['cls'] == 'TR': c = min(c, max(b['top'] - y, y - b['bot']))
        elif b['cls'].split()[0] == 'row': c = min(c, max(b['bot'] - 1 - y, y - b['bot']))   # a row's hairline rule is kept off the edges too
    return c
def best(m, lo, hi, vis, want=None, step=0.25):
    """the scroll in [lo, hi] whose two edges keep the widest clearance; ties go to the one nearest `want`"""
    cands = []; s = lo
    while s <= hi + 1e-9:
        cands.append((round(min(margin(s, m), margin(s + vis, m)), 2), -abs(s - want) if want is not None else 0, s)); s += step
    return max(cands) if cands else None
def one(p, W):
    H = -(-W * 5 // 4); DPR = FW / W; VIS = (FH - FOOT) / DPR   # H rounded up; the recorder crops the shot to 1350 rows
    b = p.chromium.launch(); pg = b.new_context(viewport={'width': W, 'height': H}, device_scale_factor=DPR).new_page(); pg.emulate_media(reduced_motion='reduce')
    pg.goto('file://' + HTML); pg.wait_for_timeout(250); r = {'W': W, 'H': H, 'DPR': DPR, 'VIS': VIS}
    home = pg.evaluate(JS)
    ver = next(l for l in home['lines'] if l['cls'] == 'ver'); p1 = min((l for l in home['lines'] if l['top'] > ver['bot']), key=lambda l: l['top'])
    r['band'] = (ver['bot'] + p1['top']) / 2; r['band_clear'] = round((p1['top'] - ver['bot']) / 2, 1)
    row = next(x for x in home['boxes'] if x['cls'].startswith('row') and x['t'].startswith('The obstetric'))
    want = (row['top'] + row['bot']) / 2 - 0.6 * VIS
    r['S_row'] = best(home, max(row['bot'] + 12 - VIS, want - 70), min(row['top'] - 12, want + 70), VIS, want)[2]; r['row_clear'] = round(min(margin(r['S_row'], home), margin(r['S_row'] + VIS, home)), 2)
    r['row_frac'] = round(((row['top'] + row['bot']) / 2 - r['S_row']) / VIS, 3)
    pg.evaluate("document.querySelector('.row[data-id=\"obstetric\"]').click()"); pg.wait_for_timeout(700); pg.evaluate('scrollTo(0, 0)')
    states = {}
    for chip in ['19 mm', '12 mm', '7 mm']:
        pg.evaluate("w => [...document.querySelectorAll('#card .chips .chip')].find(b => b.textContent === w).click()", chip); pg.wait_for_timeout(80); states[chip] = pg.evaluate(JS)
    c19, c7 = states['19 mm'], states['7 mm']
    box = lambda m, k, t='': next(x for x in m['boxes'] if x['cls'].split()[0] == k and x['t'].startswith(t))
    win, chips, h1 = box(c19, 'win'), box(c19, 'chip'), next(l for l in c19['lines'] if l['cls'] == 'H1')
    trs = [x for x in c19['boxes'] if x['cls'] == 'TR']; tab_top, tab_bot = min(x['top'] for x in trs), max(x['bot'] for x in trs)
    # the draw: from the top of the page; the whole figure and its table in view
    r['S_draw'] = best(c19, 0, max(0, tab_bot + 2 - VIS), VIS, 0)[2] if tab_bot + 2 - VIS > 0 else 0.0
    r['draw_clear'] = round(min(margin(r['S_draw'] + VIS, c19), 99), 2); r['draw_shows_table'] = r['S_draw'] + VIS >= tab_bot
    # the chips: the whole figure, its table and the chips; clear of all three chip states
    lo, hi = chips['bot'] + 1 - VIS, win['top'] - 1
    cands = []
    s = lo
    while s <= hi:
        cands.append((round(min(min(margin(s, m), margin(s + VIS, m)) for m in states.values()), 2), -abs(s - (lo + hi) / 2), s)); s += 0.25
    k = max(cands) if cands else (None, None, None); r['S_chips'] = k[2]; r['chips_clear'] = k[0]
    # the end, after 7 mm: the table, the chips, the note, What to give and when to give it; the figure window above the frame
    tr7 = [x for x in c7['boxes'] if x['cls'] == 'TR']; w7 = box(c7, 'win'); when = [l for l in c7['lines'] if l['t'].startswith('FIBTEM A5 under')]
    lo, hi = w7['bot'] + 0.5, min(x['top'] for x in tr7) - 0.5
    lo = max(lo, max(l['bot'] for l in when) + 2 - VIS)
    e = best(c7, lo, hi, VIS, lo) if lo <= hi else None
    r['S_end'] = e[2] if e else None; r['end_clear'] = e[0] if e else None
    if e:
        r['end_cuts_after'] = next((l['t'][:40] for l in sorted(c7['lines'], key=lambda l: -l['bot']) if l['bot'] <= r['S_end'] + VIS), None)
    # the smallest text in any hold, at phone size
    def smallest(m, a, z):
        v = [l for l in m['lines'] if l['bot'] > a and l['top'] < z]; l = min(v, key=lambda l: l['fs']); return round(l['fs'] * PHONE_W / W, 2), l['t'][:20]
    r['small'] = min(smallest(home, 0, r['band']), smallest(home, r['S_row'], r['S_row'] + VIS), smallest(c19, r['S_draw'], r['S_draw'] + VIS), smallest(c19, r['S_chips'] or 0, (r['S_chips'] or 0) + VIS), smallest(c7, r['S_end'] or 0, (r['S_end'] or 0) + VIS))
    r['geo'] = {'row': [row['top'], row['bot']], 'h1': [h1['top'], h1['bot']], 'win': [win['top'], win['bot']], 'table': [tab_top, tab_bot], 'chips': [chips['top'], chips['bot']], 'docH': c19['docH'], 'docH7': c7['docH'], 'docH_home': home['docH']}
    b.close(); return r
with sync_playwright() as p:
    res = [one(p, W) for W in WS]
for r in res: print(json.dumps({k: (round(v, 2) if isinstance(v, float) else v) for k, v in r.items() if k != 'geo'}))
ok = [r for r in res if r['S_end'] is not None and r['S_chips'] is not None and r['small'][0] >= FLOOR]
if ok:
    pick = max(ok, key=lambda r: min(r['band_clear'], r['row_clear'], r['draw_clear'], r['chips_clear'], r['end_clear']))
    json.dump(pick, open(OUT, 'w'), indent=1); print('PICK', pick['W'], 'min clearance', min(pick['band_clear'], pick['row_clear'], pick['draw_clear'], pick['chips_clear'], pick['end_clear']))
else: print('NO WIDTH FITS')
```

```python
#!/usr/bin/env python3
# record.py <html> <frames_dir> <plan.json>: the obstetric-card walkthrough rendered frame by frame from the app itself at
# 1080x1350, under Playwright's fake clock so the app's own opening draw runs at its own speed. The zoom and every hold's
# scroll come from plan.json (plan.py), which keeps text and small boxes off the frame edges. Resumable: frames on disk are skipped.
import sys, os, io, math, json
import numpy as np
from playwright.sync_api import sync_playwright
from PIL import Image, ImageDraw, ImageFont
HTML = os.path.abspath(sys.argv[1]); OUT = sys.argv[2]; PLAN = json.load(open(sys.argv[3])); os.makedirs(OUT, exist_ok=True)
FPS, W, H, DPR = 30, PLAN['W'], PLAN['H'], PLAN['DPR']   # 1080/W zoom: text at or above the phone floor, see plan.py
FW, FH, FOOT = 1080, 1350, 64
VIS = (FH - FOOT) / DPR                      # CSS px visible above the footer strip
assert abs(VIS - PLAN['VIS']) < 1e-6 and round(W * DPR) == FW and H * DPR >= FH - 0.01
S_ROW, S_DRAW, S_CHIPS, S_END = PLAN['S_row'], PLAN['S_draw'], PLAN['S_chips'], PLAN['S_end']
LAND = (1.60, 2.60)
TAPS = [(2.62, 2.92, 'row', 0.30), (8.30, 8.42, '12 mm', 0.42), (10.40, 10.52, '7 mm', 0.42)]
CS1 = (7.52, 8.02); CS2 = (12.62, 13.52); T_END = 15.6; N = int(round(T_END * FPS))
ACC = (0x7A, 0x1F, 0x3D); CREAM = (0xEF, 0xE9, 0xDC); PAPER = (0xFB, 0xF9, 0xF4); MUTED = (0x5B, 0x53, 0x49); RULE = (0xD8, 0xD0, 0xC0); INK = (0x22, 0x1E, 0x19)
F = '/usr/share/fonts/truetype/google-fonts/'
QUESTION = 'Which number falls first in a postpartum bleed?'
CREDIT = 'Dr Ganesh Sivasankara · MD · FRCA · FCARCSI · Consultant Anaesthetist'
def io_(u): u = max(0.0, min(1.0, u)); return 4 * u ** 3 if u < 0.5 else 1 - (-2 * u + 2) ** 3 / 2
def dio(u): u = max(0.0, min(1.0, u)); return 12 * u ** 2 if u < 0.5 else 3 * (2 - 2 * u) ** 2
def sin_io(u): u = max(0.0, min(1.0, u)); return (1 - math.cos(math.pi * u)) / 2
def out_(u): u = max(0.0, min(1.0, u)); return 1 - (1 - u) ** 3
def vblur(a, L):
    L = int(round(L))
    if L < 2: return a
    pad = L // 2; ap = np.pad(a, ((pad, L - 1 - pad), (0, 0), (0, 0)), mode='edge'); c = np.cumsum(ap, axis=0, dtype=np.float64)
    c = np.concatenate([np.zeros((1,) + c.shape[1:]), c], axis=0); return (c[L:] - c[:-L]) / L
lora = ImageFont.truetype(F + 'Lora-Variable.ttf', 60); lora.set_variation_by_axes([500])
pop = ImageFont.truetype(F + 'Poppins-Regular.ttf', 25)
QL = ['Which number falls first', 'in a postpartum bleed?']; LH = 78
BAND_Y0, BAND_Y1 = PLAN['band'] * DPR, FH - FOOT   # the band's top sits in the gap under the version line (plan.py)
def overlay(im, t, rings, S, on_cover, blur=0.0):
    layer = Image.new('RGBA', im.size, (0, 0, 0, 0)); d = ImageDraw.Draw(layer)
    if on_cover and BAND_Y1 - S * DPR > 0:
        y0 = BAND_Y0 - S * DPR; d.rectangle([0, y0, FW, y0 + (BAND_Y1 - BAND_Y0)], fill=ACC + (255,))
        y = y0 + (BAND_Y1 - BAND_Y0 - LH * len(QL)) / 2 - 6
        for ln in QL: d.text((BX0, y), ln, font=lora, fill=PAPER + (255,)); y += LH
    for what, (t0, dur, cx, cy) in rings.items():
        if t0 <= t < t0 + dur:
            u = (t - t0) / dur; r = (18 + 10 * out_(u)) * DPR; k = (1 - u) ** 1.2
            d.ellipse([cx * DPR - r, cy * DPR - r, cx * DPR + r, cy * DPR + r], fill=INK + (int(255 * 0.20 * k),), outline=PAPER + (int(255 * 0.85 * k),), width=4)
    base = Image.alpha_composite(im.convert('RGBA'), layer).convert('RGB')
    if blur >= 2: base = Image.fromarray(np.clip(np.round(vblur(np.asarray(base, dtype=np.float32), blur)), 0, 255).astype(np.uint8))
    d = ImageDraw.Draw(base)   # the footer is fixed to the frame, drawn after any smear
    d.rectangle([0, FH - FOOT, FW, FH], fill=CREAM); d.rectangle([0, FH - FOOT, FW, FH - FOOT + 1], fill=RULE)
    tw = pop.getlength(CREDIT); bb = pop.getbbox(CREDIT)
    d.text(((FW - tw) / 2, FH - FOOT / 2 - (bb[1] + bb[3]) / 2), CREDIT, font=pop, fill=MUTED)
    im.paste(base); return im
GEO = """() => { const q = s => { const r = document.querySelector(s).getBoundingClientRect(); return [r.top + scrollY, r.bottom + scrollY]; };
  const on = document.querySelector('.screen.on'); const o = { docH: document.documentElement.scrollHeight };
  if (on.querySelector('.row[data-id="obstetric"]')) o.row = q('.row[data-id="obstetric"]');
  if (on.querySelector('#card .win')) { o.win = q('#card .win'); o.h1 = q('#card h1'); o.chips = q('#card .chips .chip'); const t = [...on.querySelectorAll('#card tr')].map(e => e.getBoundingClientRect()); o.table = [t[0].top + scrollY, t[t.length - 1].bottom + scrollY]; }
  const w = document.querySelector('.wrap'); const cs = getComputedStyle(w), r = w.getBoundingClientRect(); o.col = [r.left + parseFloat(cs.paddingLeft), r.right - parseFloat(cs.paddingRight)];
  return o; }"""
def same(live, key, tol=0.6):   # the live page must match the page the plan was measured on
    a, b = live[key], PLAN['geo'][key]; assert all(abs(x - y) <= tol for x, y in zip(a, b)), (key, a, b)
with sync_playwright() as p:
    b = p.chromium.launch(); ctx = b.new_context(viewport={'width': W, 'height': H}, device_scale_factor=DPR); pg = ctx.new_page()
    pg.clock.install(time=0); pg.goto('file://' + HTML); pg.evaluate('document.fonts.ready.then(() => true)'); pg.clock.pause_at(5000); now = BASE = 5000
    g = pg.evaluate(GEO); same(g, 'row'); BX0, BX1 = g['col'][0] * DPR, g['col'][1] * DPR
    assert all(lora.getlength(l) <= BX1 - BX0 for l in QL) and ' '.join(QL) == QUESTION
    card = None; rings = {}; prev = -1.0; made = 0
    for i in range(N):
        t = i / FPS; target = BASE + round(t * 1000)
        if target > now: pg.clock.run_for(target - now); now = target
        for tap_t, click_t, what, dur in TAPS:
            if prev < click_t <= t:
                if what == 'row':
                    pg.evaluate("document.querySelector('.row[data-id=\"obstetric\"]').click()"); card = pg.evaluate(GEO)
                    for k in ('win', 'table', 'chips'): same(card, k)
                else:
                    pg.evaluate("w => [...document.querySelectorAll('#card .chips .chip')].find(b => b.textContent === w).click()", what)
                    if what == '7 mm': assert abs(pg.evaluate(GEO)['docH'] - PLAN['geo']['docH7']) < 1
        blur = 0.0
        if card is None:
            S = S_ROW * sin_io((t - LAND[0]) / (LAND[1] - LAND[0]))
            if LAND[0] < t < LAND[1]:   # the flick down the cover: a vertical smear as long as the page moves in half a frame (180 degree shutter)
                u = (t - LAND[0]) / (LAND[1] - LAND[0]); blur = S_ROW * math.pi / 2 * math.sin(math.pi * u) / (LAND[1] - LAND[0]) * DPR * 0.5 / FPS
        else:
            if t < CS1[0]: S = S_DRAW
            elif t < CS2[0]:
                u = (t - CS1[0]) / (CS1[1] - CS1[0]); S = S_DRAW + (S_CHIPS - S_DRAW) * io_(u)
                if 0 < u < 1: blur = abs(S_CHIPS - S_DRAW) * dio(u) / (CS1[1] - CS1[0]) * DPR * 0.5 / FPS   # the same shutter on the card's own scrolls
            else:
                u = (t - CS2[0]) / (CS2[1] - CS2[0]); S = S_CHIPS + (S_END - S_CHIPS) * io_(u)
                if 0 < u < 1: blur = abs(S_END - S_CHIPS) * dio(u) / (CS2[1] - CS2[0]) * DPR * 0.5 / FPS
        pg.evaluate('y => window.scrollTo(0, y)', S)
        for tap_t, click_t, what, dur in TAPS:
            if prev < tap_t <= t:
                sel = ".row[data-id=\"obstetric\"]" if what == 'row' else None
                r = pg.evaluate("([w, sel]) => { const e = sel ? document.querySelector(sel) : [...document.querySelectorAll('#card .chips .chip')].find(b => b.textContent === w); const r = e.getBoundingClientRect(); return [r.left + r.width / 2, r.top + r.height / 2]; }", [what, sel])
                rings[what] = (tap_t, dur, r[0], r[1])
        prev = t
        path = os.path.join(OUT, 'f%04d.png' % i)
        if os.path.exists(path): continue
        im = Image.open(io.BytesIO(pg.screenshot(type='png'))).convert('RGB')
        if im.size != (FW, FH): im = im.crop((0, 0, FW, FH))
        overlay(im, t, rings, S, card is None, blur)
        tmp = path + '.tmp.png'; im.save(tmp, compress_level=1); os.replace(tmp, path); made += 1
    print('frames', N, 'made', made, 'W', W, 'DPR', round(DPR, 4), 'holds', [round(x, 2) for x in (S_ROW, S_DRAW, S_CHIPS, S_END)], 'column', [round(BX0, 1), round(BX1, 1)], 'credit width', round(pop.getlength(CREDIT)))
    b.close()
```

```python
#!/usr/bin/env python3
# census.py <html> <plan.json> [frames_dir]: every hold of the video framed as the recorder frames it (from the same plan).
# Reports text read at phone size, any text line or small box cut by a frame edge, and the clearance left at each edge;
# with frames_dir it also looks at the rendered pixels along each edge of every hold for ink the page layout missed.
import sys, json, os
import numpy as np
from PIL import Image
from playwright.sync_api import sync_playwright
HTML, PLAN = sys.argv[1], json.load(open(sys.argv[2])); FR = sys.argv[3] if len(sys.argv) > 3 else None
W, H, DPR, VIS = PLAN['W'], PLAN['H'], PLAN['DPR'], PLAN['VIS']; PHONE = 390 / W; FLOOR = 8.4; FPS = 30; FH, FOOT = 1350, 64
JS = open(os.path.join(os.path.dirname(os.path.abspath(__file__)), 'plan.py')).read().split('JS = """')[1].split('"""')[0]
SOLID = ('chip', 'cbtn', 'win', 'TR', 'back')
def edge_hits(m, y):
    out = []
    for l in m['lines']:
        if l['top'] < y < l['bot']: out.append('text "%s" (%s, %.1f-%.1f)' % (l['t'][:34], l['cls'], l['top'], l['bot']))
    for b in m['boxes']:
        k = b['cls'].split()[0]
        if (k in SOLID) and b['top'] < y < b['bot']: out.append('box %s "%s" (%.1f-%.1f)' % (k, b['t'][:24], b['top'], b['bot']))
    return out
def clearance(m, y):
    c = 1e9
    for l in m['lines']: c = min(c, max(l['top'] - y, y - l['bot']))
    for b in m['boxes']:
        k = b['cls'].split()[0]
        if k in SOLID: c = min(c, max(b['top'] - y, y - b['bot']))
        elif k == 'row': c = min(c, max(b['bot'] - 1 - y, y - b['bot']))
    return c
faults = 0
def hold(name, m, top, bot, top_is_page_top=False):
    global faults
    vis = [l for l in m['lines'] if l['bot'] > top + 0.5 and l['top'] < bot - 0.5]
    small = min(vis, key=lambda l: l['fs']); cuts = ([] if top_is_page_top else edge_hits(m, top)) + edge_hits(m, bot)
    ct = 99.0 if top_is_page_top else clearance(m, top); cb = clearance(m, bot)
    print('--- %s: %d text lines in view; smallest %.2f px on a phone ("%s"); clearance top %.2f, bottom %.2f CSS px' % (name, len(vis), small['fs'] * PHONE, small['t'][:20], min(ct, 99), cb))
    for c in cuts: print('   CUT at an edge:', c); faults += 1
    if small['fs'] * PHONE < FLOOR: print('   SMALL: below the %.1f px floor' % FLOOR); faults += 1
with sync_playwright() as p:
    b = p.chromium.launch(); pg = b.new_context(viewport={'width': W, 'height': H}, device_scale_factor=DPR).new_page(); pg.emulate_media(reduced_motion='reduce')
    pg.goto('file://' + HTML); pg.wait_for_timeout(300); home = pg.evaluate(JS)
    hold('cover, 0-1.6 s (the band covers the page from %.1f)' % PLAN['band'], home, 0, PLAN['band'], True)
    hold('list, tap on the row, 2.6-2.9 s', home, PLAN['S_row'], PLAN['S_row'] + VIS)
    pg.evaluate("document.querySelector('.row[data-id=\"obstetric\"]').click()"); pg.wait_for_timeout(700); pg.evaluate('scrollTo(0, 0)')
    st = {}
    for chip in ['19 mm', '12 mm', '7 mm']:
        pg.evaluate("w => [...document.querySelectorAll('#card .chips .chip')].find(b => b.textContent === w).click()", chip); pg.wait_for_timeout(80); st[chip] = pg.evaluate(JS)
    hold('card drawing, 2.9-7.5 s', st['19 mm'], PLAN['S_draw'], PLAN['S_draw'] + VIS, PLAN['S_draw'] == 0)
    for chip in st: hold('chips at %s, 8.0-12.6 s' % chip, st[chip], PLAN['S_chips'], PLAN['S_chips'] + VIS)
    hold('end, What to give, 13.5-15.6 s', st['7 mm'], PLAN['S_end'], PLAN['S_end'] + VIS)
    b.close()
def L(h):
    h = h.lstrip('#'); c = [int(h[i:i + 2], 16) / 255 for i in (0, 2, 4)]; c = [v / 12.92 if v <= 0.03928 else ((v + 0.055) / 1.055) ** 2.4 for v in c]; return 0.2126 * c[0] + 0.7152 * c[1] + 0.0722 * c[2]
def cr(a, b): la, lb = sorted([L(a), L(b)], reverse=True); return (la + 0.05) / (lb + 0.05)
print('--- overlays: band text cream on garnet %.1f:1, footer text on cream %.1f:1 (need 4.5)' % (cr('#FBF9F4', '#7A1F3D'), cr('#5B5349', '#EFE9DC')))
if FR:   # the pixels: ink (anything darker than the page's rules) in the three rows at each edge of every held frame
    HOLDS = {'cover': (0, 1.6), 'list': (2.6, 2.92), 'draw': (3.0, 7.5), 'chips': (8.05, 12.6), 'end': (13.55, 15.6)}
    for name, (a, z) in HOLDS.items():
        worst = []
        for i in range(int(round(a * FPS)), int(round(z * FPS))):
            f = np.asarray(Image.open(os.path.join(FR, 'f%04d.png' % i)).convert('L'), dtype=np.int16)
            band_top = int(round(PLAN['band'] * DPR)) if name == 'cover' else None
            rows = {'top': f[0:3], 'bottom': f[FH - FOOT - 3:FH - FOOT]}
            if band_top: rows = {'band edge': f[band_top - 4:band_top - 1]}   # the page just above the question band
            for k, r in rows.items():
                ink = r < 170; cols = np.where(ink.any(axis=0))[0]; n = 0
                for run in np.split(cols, np.where(np.diff(cols) > 1)[0] + 1) if len(cols) else []:
                    if len(run) <= 3 and ink[:, run].any(axis=1).all(): continue   # a box's side border running on past the edge, not a cut
                    n += int(ink[:, run].sum())
                if n: worst.append((n, k, i))
        print('--- pixels, %s hold: %s' % (name, 'no ink on any edge' if not worst else 'INK on an edge %s' % sorted(worst)[-3:]))
        faults += bool(worst)
print('FAULTS', faults)
```

```python
#!/usr/bin/env python3
# qc.py <video.mp4> <frames_dir> <plan.json>: the encoded file decoded the way a phone decodes it (BT.709, limited range),
# checked against the frames it was made from; colour of the app's own paints; what moves when; seeking; determinism.
import sys, subprocess, json, hashlib
import numpy as np
from PIL import Image
V, FR, PLAN = sys.argv[1], sys.argv[2], json.load(open(sys.argv[3])); FW, FH, N, FPS = 1080, 1350, 468, 30
DEC = ['-vf', 'scale=in_color_matrix=bt709:in_range=tv:out_range=pc:flags=accurate_rnd+full_chroma_int,format=rgb24', '-f', 'rawvideo', '-']
def src(i): return np.asarray(Image.open('%s/f%04d.png' % (FR, i)).convert('RGB'), dtype=np.int16)
def psnr(a, b): m = ((a.astype(np.float64) - b) ** 2).mean(); return 99.0 if m == 0 else 10 * np.log10(255 ** 2 / m)
p = subprocess.Popen(['ffmpeg', '-v', 'error', '-i', V] + DEC, stdout=subprocess.PIPE); dec = {}; ps = []; still = []; prev = None; i = 0; keep = {0, 88, 240, 250, 300, 380, 407, 467}
band_y = int(round(PLAN['band'] * PLAN['DPR'])) + 12
while True:
    buf = p.stdout.read(FW * FH * 3)
    if len(buf) < FW * FH * 3: break
    f = np.frombuffer(buf, np.uint8).reshape(FH, FW, 3).astype(np.int16); s = src(i); ps.append(psnr(f, s))
    if prev is not None: still.append(int(np.abs(f - prev).max()))
    if i in keep: dec[i] = f
    prev = f; i += 1
p.wait(); print('decoded frames', i, '| PSNR against the source frames: min %.1f dB (frame %d), mean %.1f dB' % (min(ps), int(np.argmin(ps)), np.mean(ps)))
def at(f, x0, x1, y0, y1): return tuple(int(round(v)) for v in f[y0:y1, x0:x1].reshape(-1, 3).mean(0))
print('colour as a phone shows it (target in brackets): band garnet %s (122, 31, 61) | page %s (%s) | footer cream %s (239, 233, 220)' % (at(dec[0], 20, 60, band_y, band_y + 30), at(dec[0], 20, 60, 6, 16), tuple(int(v) for v in src(0)[6:16, 20:60].reshape(-1, 3).mean(0)), at(dec[0], 20, 60, FH - 20, FH - 8)))
# what moves, and when: runs of frames whose source changes from the previous frame
runs, cur = [], None
for k in range(1, N):
    d = np.abs(src(k) - src(k - 1)).max(axis=2) > 6
    if d.any():
        ys, xs = np.where(d); box = [int(xs.min()), int(ys.min()), int(xs.max()), int(ys.max())]
        if cur and cur[1] == k - 1: cur[1] = k; cur[2] = [min(cur[2][0], box[0]), min(cur[2][1], box[1]), max(cur[2][2], box[2]), max(cur[2][3], box[3])]
        else: cur = [k, k, box]; runs.append(cur)
print('what moves (source frames): ' + '; '.join('%.2f-%.2f s in x %d-%d, y %d-%d' % (a / FPS, b / FPS, bx[0], bx[2], bx[1], bx[3]) for a, b, bx in runs))
# after encoding: the held frames must stay held (no pulsing at keyframes); largest frame-to-frame change inside each still stretch
stills = []; k0 = 0
moving = set(k for a, b, _ in runs for k in range(a, b + 1))
for k in range(1, N):
    if k in moving:
        if k - k0 > 5: stills.append((k0, k - 1))
        k0 = k
if N - k0 > 5: stills.append((k0, N - 1))
print('held stretches after encoding (largest pixel step from one frame to the next, 0-255): ' + '; '.join('%.2f-%.2f s: %d' % (a / FPS, b / FPS, max(still[a:b]) if b > a else 0) for a, b in stills))
# keyframes, seeking and determinism
kf = subprocess.run(['ffprobe', '-v', 'error', '-select_streams', 'v', '-show_entries', 'frame=key_frame,pts_time', '-of', 'csv=p=0', V], capture_output=True, text=True).stdout.split()
print('keyframes at', [r.split(',')[1] for r in kf if r.startswith('1')])
bad = []
for j in sorted(keep):
    buf = subprocess.run(['ffmpeg', '-v', 'error', '-ss', '%.4f' % ((j - 0.4) / FPS), '-i', V, '-frames:v', '1'] + DEC, capture_output=True).stdout
    g = np.frombuffer(buf[:FW * FH * 3], np.uint8).reshape(FH, FW, 3).astype(np.int16)
    if not np.array_equal(g, dec[j]): bad.append(j)
print('seeking to frames %s gives the same picture as playing through: %s' % (sorted(keep), 'yes' if not bad else 'NO at %s' % bad))
h = [hashlib.sha256(subprocess.run(['ffmpeg', '-v', 'error', '-i', V, '-f', 'framemd5', '-'], capture_output=True).stdout).hexdigest() for _ in range(2)]
print('two decodes identical:', h[0] == h[1])
```

## X. The notebook video, v4 (leo.py with model.py from section W, render_leo.py, qc_leo.py in one folder; scipy and opencv needed)

```
python3 render_leo.py lframes4 0 2 & python3 render_leo.py lframes4 1 2    # two halves in parallel; resumable; the sheet and the wash are made on the first frame
ENC="scale=out_color_matrix=bt709:out_range=tv:flags=accurate_rnd+full_chroma_int+full_chroma_inp,format=yuv420p"
ffmpeg -framerate 30 -i lframes4/f%04d.png -vf "$ENC" -c:v libx264 -preset slow -crf 16 -profile:v high -colorspace bt709 -color_primaries bt709 -color_trc iec61966-2-1 -color_range tv -movflags +faststart+write_colr -r 30 how-a-teg-draws-its-trace-notebook-v4.mp4
ffmpeg -framerate 30 -i lframes4/f%04d.png -vf "$ENC" -c:v libx264 -preset slow -crf 23 -profile:v high -colorspace bt709 -color_primaries bt709 -color_trc iec61966-2-1 -color_range tv -movflags +faststart+write_colr -r 30 how-a-teg-draws-its-trace-app-v4.mp4   # the app's lighter copy (C99)
python3 qc_leo.py how-a-teg-draws-its-trace-notebook-v4.mp4 lframes4
```

```python
#!/usr/bin/env python3
# leo.py: "How a TEG draws its trace" as a page from Leonardo's anatomical notebooks. A parchment sheet taller than the
# frame; iron-gall ink and red chalk; left-handed hatching running down to the right; the cup drawn from the side and
# from above; the trace drawn by the pin and hatched in red chalk; notes in an italic hand written beside the drawings.
# A camera moves over the sheet (whole page, in on the start of the trace, down to the foot of the page at the close).
# Every frame is drawn in Python: ink on a 3x layer averaged down, text at 1x in Crimson Pro. frame(v) -> image at v s.
import math, random, os
import numpy as np
from PIL import Image, ImageDraw, ImageFont, ImageFilter
import model as M

W, H, SS, FOOT = 1080, 1350, 3, 64
SHEET_H = 2100
PARCH = np.array([0xEA, 0xDA, 0xB8], float)
INK, SEPIA, SANG, CHALK = (0x3A, 0x26, 0x17), (0x6B, 0x49, 0x2D), (0x98, 0x3A, 0x26), (0xB8, 0x6A, 0x50)
BAND, RULEC = (0xDD, 0xCC, 0xA8), (0x8E, 0x74, 0x55)
HALO = (0xE9, 0xD9, 0xB7)                          # the sheet's own colour, for clearing hatching round a word
FD = '/mnt/skills/examples/canvas-design/canvas-fonts/'
_F = {}
def font(kind, size):
    size = max(8, int(round(size)))
    k = (kind, size)
    if k not in _F: _F[k] = ImageFont.truetype(FD + {'it': 'CrimsonPro-Italic.ttf', 'rm': 'CrimsonPro-Regular.ttf', 'bd': 'CrimsonPro-Bold.ttf'}[kind], size)
    return _F[k]
CREDIT = 'Dr Ganesh Sivasankara · MD · FRCA · FCARCSI · Consultant Anaesthetist'

# ---------------------------------------------------------------- timing, the same script as the garnet version
NOTES = [   # (from, to, text, where) where: 'page' = the note block under the top view; 'detail' = beside the start of the trace
    (0.0, 4.2, 'A TEG turns a cup of blood back and forth around a pin.', 'page'),
    (4.2, 8.0, 'Liquid blood leaves the pin still, so the trace is flat.', 'page'),
    (8.0, 11.8, 'As the blood clots, fibrin links the cup to the pin.', 'page'),
    (11.8, 15.6, 'The pin starts to swing, and the trace widens with it.', 'page'),
    (16.45, 20.1, 'R is the time until the trace is 2 mm wide.', 'detail'),
    (20.1, 23.3, 'K is the time from 2 to 20 mm.', 'detail'),
    (23.3, 27.4, 'Alpha is the angle of the rise, the speed of fibrin build-up.', 'detail'),
    (28.2, 32.6, 'MA, the widest point, is the clot’s strength, set by platelets and fibrinogen.', 'page'),
    (32.6, 36.8, 'LY30 is the share of that width lost 30 minutes after MA.', 'page'),
    (36.8, 45.5, 'This trace is an example, drawn through the middle of\nthe R, K and MA ranges.', 'foot'),
]
T_START, T_CLOSE, T_END = 3.0, 36.8, 45.5          # story time; the video adds the cover in front (T_COVER)
T_HOLD, T_COVER = 1.0, 1.5                         # the finished page held, then the ink lifts back to the red chalk
T_VIDEO = T_COVER + T_END
KNOTS = [(3.0, 0.0), (8.0, 5.6), (11.8, 6.9), (16.3, 8.6), (20.1, 8.7), (23.3, 8.78), (27.4, 8.86), (28.2, 9.4), (29.4, 12.0), (30.6, 34.3), (32.6, 35.6), (34.6, 64.3), (35.2, 66.0)]
def pchip(xs, ys):
    xs, ys = np.array(xs, float), np.array(ys, float); h = np.diff(xs); dl = np.diff(ys) / h; m = np.zeros(len(xs))
    for i in range(1, len(xs) - 1):
        if dl[i - 1] * dl[i] > 0: w1, w2 = 2 * h[i] + h[i - 1], h[i] + 2 * h[i - 1]; m[i] = (w1 + w2) / (w1 / dl[i - 1] + w2 / dl[i])
    m[0], m[-1] = dl[0], dl[-1]
    def f(x):
        if x <= xs[0]: return float(ys[0])
        if x >= xs[-1]: return float(ys[-1])
        i = int(np.searchsorted(xs, x) - 1); t = (x - xs[i]) / h[i]
        return float((2*t**3 - 3*t**2 + 1) * ys[i] + (t**3 - 2*t**2 + t) * h[i] * m[i] + (-2*t**3 + 3*t**2) * ys[i+1] + (t**3 - t**2) * h[i] * m[i+1])
    return f
TEST_MIN = pchip(*zip(*KNOTS))
def test_min(v): return 0.0 if v < T_START else TEST_MIN(v)
def smooth(u): u = max(0.0, min(1.0, u)); return u * u * (3 - 2 * u)
def ramp(v, a, b): return smooth((v - a) / (b - a)) if b > a else float(v >= a)
def ease(u): u = max(0.0, min(1.0, u)); return 4 * u ** 3 if u < 0.5 else 1 - (-2 * u + 2) ** 3 / 2

# ---------------------------------------------------------------- the camera over the sheet
CAM_FULL, CAM_DETAIL, CAM_FOOT = (540.0, 675.0, 1.0), (177.0, 1032.0, 5.0), (540.0, 1390.0, 1.0)
def cam_mix(a, b, u):
    """zoom in log space about the one point of the sheet that stays still on screen, so the move reads as leaning in"""
    (ax, ay, az), (bx, by, bz) = a, b
    if abs(az - bz) < 1e-9: return (ax + (bx - ax) * u, ay + (by - ay) * u, az)
    z = az * (bz / az) ** u; k = (1 - az / z) / (1 - az / bz)
    return (ax + (bx - ax) * k, ay + (by - ay) * k, z)
def camera(v):
    c = CAM_FULL
    if v >= 15.4: c = cam_mix(CAM_FULL, CAM_DETAIL, ease((v - 15.4) / 1.3))   # after the last page note has gone
    if v >= 27.2: c = cam_mix(CAM_DETAIL, CAM_FULL, ease((v - 27.2) / 1.4))
    if v >= 36.7: c = cam_mix(CAM_FULL, CAM_FOOT, ease((v - 36.7) / 1.8))
    return c
def to_screen(pts, cam):
    cx, cy, z = cam; p = np.asarray(pts, float)
    return np.stack([(p[..., 0] - cx) * z + W / 2, (p[..., 1] - cy) * z + H / 2], axis=-1)

# ---------------------------------------------------------------- strokes: a pen line with a wandering edge and pressure
class Pen:
    def __init__(self, seed): self.r = random.Random(seed)
    def wobble(self, n, amp, waves=3):
        s = np.linspace(0, 1, n); out = np.zeros(n)
        for k in range(waves):
            out += amp / (k + 1) * np.sin(2 * math.pi * s * self.r.uniform(0.6, 2.4) * (k + 1) + self.r.uniform(0, 6.3))
        return out
def stroke(pts, width, seed, jitter=0.7, taper=0.35):
    """a stroke as left and right edges in sheet space plus normalised arc length, for reveal"""
    p = np.asarray(pts, float)
    if len(p) < 2: return None
    seg = np.hypot(*np.diff(p, axis=0).T); L = seg.sum()
    if L < 0.5: return None
    n = max(4, int(L / 2.5)); s = np.concatenate([[0], np.cumsum(seg)]) / L
    u = np.linspace(0, 1, n); q = np.stack([np.interp(u, s, p[:, 0]), np.interp(u, s, p[:, 1])], axis=1)
    d = np.gradient(q, axis=0); d /= (np.hypot(d[:, 0], d[:, 1])[:, None] + 1e-9); nrm = np.stack([-d[:, 1], d[:, 0]], axis=1)
    pen = Pen(seed); q = q + nrm * pen.wobble(n, jitter)[:, None]
    press = (np.sin(np.pi * np.clip(u, 0, 1)) ** taper) * (1 + 0.14 * pen.wobble(n, 1.0, 2)); w = np.maximum(0.25, width * (0.35 + 0.65 * press))
    return dict(q=q, nrm=nrm, w=w, Lt=q + nrm * (w / 2)[:, None], u=u)
def stroke_poly(st, frac, cam):
    if st is None or frac <= 0: return None
    k = int(np.searchsorted(st['u'], min(1.0, frac), side='right'))
    if k < 2: return None
    c = to_screen(st['q'][:k], cam); off = st['nrm'][:k] * (st['w'][:k] / 2 * cam[2] ** 0.4)[:, None]   # a pen line grows slower than the zoom
    return [tuple(x) for x in np.concatenate([c + off, (c - off)[::-1]]) * SS]

def hatch(inside, box, spacing, seed, width=1.1, angle=45.0, jitter=0.5, trim=0.18):
    """left-handed hatching: straight strokes running down to the right, clipped to a region"""
    r = random.Random(seed); a = math.radians(angle); dx, dy = math.cos(a), math.sin(a); nx, ny = -dy, dx
    x0, y0, x1, y1 = box; cx, cy = (x0 + x1) / 2, (y0 + y1) / 2; R_ = math.hypot(x1 - x0, y1 - y0) / 2 + 4
    out = []; k = -R_
    while k <= R_:
        ox, oy = cx + nx * k, cy + ny * k; ts = np.arange(-R_, R_, 1.5)
        xs, ys = ox + dx * ts, oy + dy * ts; ins = inside(xs, ys)
        if ins.any():
            idx = np.flatnonzero(np.diff(np.concatenate([[0], ins.astype(int), [0]])))
            for s0, s1 in zip(idx[0::2], idx[1::2]):
                t0, t1 = ts[s0], ts[s1 - 1]; ln = t1 - t0
                if ln < 3: continue
                t0 += r.uniform(0, trim) * ln * 0.5; t1 -= r.uniform(0, trim) * ln * 0.5
                st = stroke([(ox + dx * t0, oy + dy * t0), (ox + dx * t1, oy + dy * t1)], width * r.uniform(0.8, 1.2), r.randrange(10 ** 6), jitter=jitter, taper=0.25)
                if st: out.append((k, st))
        k += spacing * r.uniform(0.85, 1.15)
    return out

# ---------------------------------------------------------------- the parchment
PARCH_FILE = '/home/claude/tegvid/parchment2-%dx%d.png' % (W * SS, SHEET_H * SS)
def value_noise(h, w, cells, rng):
    g = rng.random((cells + 3, int(cells * w / h) + 3)); im = Image.fromarray((g * 255).astype(np.uint8)).resize((w, h), Image.BICUBIC)
    return np.asarray(im, float) / 255.0
def make_parchment():
    """an old sheet: uneven tone, browner toward ragged edges, a few water stains with tide lines, fibres and foxing"""
    if os.path.exists(PARCH_FILE): return Image.open(PARCH_FILE).convert('RGB')
    rng = np.random.default_rng(5); h, w = SHEET_H * SS, W * SS
    n = sum(value_noise(h, w, c, rng) * a for c, a in ((3, 0.45), (8, 0.3), (24, 0.17), (70, 0.08)))
    n = ((n - n.mean()) / (n.std() + 1e-9)).astype(np.float32)
    shade = 1 + 0.036 * n                                                    # the sheet's mottling
    low = value_noise(h, w, 5, rng).astype(np.float32) - 0.5
    yy, xx = np.mgrid[0:h, 0:w].astype(np.float32)
    dist = np.minimum(np.minimum(xx, w - 1 - xx), np.minimum(yy, h - 1 - yy)) / w + 0.03 * low
    shade *= 1 - 0.15 * np.clip(1 - dist / 0.10, 0, 1) ** 1.8                # browned, uneven edges
    del xx, yy, dist, low
    shade = np.clip(shade, 0.5, 1.2)
    img = PARCH[None, None, :].astype(np.float32) * np.stack([shade ** 0.8, shade ** 1.05, shade ** 1.6], -1)   # darker turns browner
    fib = np.asarray(Image.fromarray((rng.random((h // 12, w)) * 255).astype(np.uint8)).resize((w, h), Image.BILINEAR), np.float32) / 255
    img *= (1 - 0.014 * (fib - 0.5))[..., None]
    out = Image.fromarray(np.clip(img, 0, 255).astype(np.uint8)); del img, shade, fib
    d = ImageDraw.Draw(out, 'RGBA')                                           # foxing: small rust spots
    for i in range(120):
        x, y = rng.uniform(0, w), rng.uniform(0, h); r = rng.uniform(1.5, 8) * SS * 0.5
        if 60 * SS < x < 300 * SS and 880 * SS < y < 1180 * SS: continue     # not in the close-up, where a spot would read as a blot
        d.ellipse([x - r, y - r, x + r, y + r], fill=(140, 92, 50, int(rng.uniform(8, 32))))
    out = out.filter(ImageFilter.GaussianBlur(1.2)); out.save(PARCH_FILE); return out
PARCHMENT = None
def background(cam):
    global PARCHMENT
    if PARCHMENT is None: PARCHMENT = make_parchment()
    cx, cy, z = cam; x0, y0 = (cx - W / 2 / z), (cy - H / 2 / z); x1, y1 = x0 + W / z, y0 + H / z
    box = [x0 * SS, y0 * SS, x1 * SS, y1 * SS]
    return PARCHMENT.resize((W, H), Image.Resampling.BOX if z < 1.5 else Image.Resampling.BICUBIC, box=box)

# ---------------------------------------------------------------- pen and wash: a thin brown wash in the shadows, red where the blood is
WASH_FILE = '/home/claude/tegvid/wash-%dx%d.png' % (W, SHEET_H)
WASH = None
def make_wash():
    if os.path.exists(WASH_FILE): return Image.open(WASH_FILE).convert('RGBA')
    from scipy.ndimage import gaussian_filter
    h, w = SHEET_H, W; y, x = np.mgrid[0:h, 0:w].astype(float) + 0.5
    rng = np.random.default_rng(11); mod = 0.75 + 0.5 * value_noise(h, w, 14, rng)          # a wash is never even
    s = (x - SX) / S_RC; sp = (x - SX) / S_RP; d = ((x - TX) * 0.55 + (y - TY) * 0.83) / T_RP
    layers = [
        (in_body(x, y) * 0.40 * np.clip((s + 0.15) / 1.15, 0, 1) ** 1.3 * (1 - 0.4 * np.clip((s - 0.86) / 0.14, 0, 1)), SEPIA),   # the wall, darker to the right, lifted by reflected light at the edge
        (in_shadow(x, y) * 0.26 * np.clip(1 - np.hypot((x - (SX + 96)) / 176, (y - (sY(0) + 10)) / 30), 0, 1) ** 0.5, SEPIA),
        (in_backwall(x, y) * 0.30, SEPIA),
        (in_pin_body(x, y) * 0.28 * np.clip((sp + 0.2) / 1.2, 0, 1) ** 1.3, SEPIA),
        (in_bar(x, y) * 0.25, SEPIA),
        (in_rimshade(x, y) * 0.22, SEPIA),
        ((np.hypot(x - TX, y - TY) < T_RP - 3) * 0.16 * np.clip(d, 0, 1) ** 1.5, SEPIA),
        (in_mouth_blood(x, y) * 0.24, SANG),
        (in_ring(x, y) * 0.20, SANG)]
    A = np.zeros((h, w)); C = np.zeros((h, w, 3))
    for a, col in layers:                                                                     # premultiplied, one over another
        a = np.clip(a * mod, 0, 1); C = C * (1 - a[..., None]) + np.array(col, float) * a[..., None]; A = A * (1 - a) + a
    A = gaussian_filter(A, 1.3); C = np.stack([gaussian_filter(C[..., k], 1.3) for k in range(3)], -1)
    rgb = np.where(A[..., None] > 1e-4, C / np.maximum(A, 1e-4)[..., None], 0)
    out = Image.fromarray(np.dstack([np.clip(rgb, 0, 255), np.clip(A * 255, 0, 255)]).astype(np.uint8), 'RGBA'); out.save(WASH_FILE); return out
def wash_view(cam, a):
    global WASH
    if WASH is None: WASH = make_wash()
    cx, cy, z = cam; x0, y0 = cx - W / 2 / z, cy - H / 2 / z
    im = WASH.resize((W, H), Image.Resampling.BOX if z < 1.01 else Image.Resampling.BICUBIC, box=[x0, y0, x0 + W / z, y0 + H / z])
    if a < 0.999: im.putalpha(im.getchannel('A').point(lambda p: int(p * a + 0.5)))
    return im

# ---------------------------------------------------------------- the side study: the cup as a solid, the pin hanging into it
SX, SYB, ELEV = 262.0, 640.0, math.radians(28)
KE, CE = math.sin(ELEV), math.cos(ELEV)
S_RC, S_RI, S_RP = 118.0, 105.0, 64.0
S_ZRIM, S_ZFILL, S_ZPT = 212.0, 188.0, 300.0
Z_B1, Z_B2 = S_ZRIM - 10.0, S_ZRIM - 32.0          # a graduated collar round the cup's wall, so its turn can be seen from the side
BRACKET_Y = 168.0
def sY(z): return SYB - z * CE
def sP(r, phi, z): return (SX + r * math.cos(phi), sY(z) + r * math.sin(phi) * KE)
def s_ell(r, z, a0, a1, n=80): return [sP(r, a0 + (a1 - a0) * i / n, z) for i in range(n + 1)]
def half(r, x): return np.sqrt(np.clip(r * r - (x - SX) ** 2, 0, None)) * KE
# ---------------------------------------------------------------- the top study: the cup from above
TX, TY, T_RO, T_RW, T_RP = 760.0, 330.0, 158.0, 139.0, 88.0
CUP_SWING = math.radians(24)
ROCK_T = 1.8
def phase(v): return math.sin(2 * math.pi * (v - T_START) / ROCK_T) if v >= T_START else 0.0
def cup_angle(v): return CUP_SWING * ramp(v, T_START - 0.2, T_START + 0.6) * phase(v)
def width_now(v): return M.A(test_min(v) * 60) if v >= T_START else 0.0
def clot(v): return width_now(v) / M.MA
def pin_angle(v): return cup_angle(v) * width_now(v) / 100.0
def tG(r, a): return (TX + r * math.cos(a), TY - r * math.sin(a))
SMALL = 31                                                              # the smallest words on the page: 31 px, 11.2 pt on a phone 390 pt wide
TURN_AT = (1054.0, 486.0)                                               # 'the turn, drawn / larger than life', right-aligned, first baseline
BLOOD_AT = (598.0, 488.0)                                              # the word's right end, on its baseline
BLOOD_LEADER = [(603.0, 478.0), (640.0, 452.0), (683.0, 414.0)]        # to the middle of the ring, lower left
# ---------------------------------------------------------------- the trace, angle-true
GX0, GX1, YM, YAX = 100.0, 990.0, 1020.0, 1236.0
FULL_MIN = 66.0
SXS = (GX1 - GX0) / (FULL_MIN * 60); SYS = SXS * 2 * M.K_ALPHA
def tx(t): return GX0 + t * SXS
def up(w): return YM - w / 2 * SYS
def dn(w): return YM + w / 2 * SYS

# ---------------------------------------------------------------- regions of the two studies, for hatching and for the wash
def in_cup(x, y):                     # the cup's silhouette on the side study
    return (np.abs(x - SX) < S_RC + 2) & (y > sY(S_ZRIM) - half(S_RC, x) - 2) & (y < sY(0) + half(S_RC, x) + 2)
def in_shadow(x, y):                  # the shadow it casts on the table, to the right; never over the cup itself
    return (((x - (SX + 96)) / 176) ** 2 + ((y - (sY(0) + 10)) / 30) ** 2 < 1) & ~in_cup(x, y)
def in_body(x, y):                    # the cup's outside wall, below the rim
    return (np.abs(x - SX) < S_RC - 1) & (y > sY(S_ZRIM) + half(S_RC, x) + 1) & (y < sY(0) + half(S_RC, x))
def in_pin_body(x, y):                # the pin's side, from its top face down to the front of the rim
    return (np.abs(x - SX) < S_RP - 1) & (y > sY(S_ZPT) + half(S_RP, x) + 1) & (y < sY(S_ZRIM) + half(S_RI, x) - 1)
def in_mouth_blood(x, y):
    yb = sY(S_ZFILL); ok = np.abs(x - SX) < S_RI - 2
    return ok & (y > yb - half(S_RI, x) + 2) & (y < sY(S_ZRIM) + half(S_RI, x) - 3) & (y < yb + half(S_RI, x)) & ~((np.abs(x - SX) < S_RP + 2) & (y > sY(S_ZPT)))
def in_backwall(x, y):
    ok = (np.abs(x - SX) < S_RI - 2) & (np.abs(x - SX) > S_RP + 3)
    return ok & (y > sY(S_ZRIM) - half(S_RI, x) + 2) & (y < sY(S_ZFILL) - half(S_RI, x) - 2)
def in_deepshade(x, y):
    return (x > SX + S_RC * 0.55) & (x < SX + S_RC - 1) & (y > sY(Z_B2) + half(S_RC, x) + 4) & (y < sY(0) + half(S_RC, x) - 4)
def in_bar(x, y): return (np.abs(x - SX) < 86) & (y > BRACKET_Y + 1) & (y < BRACKET_Y + 8)
def in_ring(x, y):
    r = np.hypot(x - TX, y - TY); return (r > T_RP + 3) & (r < T_RW - 3)
def in_rimshade(x, y):
    r = np.hypot(x - TX, y - TY); ang = np.arctan2(-(y - TY), x - TX)
    return (r > T_RW + 2) & (r < T_RO - 2) & (ang < -0.2) & (ang > -1.9)
def behind_pin(r, z, a0, a1, n):
    """a back arc of the side study with the stretch the pin hides left out: the pin stands in front of the far rim"""
    c = min(1.0, (S_RP + 1.5) / r); cut_l, cut_r = math.pi + math.acos(c), 2 * math.pi - math.acos(c)
    out = []
    if a0 < cut_l: out.append(s_ell(r, z, a0, min(a1, cut_l), n))
    if a1 > cut_r: out.append(s_ell(r, z, max(a0, cut_r), a1, n))
    return out

def build_static():
    """every ink stroke that does not move, with the time its drawing starts and how long it takes"""
    S = []; sd = [0]
    def add(pts, w, col, a, t0, dur, grp='ink', jit=0.7):
        sd[0] += 1; st = stroke(pts, w, sd[0], jit)
        if st: S.append((st, col, a, t0, dur, grp))
    H_ = []
    def hat(inside, box, sp, seed, w, col, a, t0, t1, grp, angle=45.0):
        H_.append((hatch(inside, box, sp, seed, w, angle), col, a, t0, t1, grp))
    # ---- side study
    # cast shadow on the table, to the right
    hat(in_shadow, (SX - 90, sY(0) - 30, SX + 280, sY(0) + 44), 6.0, 41, 1.0, SEPIA, 0.45, 1.5, 2.3, 'shadow')
    # the cup's silhouette: the outer rim in one stroke round the front, from one side of the pin to the other; the inner
    # rim's far half in two pieces either side of the pin; sides; base
    cO = math.acos(min(1.0, (S_RP + 1.5) / S_RC))
    add(s_ell(S_RC, S_ZRIM, -cO, math.pi + cO, 130), 2.6, INK, 0.95, 0.20, 0.55)
    for k, arc in enumerate(behind_pin(S_RI, S_ZRIM, math.pi, 2 * math.pi, 40)): add(arc, 1.6, INK, 0.85, 0.30 + 0.12 * k, 0.2)
    add(s_ell(S_RI, S_ZRIM, 0, math.pi, 80), 1.3, INK, 0.7, 0.34, 0.40)
    for sg in (-1, 1): add([(SX + sg * S_RC, sY(S_ZRIM)), (SX + sg * S_RC * 0.995, sY(0))], 2.6, INK, 0.95, 0.40, 0.40)
    add(s_ell(S_RC, 0, 0, math.pi, 90), 2.6, INK, 0.95, 0.55, 0.40)
    add([(SX + S_RC + 2.6, sY(S_ZRIM) + 10), (SX + S_RC + 2.0, sY(0) - 8)], 1.0, SEPIA, 0.45, 0.7, 0.35)        # a searching second line
    for z_ in (Z_B1, Z_B2): add(s_ell(S_RC, z_, 0.03, math.pi - 0.03, 80), 1.1, INK, 0.8, 0.62, 0.3)                # the collar's edges
    # the blood in the mouth: its surface, seen between the back wall and the front rim, hidden where the pin stands
    for k, arc in enumerate(behind_pin(S_RI, S_ZFILL, math.pi + 0.05, 2 * math.pi - 0.05, 35)): add(arc, 1.6, SANG, 0.9, 0.80 + 0.1 * k, 0.2)
    hat(in_mouth_blood, (SX - S_RI, sY(S_ZFILL) - 40, SX + S_RI, sY(S_ZRIM) + 40), 3.8, 42, 1.2, SANG, 0.85, 1.0, 2.0, 'blood')
    # the back wall inside the mouth, in shade
    hat(in_backwall, (SX - S_RI, sY(S_ZRIM) - 40, SX + S_RI, sY(S_ZFILL)), 4.5, 43, 0.9, SEPIA, 0.6, 0.9, 1.7, 'wall')
    # the cup's body: contour hatching, lines that follow the cylinder, closer toward the edges, heavier on the right
    rr = random.Random(9)
    for i in range(1, 40):
        th = math.pi * i / 40; x = SX + S_RC * math.cos(th); dens = abs(math.cos(th))
        if th > math.pi / 2 and dens < 0.62: continue                                  # the lit left side stays mostly clear
        if dens < 0.08: continue                                                        # and no seam down the middle
        yt = float(sY(Z_B2) + half(S_RC, np.array(x))) + 3 + rr.uniform(0, 26) * (1 - dens); yb = float(sY(0) + half(S_RC, np.array(x))) - 3 - rr.uniform(0, 18) * (1 - dens)
        bow = (x - SX) / S_RC * 3.0
        add([(x, yt), (x + bow, (yt + yb) / 2), (x + 0.4, yb)], 0.8 + 0.6 * dens, SEPIA, 0.5 + 0.35 * dens, 1.2 + 0.012 * i, 0.35, 'body')
    hat(in_deepshade, (SX + S_RC * 0.5, sY(S_ZRIM), SX + S_RC, sY(0) + 30), 5.0, 44, 0.9, SEPIA, 0.55, 1.7, 2.3, 'body2')
    # the pin, hanging into the blood: its sides down to the front rim, its cap, its shade
    for sg in (-1, 1):
        x = SX + sg * S_RP; yb = sY(S_ZRIM) + float(half(S_RI, np.array(x)))
        add([(x, sY(S_ZPT)), (x, yb - 1)], 2.2, INK, 0.95, 0.95, 0.35)
    add(s_ell(S_RP, S_ZPT, 0, 2 * math.pi, 90), 2.0, INK, 0.9, 1.05, 0.35)
    for i in range(1, 16):
        th = math.pi / 2 * i / 16; x = SX + S_RP * math.cos(th)
        if math.cos(th) < 0.3: continue
        yt = sY(S_ZPT) + float(half(S_RP, np.array(x))) + 2; yb = sY(S_ZRIM) + float(half(S_RI, np.array(x))) - 3
        add([(x, yt), (x, yb)], 0.8 + 0.6 * math.cos(th), SEPIA, 0.6, 1.3 + 0.02 * i, 0.3, 'pin')
    # the wire and the bar it hangs from
    add([(SX, sY(S_ZPT)), (SX, BRACKET_Y + 8)], 1.4, INK, 0.9, 1.25, 0.35)
    add([(SX - 88, BRACKET_Y), (SX + 88, BRACKET_Y)], 3.0, INK, 0.9, 1.35, 0.3)
    add([(SX - 88, BRACKET_Y + 9), (SX + 88, BRACKET_Y + 9)], 1.2, INK, 0.7, 1.4, 0.3)
    for sg in (-1, 1): add([(SX + sg * 88, BRACKET_Y - 3), (SX + sg * 88, BRACKET_Y + 12)], 2.0, INK, 0.85, 1.5, 0.15)
    add([(SX - 7, BRACKET_Y + 9), (SX - 7, BRACKET_Y + 20), (SX + 7, BRACKET_Y + 20), (SX + 7, BRACKET_Y + 9)], 1.3, INK, 0.85, 1.55, 0.15)
    hat(in_bar, (SX - 90, BRACKET_Y, SX + 90, BRACKET_Y + 10), 3.0, 45, 0.7, SEPIA, 0.6, 1.5, 1.8, 'bar')
    # ---- top study: rim, wall, pin face, shade on the rim and the face
    add([tG(T_RO, 2 * math.pi * i / 140) for i in range(141)], 2.6, INK, 0.95, 0.55, 0.55)
    add([tG(T_RW, 2 * math.pi * i / 140) for i in range(141)], 1.8, INK, 0.9, 0.70, 0.50)
    add([tG(T_RP, 2 * math.pi * i / 110) for i in range(111)], 2.2, INK, 0.95, 0.90, 0.45)
    add([tG(T_RO + 3.2, 2 * math.pi * i / 120 + 0.4) for i in range(52)], 1.0, SEPIA, 0.45, 0.85, 0.4)
    hat(in_ring, (TX - T_RW, TY - T_RW, TX + T_RW, TY + T_RW), 4.4, 21, 1.25, SANG, 0.78, 1.1, 2.5, 'ring')
    for i in range(10):                                                   # curved shade on the pin face, lower right
        r = T_RP - 6 - i * 5.5
        if r < 20: break
        arc = [tG(r, -1.35 + 1.1 * j / 20 - 0.1 * i / 10) for j in range(21)]
        add(arc, 0.9, SEPIA, 0.5, 1.5 + 0.03 * i, 0.3, 'face')
    hat(in_rimshade, (TX - T_RO, TY - T_RO, TX + T_RO, TY + T_RO), 3.6, 46, 0.8, SEPIA, 0.55, 1.6, 2.2, 'rim')
    # ---- the trace's ground: centre line and time axis with ticks
    add([(GX0 - 8, YM), (GX1 + 6, YM)], 1.0, SEPIA, 0.55, 2.2, 0.8)
    add([(GX0, YAX), (GX1, YAX)], 1.6, INK, 0.85, 2.3, 0.8)
    for m in range(0, 67, 5):
        x = tx(m * 60); add([(x, YAX), (x, YAX + (9 if m % 10 == 0 else 5))], 1.3, INK, 0.8, 2.4 + m * 0.008, 0.1)
    return S, H_
STATIC, HATCH = build_static()

# the trace's red chalk hatching, laid once over the finished shape and uncovered as the pen passes
def in_spindle(x, y):
    t = (x - GX0) / SXS; w = np.array([M.A(tt) for tt in np.clip(t, 0, FULL_MIN * 60)]) if np.ndim(t) else M.A(t)
    return (x > GX0) & (x < GX1) & (np.abs(y - YM) < w / 2 * SYS - 2.0)
TRACE_HATCH = hatch(in_spindle, (GX0, up(M.MA) - 4, GX1, dn(M.MA) + 4), 1.9, 31, 1.1)

def envelope(t_now, n=260):
    ts = np.linspace(0, t_now, n); U = [(tx(t), up(M.A(t))) for t in ts]; D = [(tx(t), dn(M.A(t))) for t in ts]
    return U, D

UNDER = None
def underdrawing():
    """the whole page first set down in red chalk: contours, the shading, and the finished trace"""
    global UNDER
    if UNDER is None:
        out = [st for st, col, a, t0, dur, grp in STATIC]
        for strokes, col, a, t0, t1, grp in HATCH: out += [st for k, st in strokes[::2]]
        U, D = envelope(FULL_MIN * 60, 200)
        out += [stroke(U, 1.8, 901, 1.0), stroke(D, 1.8, 902, 1.0)]
        out += [st for k, st in TRACE_HATCH[::2]]
        out += [stroke([tG(T_RW + 4, k * math.pi / 20), tG(T_RO - 4, k * math.pi / 20)], 1.2, 500 + k, 0.3) for k in range(40)]
        UNDER = [st for st in out if st is not None]
    return UNDER

QUEUE = []
def draw_group(layer_img, polys, col, alpha):
    """queue polygons for one pass on a single layer: later strokes lie over earlier ones, as ink does"""
    if polys: QUEUE.append((polys, col + (int(255 * max(0.0, min(1.0, alpha))),)))
def flush(size):
    lay = Image.new('RGBA', size, (0, 0, 0, 0)); d = ImageDraw.Draw(lay)
    for polys, rgba in QUEUE:
        for p in polys:
            if p: d.polygon(p, fill=rgba)
    QUEUE.clear(); return lay.resize((W, H), Image.Resampling.BOX)
STATIC_CACHE = {}
STATIC_DONE = 4.6                                   # after this the underdrawing is gone and every fixed stroke is down
def static_layer(v, cam):
    key = (round(cam[0], 3), round(cam[1], 3), round(cam[2], 4))
    if v >= STATIC_DONE and key in STATIC_CACHE: return STATIC_CACHE[key]
    a_under = 0.6 * (1 - ramp(v, 2.4, 4.4))         # the red chalk underdrawing, fading as the ink goes over it
    if a_under > 0: draw_group(None, [stroke_poly(st, 1, cam) for st in underdrawing()], CHALK, a_under)
    groups = {}
    for st, col, a, t0, dur, grp in STATIC:
        f = (v - t0) / dur
        if f > 0: groups.setdefault((grp, col, a), []).append(stroke_poly(st, f, cam))
    for strokes, col, a, t0, t1, grp in HATCH:
        n = len(strokes)
        for i, (k, st) in enumerate(strokes):
            ts = t0 + (t1 - t0) * i / max(1, n); f = (v - ts) / 0.12
            if f > 0: groups.setdefault((grp, col, a), []).append(stroke_poly(st, f, cam))
    order = sorted(groups.items(), key=lambda kv: (kv[0][1] == INK, kv[0][2]))   # shading first, the pen's contours last
    for (grp, col, a), polys in order: draw_group(None, polys, col, a)
    lay = flush((W * SS, H * SS))
    if v >= STATIC_DONE:
        if len(STATIC_CACHE) > 6: STATIC_CACHE.clear()
        STATIC_CACHE[key] = lay
    return lay

COVER = [False]; _STILL = {}
def cover(write=True):
    """the finished page: both studies inked and washed, the whole trace with its five names, no notes. The first frame"""
    if ('cover', write) in _STILL: return _STILL[('cover', write)]
    COVER[0] = True
    try:
        v, cam = 36.5, CAM_FULL; out = background(cam).convert('RGBA'); out.alpha_composite(wash_view(cam, 1.0))
        out.alpha_composite(static_layer(50.0, cam)); draw_moving(None, v, cam); out.alpha_composite(flush((W * SS, H * SS)))
        if write: write_text(out, v, cam)
        img = out.convert('RGB')
    finally: COVER[0] = False
    _STILL[('cover', write)] = img; return img
def frame(t, write=True):
    """the video at t s: the finished page, held, dissolving to the red chalk sketch, then the story from its start"""
    if t >= T_COVER: return story_frame(t - T_COVER, write)
    a = 1 - ramp(t, T_HOLD, T_COVER); c = cover(write)
    if a >= 0.999: return c
    if ('start', write) not in _STILL: _STILL[('start', write)] = story_frame(0.0, write)
    return Image.blend(_STILL[('start', write)], c, a)
def story_frame(v, write=True):
    cam = camera(v); out = background(cam).convert('RGBA')
    a_wash = ramp(v, 1.7, 3.2)                                           # the wash goes on once the pen has set the forms down
    if a_wash > 0: out.alpha_composite(wash_view(cam, a_wash))
    out.alpha_composite(static_layer(v, cam))
    draw_moving(None, v, cam); out.alpha_composite(flush((W * SS, H * SS)))
    if write: write_text(out, v, cam)
    return out.convert('RGB')

def draw_moving(ink, v, cam):
    th_c, th_p, s = (0.0, 0.0, clot(v)) if COVER[0] else (cup_angle(v), pin_angle(v), clot(v))
    polys_ink, polys_sep, polys_sang, polys_fib = [], [], [], []
    a_top = ramp(v, 0.6, 1.2)
    # the leader from the word 'blood' to the ring
    a_bl = 1.0 if COVER[0] else ramp(v, 1.6, 2.2) * (1 - ramp(v, 7.9, 8.6))
    if a_bl > 0.01: draw_group(None, [stroke_poly(stroke(BLOOD_LEADER, 1.1, 604, 0.4, 0.5), ramp(v, 1.8, 2.3), cam)], SEPIA, 0.85 * a_bl)
    # ticks on the rim ride the cup's turn
    for k in range(40):
        a = th_c + k * math.pi / 20; st = stroke([tG(T_RW + 4, a), tG(T_RO - 4, a)], 1.3, 500 + k, 0.2, 0.5)
        polys_ink.append(stroke_poly(st, ramp(v, 0.9 + k * 0.012, 1.2 + k * 0.012), cam))
    # the notch on the pin face and the sweep it covers
    st = stroke([tG(10, th_p), tG(T_RP - 6, th_p)], 3.0, 600, 0.3, 0.6); polys_ink.append(stroke_poly(st, ramp(v, 1.2, 1.5), cam))
    span = CUP_SWING * width_now(v) / 100.0
    if span > 0.02:
        arc = [tG(T_RP - 16, -span + 2 * span * i / 24) for i in range(25)]
        polys_sep.append(stroke_poly(stroke(arc, 1.4, 601, 0.2, 0.4), 1, cam))
    # the cup's turn: a curved arrow outside the rim
    if v >= T_START - 0.4:
        arc = [tG(T_RO + 22, -CUP_SWING + 2 * CUP_SWING * i / 30) for i in range(31)]
        polys_ink.append(stroke_poly(stroke(arc, 1.8, 602, 0.3, 0.5), ramp(v, T_START - 0.4, T_START + 0.2), cam))
        for e, nx in ((arc[0], arc[1]), (arc[-1], arc[-2])):
            ang = math.atan2(e[1] - nx[1], e[0] - nx[0])
            for sgn in (-1, 1):
                q = (e[0] - 12 * math.cos(ang + sgn * 0.45), e[1] - 12 * math.sin(ang + sgn * 0.45))
                polys_ink.append(stroke_poly(stroke([q, e], 1.6, 603 + sgn, 0.1, 0.4), ramp(v, T_START, T_START + 0.3), cam))
        arc = [sP(S_RC + 26, math.pi / 2 - 0.55 + 1.1 * i / 30, 0) for i in range(31)]          # and under the side study
        polys_ink.append(stroke_poly(stroke(arc, 1.8, 605, 0.3, 0.5), ramp(v, T_START - 0.4, T_START + 0.2), cam))
        for e, nx in ((arc[0], arc[1]), (arc[-1], arc[-2])):
            ang = math.atan2(e[1] - nx[1], e[0] - nx[0])
            for sgn in (-1, 1):
                q = (e[0] - 12 * math.cos(ang + sgn * 0.45), e[1] - 12 * math.sin(ang + sgn * 0.45))
                polys_ink.append(stroke_poly(stroke([q, e], 1.6, 606 + sgn, 0.1, 0.4), ramp(v, T_START, T_START + 0.3), cam))
    # the side study turns too. Seen from the front the same turn runs the other way round, so its angles are negated.
    # The collar's ticks ride the cup's turn; a notch on the pin's top face follows once the clot grips; a twist mark on
    # the wire shows it taking up the turn
    for k in range(36):
        ph = k * math.pi / 18 - th_c
        if math.sin(ph) < 0.08: continue                                   # only the front of the wall is seen
        x = SX + S_RC * math.cos(ph); zb = Z_B2 + 2 if k % 3 == 0 else (Z_B1 + Z_B2) / 2
        y1, y2 = sY(Z_B1 - 2) + S_RC * math.sin(ph) * KE, sY(zb) + S_RC * math.sin(ph) * KE
        polys_ink.append(stroke_poly(stroke([(x, y1), (x, y2)], 1.2, 540 + k, 0.1, 0.5), ramp(v, 0.95 + k * 0.01, 1.25 + k * 0.01), cam))
    ps = math.pi / 2 + 0.7 - th_p
    polys_ink.append(stroke_poly(stroke([sP(10, ps, S_ZPT), sP(S_RP - 6, ps, S_ZPT)], 2.4, 610, 0.2, 0.6), ramp(v, 1.25, 1.55), cam))
    a_tw = 1.0 if COVER[0] else smooth((width_now(v) - 2.0) / 10.0)
    if a_tw > 0.01:
        arc = [(SX + 17 * math.cos(p), 292.0 + 5.5 * math.sin(p)) for p in np.linspace(0.4, math.pi - 0.4, 18)]
        tw = [stroke_poly(stroke(arc, 1.3, 611, 0.1, 0.5), 1, cam)]
        for e, nx in ((arc[0], arc[1]), (arc[-1], arc[-2])):
            ang = math.atan2(e[1] - nx[1], e[0] - nx[0])
            for sgn in (-1, 1):
                q = (e[0] - 7 * math.cos(ang + sgn * 0.5), e[1] - 7 * math.sin(ang + sgn * 0.5))
                tw.append(stroke_poly(stroke([q, e], 1.1, 612 + sgn, 0.05, 0.4), 1, cam))
        draw_group(None, tw, INK, 0.85 * a_tw)
    # fibrin in the ring and in the cut: fine ink threads, more as the clot firms
    rng = random.Random(77); sv = s ** 0.4 * 1.1 if s > 0 else 0.0
    for i in range(64):
        a = 2 * math.pi * (i + rng.uniform(-0.35, 0.35)) / 64; dd = rng.uniform(-0.2, 0.2); u = rng.random() * 0.9; bow = rng.uniform(-5, 5)
        al = max(0.0, min(1.0, (sv - u) / 0.07))
        if al > 0.02:
            p1, p2 = tG(T_RP + 2, a + th_p), tG(T_RW - 2, a + dd + th_c)
            mx, my = (p1[0] + p2[0]) / 2 - (p2[1] - p1[1]) * bow / 60, (p1[1] + p2[1]) / 2 + (p2[0] - p1[0]) * bow / 60
            polys_fib.append(stroke_poly(stroke([p1, (mx, my), p2], 0.9, 700 + i, 0.3, 0.4), al, cam))
    # the trace: envelope in red chalk ink, the pen at its tip, the hatching uncovered behind it
    if v >= T_START:
        t_now = test_min(v) * 60; U, D = envelope(t_now)
        for pts, sd in ((U, 901), (D, 902)):
            st = stroke(pts, 2.2, sd, 0.5, 0.15); polys_ink.append(stroke_poly(st, 1, cam))
        x_now = tx(t_now); a_fine = min(1.0, max(0.0, (cam[2] - 1.0) / 1.2))
        fine = []
        for i, (k, st) in enumerate(TRACE_HATCH):
            if i % 3 and a_fine <= 0.02: continue
            if st['q'][:, 0].min() < x_now - 1:
                keep = st['q'][:, 0] <= x_now
                if keep.all(): p = stroke_poly(st, 1, cam)
                else:
                    kk = int(np.argmax(~keep)) if keep[0] else 0
                    p = stroke_poly(st, st['u'][max(1, kk - 1)], cam) if keep[0] else None
                (polys_sang if i % 3 == 0 else fine).append(p)
    draw_group(ink, polys_sep, SEPIA, 0.7); draw_group(ink, polys_sang, SANG, 0.8)
    if v >= T_START and a_fine > 0.02: draw_group(ink, fine, SANG, 0.8 * a_fine)
    draw_group(ink, polys_ink, INK, 0.92); draw_group(ink, polys_fib, INK, 0.75)
    marks(ink, v, cam)
    if T_START <= v < T_CLOSE and not COVER[0]:                         # the pen
        w = width_now(v); t_now = test_min(v) * 60; p = to_screen([(tx(t_now), YM - w / 2 * SYS * phase(v))], cam)[0] * SS; r = 4.5 * cam[2] ** 0.5 * SS
        draw_group(None, [[(p[0] + r * math.cos(2 * math.pi * k / 24), p[1] + r * math.sin(2 * math.pi * k / 24)) for k in range(24)]], INK, 0.92)

MARK_TXT = []
YB = YM + 80                                  # the close-up's own time ruler, just under the trace
MS = 42.0 / CAM_DETAIL[2]                     # words in the close-up: 42 px on screen
def marks(ink, v, cam):
    """R, K, 2 and 20 mm, alpha, MA and LY30: ink on the sheet, with the words queued for the text pass"""
    MARK_TXT.clear(); tm = test_min(v); R, K = M.R_S, M.K_S; polys = []
    def ln(pts, w, a, sd):
        if a > 0.01: polys.append((stroke_poly(stroke(pts, w, sd, 0.25, 0.3), 1, cam), a))
    out = 0.0 if COVER[0] else 1 - ramp(v, 27.0, 27.5)
    aR = ramp(v, 16.6, 17.1) * out if tm >= 6.0 else 0.0
    aK = ramp(v, 20.3, 20.8) * out if tm >= 8.5 else 0.0
    aK20 = aK * (1 - ramp(v, 23.2, 23.6)); aA = ramp(v, 23.6, 24.2) * out
    xR, xK = tx(R), tx(R + K)
    if aR > 0:                                                            # R: from the start of the run to 2 mm, on a ruler under the trace
        ln([(xR, dn(2) + 2), (xR, YB + 4)], 0.5, aR * 0.7, 1001)
        ln([(GX0, YB), (xR - 1, YB)], 1.1, aR, 1002); ln([(GX0, YB - 4), (GX0, YB + 4)], 0.7, aR, 1016)
        MARK_TXT.append(('R', '6 min', ((GX0 + xR) / 2, YB + 11), aR, MS, 'c'))
        ln([(xR - 7, up(2)), (xR - 7, dn(2))], 0.6, aR, 1003)
        MARK_TXT.append(('', '2 mm', (xR - 10, up(2) - 7), aR, MS, 'r'))
    if aK > 0:
        ln([(xK, dn(20) + 2), (xK, YB + 4)], 0.5, aK * 0.7, 1004)
        ln([(xR + 1, YB), (xK - 1, YB)], 1.1, aK * 0.8, 1005)
        MARK_TXT.append(('K', '2.5 min', ((xR + xK) / 2 + 13, YB + 11), aK, MS, 'c'))
    if aK20 > 0:
        x = xK + 6; ln([(x, up(20) + 2), (x, dn(20) - 2)], 0.6, aK20, 1006)
        for yy, sgn in ((up(20), 1), (dn(20), -1)):
            ln([(x - 2.2, yy + sgn * 4), (x, yy)], 0.6, aK20, 1007); ln([(x + 2.2, yy + sgn * 4), (x, yy)], 0.6, aK20, 1008)
        MARK_TXT.append(('', '20 mm', (x + 5, YM - 10), aK20, MS, 'l'))
    if aA > 0:
        x2, y2 = xR, up(2); ang = math.atan(M.dA(R) / 2 * SYS / SXS)
        ln([(x2 - 12 * math.cos(ang), y2 + 12 * math.sin(ang)), (x2 + 64 * math.cos(ang), y2 - 64 * math.sin(ang))], 0.7, aA, 1009)
        ln([(x2, y2), (x2 + 50, y2)], 0.5, aA, 1010)
        rr = 26; ln([(x2 + rr * math.cos(-ang * i / 20), y2 + rr * math.sin(-ang * i / 20)) for i in range(21)], 0.7, aA, 1011)
        xl = max(x2 + rr * math.cos(ang / 2) + 5, tx(tm * 60) + 9)
        MARK_TXT.append(('', 'alpha %d°' % round(M.measured()['alpha']), (xl, y2 - rr * math.sin(ang / 2) - 1), aA, MS, 'l'))
    fade_close = 1 - ramp(v, T_CLOSE, T_CLOSE + 0.6)
    a_num = 0.0 if COVER[0] else 1 - ramp(v, T_CLOSE + 0.1, T_CLOSE + 0.6)     # at the close the numbers leave the drawing for the table
    xM = tx(M.T_MA); aM = 1.0 if COVER[0] else ramp(v, 30.6, 31.1)
    if aM > 0:
        y1, y2 = up(M.MA), dn(M.MA); ln([(xM, y1 + 5), (xM, y2 - 5)], 1.2, aM, 1012)
        for yy, sgn in ((y1, 1), (y2, -1)):
            ln([(xM - 5, yy + sgn * 11), (xM, yy + sgn * 1)], 1.1, aM, 1013); ln([(xM + 5, yy + sgn * 11), (xM, yy + sgn * 1)], 1.1, aM, 1014)
        if a_num > 0: MARK_TXT.append(('MA', '64 mm', (xM - 12, up(M.MA) - 24), aM * a_num, 30, 'r'))   # written above the trace, in the open
    aL = 1.0 if COVER[0] else ramp(v, 34.6, 35.1)
    if aL > 0:
        x1, x2 = xM, tx(M.T_MA + 1800); yb = up(M.MA) - 14
        ln([(x1, yb + 8), (x1, yb), (x2, yb), (x2, yb + 8)], 1.2, aL, 1015)
        if a_num > 0: MARK_TXT.append(('LY30', '0%', ((x1 + x2) / 2, yb - 20), aL * a_num, 30, 'c'))
    a_fin = 1.0 if COVER[0] else ramp(v, T_CLOSE + 0.8, T_CLOSE + 1.4)
    if a_fin > 0: final_marks(a_fin, ln)
    by = {}
    for p, a in polys: by.setdefault(round(a, 2), []).append(p)
    for a, ps in by.items(): draw_group(ink, ps, INK, 0.92 * a)

YF = YM + 90                                  # the finished trace's ruler for R and K, under the start of the rise
def final_marks(a, ln):
    """the five names on the finished trace, where each is read; the numbers stay in the table"""
    xR, xK = tx(M.R_S), tx(M.R_S + M.K_S)
    ln([(xR, dn(2) + 2), (xR, YF + 4)], 0.5, a * 0.7, 1101); ln([(xK, dn(20) + 2), (xK, YF + 4)], 0.5, a * 0.7, 1102)
    ln([(GX0, YF), (xR - 1, YF)], 1.1, a, 1103); ln([(GX0, YF - 4), (GX0, YF + 4)], 0.7, a, 1104)
    ln([(xR + 1, YF), (xK - 1, YF)], 1.1, a * 0.8, 1105); ln([(xK, YF - 4), (xK, YF + 4)], 0.7, a, 1106)
    MARK_TXT.append(('R', '', ((GX0 + xR) / 2, YF + 20), a, 30, 'c'))
    MARK_TXT.append(('K', '', ((xR + xK) / 2, YF + 20), a, 30, 'c'))
    x2, y2 = xR, up(2); ang = math.atan(M.dA(M.R_S) / 2 * SYS / SXS)          # alpha: the tangent at 2 mm, the level, the arc
    ln([(x2 - 10 * math.cos(ang), y2 + 10 * math.sin(ang)), (x2 + 80 * math.cos(ang), y2 - 80 * math.sin(ang))], 0.8, a, 1107)
    ln([(x2, y2), (x2 + 56, y2)], 0.6, a, 1108)
    rr = 30; ln([(x2 + rr * math.cos(-ang * i / 20), y2 + rr * math.sin(-ang * i / 20)) for i in range(21)], 0.8, a, 1109)
    MARK_TXT.append(('alpha', '', (x2 + 38, y2 - 26), a, 30, 'l', 'halo'))    # inside the angle: the hatching is cleared round the word
    xM = tx(M.T_MA); MARK_TXT.append(('MA', '', (xM - 12, up(M.MA) - 24), a, 30, 'r'))
    x1, x3 = xM, tx(M.T_MA + 1800); MARK_TXT.append(('LY30', '', ((x1 + x3) / 2, up(M.MA) - 34), a, 30, 'c'))

# ---------------------------------------------------------------- the hand: notes written word by word
PAGE_NOTE = (560.0, 600.0, 440.0)     # x, y, width of the note block under the top study, sheet px
DETAIL_NOTE = (96.0, 945.0, 80.0)
FOOT_NOTE = (70.0, 1345.0, 900.0)
LAYZ = 4                              # notes are measured at four times their sheet size
WORD_GAP = 1.2                                     # italic f's reach into the space: a wider gap between words keeps them apart
def line_len(words, f): return sum(f.getlength(w_) for w_ in words) + (len(words) - 1) * f.getlength(' ') * WORD_GAP
def wrap(text, f, width):
    lines, cur = [], []
    for w_ in text.split(' '):                     # plain spaces only: a number keeps its unit
        if not cur or line_len(cur + [w_], f) <= width: cur = cur + [w_]
        else: lines.append(' '.join(cur)); cur = [w_]
    return lines + [' '.join(cur)]
def write_text(out, v, cam):
    d = ImageDraw.Draw(out); z = cam[2]
    def put(xy_sheet, s, kind, size_sheet, col, a, anchor='l', base=False):
        if a <= 0.01: return
        f = font(kind, size_sheet * z); x, y = to_screen([xy_sheet], cam)[0]
        d.text((x, y), s, font=f, fill=col + (int(255 * a),), anchor={'l': 'l', 'r': 'r', 'c': 'm'}[anchor] + ('s' if base else 'm'))
    # the title, in the hand, from the first frame
    put((70, 76), 'How a TEG draws its trace', 'it', 54, INK, 1.0)
    # notes
    for a0, b0, s, where in NOTES:
        if v < a0 - 0.05 or COVER[0]: continue
        x0, y0, wd = {'page': PAGE_NOTE, 'detail': DETAIL_NOTE, 'foot': FOOT_NOTE}[where]
        size = {'page': 38, 'detail': MS, 'foot': 36}[where]; LZ = CAM_DETAIL[2] if where == 'detail' else LAYZ
        fade = 1.0 if b0 >= T_END else 1 - ramp(v, b0 - 0.25, b0)
        if where == 'detail': fade = min(fade, 1 - ramp(v, 27.0, 27.5)) if v > b0 - 0.3 else fade
        if fade <= 0: continue
        s = s.replace('2 to 20 mm', '2\u00a0to\u00a020\u00a0mm').replace('2 mm', '2\u00a0mm').replace('20 mm', '20\u00a0mm').replace('30 minutes', '30\u00a0minutes'); f0 = font('it', size * LZ); lines = [ln_ for para in s.split('\n') for ln_ in wrap(para, f0, wd * LZ)]; words_done = 0; nwords = len(s.split(' '))
        speed = 9.0                                                        # words a second, the pen writing
        yy = y0
        for ln_ in lines:
            xx = x0
            for w_ in ln_.split(' '):
                ta = a0 + 0.05 + words_done / speed; al = ramp(v, ta, ta + 0.14) * fade
                put((xx, yy), w_, 'it', size, INK, al, 'l', True); xx += (f0.getlength(w_) + f0.getlength(' ') * WORD_GAP) / LZ; words_done += 1
            yy += size * 1.38
    # labels on the top study
    pg = 1.0 if v < 15.0 or v > 28.5 else (1 - ramp(v, 15.0, 15.4)) if v < 21.0 else ramp(v, 28.0, 28.5)   # the page's labels step aside for the close-up
    a_l = ramp(v, 1.6, 2.2) * pg
    put((TX, TY - T_RO - 22), 'the same cup, from above', 'it', SMALL, SEPIA, a_l * (1 - ramp(v, T_CLOSE, T_CLOSE + 0.5)), 'c', True)
    put((SX, sY(0) + 118), 'the cup and its pin, from the side', 'it', SMALL, SEPIA, ramp(v, 1.4, 2.0) * pg * (1 - ramp(v, T_CLOSE, T_CLOSE + 0.5)), 'c', True)
    put((TX - 38, TY + 2), 'pin', 'it', SMALL, SEPIA, a_l)
    put(BLOOD_AT, 'blood', 'it', SMALL, SEPIA, 1.0 if COVER[0] else a_l * (1 - ramp(v, 7.9, 8.6)), 'r', True)
    a_turn = ramp(v, T_START, T_START + 0.5) * (1 - ramp(v, T_CLOSE, T_CLOSE + 0.5)) * pg
    put(TURN_AT, 'the turn, drawn', 'it', SMALL, SEPIA, a_turn, 'r', True)                 # found clear of the dial and its arrow at this size
    put((TURN_AT[0], TURN_AT[1] + 34), 'larger than life', 'it', SMALL, SEPIA, a_turn, 'r', True)
    # the clock and the axis numbers
    if T_START <= v and not COVER[0]:
        put((GX0, 818), '%d min' % int(test_min(v) + 1e-6), 'it', 30, SEPIA, (1 - ramp(v, T_CLOSE, T_CLOSE + 0.5)) * (1 - ramp(v, 15.0, 15.4) + ramp(v, 28.0, 28.5) if 15.0 <= v <= 28.5 else 1.0) if not (15.4 < v < 28.0) else 0.0)
    a_ax = ramp(v, 2.6, 3.2) * (1 - ramp(v, 15.0, 15.4) + ramp(v, 28.2, 28.7)) if v < 15.0 or v > 28.2 else 0.0
    for m in range(0, 67, 10):                                             # 60 centred on its tick like the others, with min after it
        if m < 60: put((tx(m * 60), YAX + 25), str(m), 'rm', SMALL, SEPIA, a_ax, 'c')
        else: put((tx(m * 60) - font('rm', SMALL).getlength('60') / 2, YAX + 25), '60 min', 'rm', SMALL, SEPIA, a_ax, 'l')
    for item in MARK_TXT:
        p, val, (x, y), a, size, anc = item[:6]; halo = len(item) > 6
        if p:
            f1, f2 = font('rm', size * z), font('it', size * z); wp = f1.getlength(p); wv = f2.getlength(' ' + val) if val else 0.0
            X, Y = to_screen([(x, y)], cam)[0]; X0 = X - (wp + wv) / 2 if anc == 'c' else X - (wp + wv) if anc == 'r' else X
            if halo and a > 0.01:                                          # clear the hatching round the word, softly
                m = Image.new('L', (W, H), 0); ImageDraw.Draw(m).text((X0, Y), p, font=f1, fill=255, anchor='lm', stroke_width=max(2, int(round(4 * z))), stroke_fill=255)
                m = m.filter(ImageFilter.GaussianBlur(2.2 * z)).point(lambda q: int(min(255, q * 1.5) * 0.94 * a))
                paper = Image.new('RGBA', (W, H), HALO + (255,)); paper.putalpha(m); out.alpha_composite(paper); d = ImageDraw.Draw(out)
            d.text((X0, Y), p, font=f1, fill=SANG + (int(255 * a),), anchor='lm')
            if val: d.text((X0 + wp, Y), ' ' + val, font=f2, fill=INK + (int(255 * a),), anchor='lm')
        else: put((x, y), val, 'it', size, INK, a, anc)
    close_page(d, v, cam, put)
    a_q = ramp(v, T_CLOSE + 1.6, T_CLOSE + 2.2)
    if a_q > 0:
        for i, (name, url) in enumerate(QRS):
            x0, y0 = QR_X, QR_Y0 + i * QR_DY; q = qr_tile(url, QR_MOD).convert('RGBA'); px = q.width
            X, Y = to_screen([(x0, y0)], cam)[0]; q.putalpha(int(255 * a_q)); out.alpha_composite(q, (int(round(X)), int(round(Y))))
            put((x0 + px / 2, y0 + px + 30), name, 'it', SMALL, INK, a_q, 'c', True)
    d.rectangle([0, H - FOOT, W, H], fill=BAND + (255,)); d.rectangle([0, H - FOOT, W, H - FOOT + 1], fill=RULEC + (255,))
    f = font('rm', 30); tw = f.getlength(CREDIT); bb = f.getbbox(CREDIT)
    d.text(((W - tw) / 2, H - FOOT / 2 - (bb[1] + bb[3]) / 2), CREDIT, font=f, fill=INK + (255,))

ROWS = [('R', '6 min', '4–8 min'), ('K', '2.5 min', '1–4 min'), ('alpha', '63°', '47–74°'), ('MA', '64 mm', '55–73 mm'), ('LY30', '0%', 'over 7.5% means lysis')]
QRS = [('Srivastava 2013', 'https://doi.org/10.1093/bjaceaccp/mks049'), ('Wells 2022', 'https://doi.org/10.1016/j.bjae.2022.07.003')]
def close_page(d, v, cam, put):
    a = ramp(v, T_CLOSE + 0.9, T_CLOSE + 1.5)
    if a <= 0: return
    m = M.measured(); assert round(m['R_min']) == 6 and round(m['K_min'], 1) == 2.5 and round(m['alpha']) == 63 and round(m['MA']) == 64 and round(m['LY30']) == 0
    y0 = 1490
    put((300, y0), 'this trace', 'it', 30, SEPIA, a); put((500, y0), 'normal, kaolin TEG', 'it', 30, SEPIA, a)
    for i, (p, x1, x2) in enumerate(ROWS):
        y = y0 + 60 + i * 60; aa = a * ramp(v, T_CLOSE + 1.0 + i * 0.12, T_CLOSE + 1.4 + i * 0.12)
        put((70, y), p, 'rm', 40, SANG, aa); put((300, y), x1, 'it', 38, INK, aa); put((500, y), x2, 'it', 38, INK, aa)
QR_CACHE = {}
QR_X, QR_Y0, QR_DY, QR_MOD = 830.0, 1480.0, 225.0, 4          # two codes beside the table, 4 px a module
def qr_tile(url, px):
    if (url, px) not in QR_CACHE:
        import cv2
        q = cv2.QRCodeEncoder.create().encode(url); q = np.pad(q, 3, constant_values=255); mod = px
        big = np.kron(q, np.ones((mod, mod), dtype=np.uint8))
        rgb = np.where(big[..., None] == 0, np.array(INK, np.uint8), np.array((0xF1, 0xE6, 0xCC), np.uint8)).astype(np.uint8)
        QR_CACHE[(url, px)] = Image.fromarray(rgb)
    return QR_CACHE[(url, px)]

if __name__ == '__main__':
    import sys, time
    outd = '/tmp/claude-0/-home-claude/ff0f67d2-fdd3-511c-bf07-cd3391078e59/scratchpad/'
    for v in [float(a) for a in sys.argv[1:]]:
        t0 = time.time(); frame(v).save(outd + 'leo-%05.2f.png' % v); s_ = v - T_COVER; print('t', v, 'story', round(s_, 2), 'cam', [round(x, 1) for x in camera(max(0, s_))], 'test min', round(test_min(s_), 2), 'secs', round(time.time() - t0, 2))
```

```python
#!/usr/bin/env python3
# render_leo.py <frames_dir> <part> <parts>: frames of leo.py at 30 fps, every <parts>-th frame from <part>; resumable
import sys, os, leo
OUT, PART, PARTS = sys.argv[1], int(sys.argv[2]), int(sys.argv[3]); os.makedirs(OUT, exist_ok=True)
N = int(round(leo.T_VIDEO * 30)); made = 0
for i in range(PART, N, PARTS):
    p = os.path.join(OUT, 'f%04d.png' % i)
    if os.path.exists(p): continue
    tmp = p + '.tmp.png'; leo.frame(i / 30).save(tmp, compress_level=1); os.replace(tmp, p); made += 1
print('part', PART, 'made', made, 'of', len(range(PART, N, PARTS)))
```

```python
#!/usr/bin/env python3
# qc_leo.py [video.mp4 [frames_dir]]: stress test of the notebook version. Layout on every 3rd frame while the camera is at rest:
# every string against every other string, the frame edges and footer, the trace's edge and the pen. Reading pace.
# Numbers from the curve. With the encoded file: spec, faststart, colour decoded as a phone does it against the frames,
# QR codes read back out of the last frame, and the largest single-frame change.
import sys, subprocess, os
import numpy as np
from PIL import ImageDraw, Image
import leo, model as M
FPS = 30; N = int(round(leo.T_VIDEO * FPS)); faults = []; REC = []
_orig = ImageDraw.ImageDraw.text
INK_OF = {}; SIZES = []; DRAWN = []
def rec(self, xy, text, fill=None, font=None, anchor=None, *a, **k):
    if self.im.size == (leo.W, leo.H) and self.im.mode != 'L' and text.strip():     # the frame, not a mask drawn to clear paper round a word
        bb = font.getbbox(text, anchor=anchor or 'la'); x, y = xy
        alpha = fill[3] / 255 if isinstance(fill, tuple) and len(fill) == 4 else 1.0
        box = (x + bb[0], y + bb[1], x + bb[2], y + bb[3]); REC.append((text, box, alpha)); INK_OF[(text, box)] = (xy, font, anchor); SIZES.append((font.size, text))
    return _orig(self, xy, text, fill, font, anchor, *a, **k)
def ink_gap(s1, b1, s2, b2):
    """the true distance between two strings' ink: italic overhangs make boxes meet where the letters do not"""
    from scipy.ndimage import distance_transform_edt
    x0, y0 = int(min(b1[0], b2[0])) - 4, int(min(b1[1], b2[1])) - 4; x1, y1 = int(max(b1[2], b2[2])) + 4, int(max(b1[3], b2[3])) + 4
    ms = []
    for s, b in ((s1, b1), (s2, b2)):
        (x, y), f, an = INK_OF[(s, b)]; m = Image.new('L', (x1 - x0, y1 - y0), 0)
        _orig(ImageDraw.Draw(m), (x - x0, y - y0), s, 255, f, an); ms.append(np.asarray(m) > 60)
    if not ms[0].any() or not ms[1].any(): return 99.0
    return float(distance_transform_edt(~ms[0])[ms[1]].min())
ImageDraw.ImageDraw.text = rec
REST = [leo.CAM_FULL, leo.CAM_DETAIL, leo.CAM_FOOT]
def at_rest(v): c = leo.camera(v); return any(all(abs(p - q) < 1e-3 for p, q in zip(c, r)) for r in REST)
def inter(a, b, pad=0): return not (a[2] + pad <= b[0] or b[2] + pad <= a[0] or a[3] + pad <= b[1] or b[3] + pad <= a[1])
checked = 0
for i in range(0, N, 3):
    t = i / FPS; cover = t < leo.T_COVER; v = t - leo.T_COVER                # video time t; story time v
    if cover and i: continue                                               # the cover is one still; its dissolve blends two checked stills
    if not cover and not at_rest(v): continue
    REC.clear(); leo.frame(t); checked += 1; cam = leo.CAM_FULL if cover else leo.camera(v)
    vis = [(s, b, a) for s, b, a in REC if a > 0.35]
    for j, (s, b, a) in enumerate(vis):
        onscreen = b[2] > 0 and b[0] < leo.W and b[3] > 0 and b[1] < leo.H - leo.FOOT
        if s != leo.CREDIT and onscreen and (b[0] < 24 or b[2] > leo.W - 24 or b[1] < 16 or b[3] > leo.H - leo.FOOT - 2): faults.append((v, 'edge', s))
        for s2, b2, a2 in vis[j + 1:]:
            same_line = abs((b[1] + b[3]) / 2 - (b2[1] + b2[3]) / 2) < 9 and (b[2] <= b2[0] + 3 or b2[2] <= b[0] + 3)
            if inter(b, b2, 1) and not same_line and ink_gap(s, b, s2, b2) < 4: faults.append((v, 'text on text', s + ' / ' + s2))
    vis = [(s, b, a) for s, b, a in vis if b[2] > 0 and b[0] < leo.W and b[3] > 0 and b[1] < leo.H]
    if cover or v >= leo.T_START:                                            # the trace edge and the pen, in screen space
        t_now = (leo.FULL_MIN if cover else leo.test_min(v)) * 60; ts = np.linspace(0, t_now, 300)
        pts = leo.to_screen([(leo.tx(t), leo.up(M.A(t))) for t in ts] + [(leo.tx(t), leo.dn(M.A(t))) for t in ts], cam)
        w = leo.width_now(v); pen = leo.to_screen([(leo.tx(t_now), leo.YM - w / 2 * leo.SYS * leo.phase(v))], cam)[0] if not cover and v < leo.T_CLOSE else None
        for s, b, a in vis:
            if s == leo.CREDIT: continue
            hit = ((pts[:, 0] >= b[0] - 2) & (pts[:, 0] <= b[2] + 2) & (pts[:, 1] >= b[1] - 2) & (pts[:, 1] <= b[3] + 2)).sum()
            if hit: faults.append((v, 'text on the trace edge', s))
            if pen is not None and b[0] - 10 <= pen[0] <= b[2] + 10 and b[1] - 10 <= pen[1] <= b[3] + 10: faults.append((v, 'text under the pen', s))
    if cover or checked % 5 == 1:                                         # text against the drawing itself: ink under a word, from a render without words
        bare = np.asarray((leo.cover(False) if cover else leo.story_frame(v, False)).convert('L'), float); paper = np.asarray(leo.background(cam).convert('L'), float)
        ink = (paper - bare) > 30
        for s, b, a in vis:
            if s == leo.CREDIT or (s == 'alpha' and cam[2] < 1.5): continue   # the credit is on its band; the final 'alpha' is written into cleared hatching on purpose
            x0, y0, x1, y1 = [int(round(c)) for c in b]; x0, y0 = max(x0 + 1, 0), max(y0 + 1, 0); x1, y1 = min(x1 - 1, leo.W), min(y1 - 1, leo.H - leo.FOOT)
            if x1 <= x0 or y1 <= y0: continue
            frac = ink[y0:y1, x0:x1].mean()
            if frac > 0.004: faults.append((v, 'text on the drawing (%.1f%% of its box inked)' % (frac * 100), s))
        DRAWN.append(v)
    if cover: print('cover checked: %d strings on it' % len(vis))
    if checked % 20 == 0: print('.', end='', flush=True)
print()
seen = {}
for f in faults: seen.setdefault((f[1], f[2]), []).append(round(f[0], 2))
for (kind, s), ts in seen.items(): print('FAULT %s: "%s" at %s s' % (kind, s[:60], ts[:5] + (['...'] if len(ts) > 5 else [])))
print('frames checked at rest', checked, '| layout faults', len(seen))
for a, b, s, where in leo.NOTES:
    full = (b - a - 0.05) - (0.25 if b < leo.T_END else 0); words = len(s.split())
    print('note %5.1f-%5.1f s (%s): %2d words, %.1f s, %.1f words/s%s' % (a, b, where, words, full, words / full, '  FAST' if words / full > 3.4 else ''))
m = M.measured(); print('numbers from the drawn curve: R %.2f, K %.2f, alpha %.1f, MA %.1f, LY30 %.2f' % (m['R_min'], m['K_min'], m['alpha'], m['MA'], m['LY30']))
sm = min(SIZES); print('smallest text drawn in any frame at rest: %d px ("%s") = %.2f pt on a phone 390 pt wide; text checked against the drawing in %d frames' % (sm[0], sm[1][:30], sm[0] * 390 / 1080, len(DRAWN)))
if len(sys.argv) > 1:
    V = sys.argv[1]; FR = sys.argv[2] if len(sys.argv) > 2 else 'lframes2'
    print(subprocess.run(['ffprobe', '-v', 'error', '-show_entries', 'stream=codec_name,profile,width,height,pix_fmt,r_frame_rate,nb_frames,color_space,color_transfer,color_primaries,color_range:format=duration,size', '-of', 'compact', V], capture_output=True, text=True).stdout.strip())
    d = open(V, 'rb').read(); print('faststart:', d.find(b'moov') < d.find(b'mdat'))
    DEC = ['-vf', 'scale=in_color_matrix=bt709:in_range=tv:out_range=pc:flags=accurate_rnd+full_chroma_int,format=rgb24', '-f', 'rawvideo', '-']
    def grab(i):
        buf = subprocess.run(['ffmpeg', '-v', 'error', '-ss', '%.4f' % ((i - 0.4) / FPS), '-i', V, '-frames:v', '1'] + DEC, capture_output=True).stdout
        return np.frombuffer(buf[:1080 * 1350 * 3], np.uint8).reshape(1350, 1080, 3)
    for i in (0, 30, 300, 520, 700, N - 1):
        f = grab(i).astype(float); src = np.asarray(Image.open(os.path.join(FR, 'f%04d.png' % i)).convert('RGB'), float)
        mse = ((f - src) ** 2).mean(); print('frame %d: decoded as a phone vs drawn, PSNR %.1f dB, mean colour %s vs %s' % (i, 10 * np.log10(255 ** 2 / mse), tuple(int(x) for x in f.reshape(-1, 3).mean(0)), tuple(int(x) for x in src.reshape(-1, 3).mean(0))))
    f0 = grab(0).astype(float); ink = (f0.mean(2) < 150).mean() * 100; chalk = (grab(46).astype(float).mean(2) < 150).mean() * 100
    print('first frame: the finished page, %.1f%% of it in ink or wash dark enough to read (the red chalk start: %.1f%%)' % (ink, chalk))
    import cv2
    last = grab(N - 1); det = cv2.QRCodeDetector(); cam = leo.CAM_FOOT
    for k in range(2):
        X, Y = leo.to_screen([(leo.QR_X, leo.QR_Y0 + k * leo.QR_DY)], cam)[0]; P = leo.qr_tile(leo.QRS[k][1], leo.QR_MOD).width
        crop = np.ascontiguousarray(last[int(Y) - 14:int(Y) + P + 14, int(X) - 14:int(X) + P + 14][:, :, ::-1])
        print('QR %d read from the encoded last frame: %s' % (k + 1, det.detectAndDecode(crop)[0] or 'NOT READ'))
    p = subprocess.Popen(['ffmpeg', '-v', 'error', '-i', V] + DEC, stdout=subprocess.PIPE); prev = None; steps = []; i = 0
    while True:
        buf = p.stdout.read(1080 * 1350 * 3)
        if len(buf) < 1080 * 1350 * 3: break
        f = np.frombuffer(buf, np.uint8).reshape(1350, 1080, 3).astype(np.int16)
        if prev is not None: steps.append((float(np.abs(f - prev).mean()), i))
        prev = f; i += 1
    p.wait(); steps.sort(reverse=True)
    print('decoded frames', i, '| largest frame-to-frame changes (mean level, frame, s):', [(round(a, 2), b, round(b / FPS, 2)) for a, b in steps[:5]])
```

## W. The TEG explainer video (model.py, teg2.py, render.py, qc_teg.py in one folder)

```
python3 render.py frames 0 2 & python3 render.py frames 1 2      # two halves in parallel; resumable
ffmpeg -framerate 30 -i frames/f%04d.png -vf "scale=out_color_matrix=bt709:out_range=tv:flags=accurate_rnd+full_chroma_int+full_chroma_inp,format=yuv420p" -c:v libx264 -preset slow -crf 16 -profile:v high -colorspace bt709 -color_primaries bt709 -color_trc iec61966-2-1 -color_range tv -movflags +faststart+write_colr -r 30 how-a-teg-draws-its-trace-v1.mp4
python3 qc_teg.py how-a-teg-draws-its-trace-v1.mp4               # must end with 0 layout faults and both QR codes read
```

```python
# model.py: the example normal kaolin TEG, drawn by the app's own engine law (engine.js, k = 1):
# A(t) = MA (1 - exp(-(t - t0)/tau)), with A(R) = 2 mm and A(R + K) = 20 mm, R, K, MA at the midpoints of the
# kaolin ranges in Srivastava 2013 Table 2 (R 4-8 min, K 1-4 min, MA 55-73 mm), no lysis. Every printed number is
# recomputed from this curve; alpha uses the app's convention (tangent at 2 mm, K_ALPHA 13.6 s per mm).
import math
R_S, K_S, MA = 360.0, 150.0, 64.0          # 6 min, 2.5 min, 64 mm
K_ALPHA = 13.6
a = -math.log(1 - 2 / MA); b = -math.log(1 - 20 / MA)
TAU = K_S / (b - a); T0 = R_S - TAU * a
def A(t):                                   # width in mm at t seconds
    return 0.0 if t <= T0 else MA * (1 - math.exp(-(t - T0) / TAU))
def dA(t):                                  # mm per second
    return 0.0 if t <= T0 else MA / TAU * math.exp(-(t - T0) / TAU)
def t_at(width):                            # seconds at which the curve reaches a width
    return T0 - TAU * math.log(1 - width / MA)
T_MA = t_at(0.98 * MA)                       # the app marks the maximum where the curve is within 2% of it
def measured():
    R = t_at(2.0); K = t_at(20.0) - R
    alpha = math.degrees(math.atan(K_ALPHA * dA(R)))
    ma = MA                                   # the parameter; the plateau value
    t_ly = T_MA + 1800
    ly30 = max(0.0, (A(T_MA) - A(t_ly)) / A(T_MA) * 100)
    return dict(R_min=R / 60, K_min=K / 60, alpha=alpha, MA=ma, T_MA_min=T_MA / 60, LY30=ly30, T0_min=T0 / 60)
if __name__ == '__main__':
    print({k: round(v, 3) for k, v in measured().items()}, 'tau', round(TAU, 2), 't0', round(T0, 2))
```

```python
#!/usr/bin/env python3
# teg2.py: "How a TEG draws its trace", second look. The app's garnet as the ground, the trace in cream like the app's
# icon, the cup seen from above as one shape. Every frame drawn in Python: shapes on a 3x canvas averaged down, text at 1x
# in the real Lora and Poppins. frame(v) returns the picture at video time v seconds.
import math, random
import numpy as np
from PIL import Image, ImageDraw, ImageFont
from fontTools.ttLib import TTFont
import model as M

W, H, SS, FOOT = 1080, 1350, 3, 64
GROUND = (0x7A, 0x1F, 0x3D)                     # the app's accent, as the whole ground
WINE, PAPER, CREAM, RULE, RULE2, MUTED, INK = (0x4A, 0x0F, 0x24), (0xFB, 0xF9, 0xF4), (0xEF, 0xE9, 0xDC), (0xD8, 0xD0, 0xC0), (0xE6, 0xDF, 0xD0), (0x5B, 0x53, 0x49), (0x22, 0x1E, 0x19)
FIB = (0xF6, 0xE0, 0xD6)
F = '/usr/share/fonts/truetype/google-fonts/'
def lora(size, wght=500):
    f = ImageFont.truetype(F + 'Lora-Variable.ttf', size); f.set_variation_by_axes([wght]); return f
def pop(size, weight='Regular'): return ImageFont.truetype(F + 'Poppins-%s.ttf' % weight, size)
POPMAP = set(TTFont(F + 'Poppins-Regular.ttf').getBestCmap())
F_TITLE, F_CAP, F_LAB, F_NOTE, F_PARAM, F_VAL, F_FOOT, F_CLOCK, F_HEAD = lora(56), pop(32), pop(26), pop(24), lora(36, 600), pop(30, 'Medium'), pop(25), pop(30, 'Medium'), pop(24)
FALLBACK = {id(F_CAP): lora(32), id(F_LAB): lora(26), id(F_NOTE): lora(24), id(F_VAL): lora(30, 500)}
CREDIT = 'Dr Ganesh Sivasankara · MD · FRCA · FCARCSI · Consultant Anaesthetist'
def runs(s, font):
    out, cur, fb = [], '', None
    for ch in s:
        need = id(font) in FALLBACK and ord(ch) not in POPMAP
        if need != fb and cur: out.append((cur, fb)); cur = ''
        cur += ch; fb = need
    if cur: out.append((cur, fb))
    return [(t, FALLBACK[id(font)] if f else font) for t, f in out]
def tlen(d, s, font): return sum(d.textlength(t, font=f) for t, f in runs(s, font))
def text(d, xy, s, font, fill):
    x, y = xy
    for t, f in runs(s, font): d.text((x, y), t, font=f, fill=fill); x += d.textlength(t, font=f)
def pa(a): return PAPER + (int(255 * max(0.0, min(1.0, a))),)

# ---------------------------------------------------------------- script and clock
TITLE = 'How a TEG draws its trace'
CAPTIONS = [   # each line held long enough to read at about 3.4 words a second, with a quarter-second fade out and in
    (0.0, 4.2, 'A TEG turns a cup of blood back and forth around a pin.'),
    (4.2, 8.0, 'Liquid blood leaves the pin still, so the trace is flat.'),
    (8.0, 11.8, 'As the blood clots, fibrin links the cup to the pin.'),
    (11.8, 15.6, 'The pin starts to swing, and the trace widens with it.'),
    (15.6, 19.4, 'R is the time until the trace is 2 mm wide.'),
    (19.4, 22.6, 'K is the time from 2 to 20 mm.'),
    (22.6, 26.7, 'Alpha is the angle of the rise, the speed of fibrin build-up.'),
    (26.7, 31.1, 'MA, the widest point, is the clot’s strength, set by platelets and fibrinogen.'),
    (31.1, 35.3, 'LY30 is the share of that width lost 30 minutes after MA.'),
    (35.3, 41.0, 'This trace is an example drawn through the middle of the R, K and MA ranges.'),
]
T_START, T_CLOSE, T_END = 0.6, 35.3, 41.0
FADE = 0.25
KNOTS = [(0.6, 0.0), (8.0, 5.6), (11.8, 6.9), (15.6, 8.6), (19.4, 8.7), (22.6, 8.78), (26.7, 8.86), (27.9, 12.0), (29.1, 34.3), (31.1, 35.6), (33.1, 64.3), (33.7, 66.0)]
def pchip(xs, ys):
    xs, ys = np.array(xs, float), np.array(ys, float); h = np.diff(xs); dl = np.diff(ys) / h; m = np.zeros(len(xs))
    for i in range(1, len(xs) - 1):
        if dl[i - 1] * dl[i] > 0: w1, w2 = 2 * h[i] + h[i - 1], h[i] + 2 * h[i - 1]; m[i] = (w1 + w2) / (w1 / dl[i - 1] + w2 / dl[i])
    m[0], m[-1] = dl[0], dl[-1]
    def f(x):
        if x <= xs[0]: return float(ys[0])
        if x >= xs[-1]: return float(ys[-1])
        i = int(np.searchsorted(xs, x) - 1); t = (x - xs[i]) / h[i]
        return float((2*t**3 - 3*t**2 + 1) * ys[i] + (t**3 - 2*t**2 + t) * h[i] * m[i] + (-2*t**3 + 3*t**2) * ys[i+1] + (t**3 - t**2) * h[i] * m[i+1])
    return f
TEST_MIN = pchip(*zip(*KNOTS))
def test_min(v): return 0.0 if v < T_START else TEST_MIN(v)
def smooth(u): u = max(0.0, min(1.0, u)); return u * u * (3 - 2 * u)
def ramp(v, a, b): return smooth((v - a) / (b - a)) if b > a else float(v >= a)
def window(v, a, b, fade=0.4): return min(ramp(v, a - fade / 2, a + fade / 2), 1 - ramp(v, b - fade / 2, b + fade / 2))

# ---------------------------------------------------------------- the cup, seen from above
GXC, GYC = 540.0, 424.0
R_O, R_W, R_P = 168.0, 146.0, 92.0
CUP_SWING = math.radians(26)            # drawn about 4.6 times the real turn; the screen says the movement is exaggerated
ROCK_T = 1.8
def G(r, a): return (GXC + r * math.cos(a), GYC - r * math.sin(a))
def phase(v): return math.sin(2 * math.pi * (v - T_START) / ROCK_T) if v >= T_START else 0.0
def cup_angle(v): return CUP_SWING * ramp(v, T_START - 0.2, T_START + 0.6) * phase(v)
def width_now(v): return M.A(test_min(v) * 60) if v >= T_START else 0.0
def clot(v): return width_now(v) / M.MA
def pin_angle(v): return cup_angle(v) * width_now(v) / 100.0      # the pin follows the cup in proportion to the width
rng = random.Random(5)
THREADS = []
for i in range(72):
    a = 2 * math.pi * (i + rng.uniform(-0.35, 0.35)) / 72
    THREADS.append(dict(a=a, d=rng.uniform(-0.22, 0.22), bow=rng.uniform(-6, 6), u=rng.random() * 0.9, w=rng.uniform(1.3, 2.3)))
LINKS = []
for i in range(40):
    a = rng.uniform(0, 2 * math.pi); r = rng.uniform(R_P + 12, R_W - 12)
    LINKS.append(dict(a=a, r=r, da=rng.uniform(0.07, 0.16), u=0.2 + rng.random() * 0.75))

# ---------------------------------------------------------------- the trace, angle-true
GX0, GX1, YM, YAX = 72.0, 1008.0, 930.0, 1172.0
FULL_MIN = 66.0
SX1 = (GX1 - GX0) / (FULL_MIN * 60)
def zoom(v): return 1.0 + 1.4 * ramp(v, 1.6, 3.0) - 1.4 * ramp(v, 26.7, 27.9)
def sx(v): return SX1 * zoom(v)
def sy(v): return sx(v) * 2 * M.K_ALPHA
def tx(t, v): return GX0 + t * sx(v)
def up(w, v): return YM - w / 2 * sy(v)
def dn(w, v): return YM + w / 2 * sy(v)

class Canvas:
    def __init__(self):
        self.im = Image.new('RGBA', (W * SS, H * SS), GROUND + (255,)); self.d = ImageDraw.Draw(self.im)
    def layer(self): return Image.new('RGBA', self.im.size, (0, 0, 0, 0))
    def comp(self, lay): self.im = Image.alpha_composite(self.im, lay); self.d = ImageDraw.Draw(self.im)
def S(pts): return [(x * SS, y * SS) for x, y in pts]
def circle(d, c, r, **kw): d.ellipse([(c[0] - r) * SS, (c[1] - r) * SS, (c[0] + r) * SS, (c[1] + r) * SS], **kw)
def head(d, tip, ang, col, size=13, spread=0.45):
    a = (tip[0] - size * math.cos(ang - spread), tip[1] - size * math.sin(ang - spread)); b = (tip[0] - size * math.cos(ang + spread), tip[1] - size * math.sin(ang + spread))
    d.polygon(S([tip, a, b]), fill=col)
def bez(a, b, bow, n=12):
    mx, my = (a[0] + b[0]) / 2, (a[1] + b[1]) / 2; dx, dy = b[0] - a[0], b[1] - a[1]; L = math.hypot(dx, dy) or 1
    cx, cy = mx - dy / L * bow, my + dx / L * bow
    return [((1-t)**2 * a[0] + 2*(1-t)*t * cx + t*t * b[0], (1-t)**2 * a[1] + 2*(1-t)*t * cy + t*t * b[1]) for t in (i / n for i in range(n + 1))]
def arc_pts(r, a0, a1, n=48): return [G(r, a0 + (a1 - a0) * i / n) for i in range(n + 1)]

def draw_cup(c, v, alpha):
    if alpha <= 0: return
    lay = c.layer(); d = ImageDraw.Draw(lay); A = lambda k=1.0: int(255 * alpha * k)
    th_c, th_p, s = cup_angle(v), pin_angle(v), clot(v)
    circle(d, (GXC, GYC), R_O, fill=PAPER + (A(),))                       # the cup wall
    for k in range(36):                                                  # ticks on the rim ride the cup's turn
        a = th_c + k * math.pi / 18; p1, p2 = G(R_W + 5, a), G(R_O - 5, a)
        d.line(S([p1, p2]), fill=GROUND + (A(),), width=int(2.6 * SS))
    circle(d, (GXC, GYC), R_W, fill=WINE + (A(),))                        # the blood
    for t in THREADS:                                                    # fibrin, pin to wall, more as the clot firms
        al = max(0.0, min(1.0, (s ** 0.4 * 1.1 - t['u']) / 0.07))   # strands come early: they make the first millimetres
        if al > 0:
            p1 = G(R_P + 1, t['a'] + th_p); p2 = G(R_W - 1, t['a'] + t['d'] + th_c)
            d.line(S(bez(p1, p2, t['bow'])), fill=FIB + (A(0.92 * al),), width=max(1, int(t['w'] * (0.85 + 0.5 * s) * SS)), joint='curve')
    for l in LINKS:
        al = max(0.0, min(1.0, (s ** 0.4 * 1.1 - l['u']) / 0.07))
        if al > 0:
            frac = (l['r'] - R_P) / (R_W - R_P); rot = th_p + (th_c - th_p) * frac
            d.line(S(arc_pts(l['r'], l['a'] + rot, l['a'] + rot + l['da'], 8)), fill=FIB + (A(0.8 * al),), width=int(1.3 * SS), joint='curve')
    circle(d, (GXC, GYC), R_P, fill=PAPER + (A(),))                       # the pin
    circle(d, (GXC, GYC), R_P - 16, outline=RULE2 + (A(),), width=int(2 * SS))
    span = CUP_SWING * width_now(v) / 100.0                              # the pin's swing, drawn inside its face
    if span > 0.01:                                                      # the fan the notch sweeps
        fan = [(GXC, GYC)] + arc_pts(R_P - 8, -span, span, 30); k = 0.18 * min(1.0, s * 4)   # blended by hand: the layer does not mix within itself
        d.polygon(S(fan), fill=tuple(int(p * (1 - k) + g * k) for p, g in zip(PAPER, GROUND)) + (A(),))
    p1, p2 = G(18, th_p), G(R_P - 8, th_p)                               # the notch that turns with the pin
    d.line(S([p1, p2]), fill=GROUND + (A(),), width=int(6 * SS)); circle(d, p2, 3, fill=GROUND + (A(),))
    a_cup = ramp(v, 0.2, 0.9)                                            # the cup's turn, outside the rim
    arc = arc_pts(R_O + 24, -CUP_SWING, CUP_SWING, 40)
    d.line(S(arc), fill=PAPER + (A(a_cup),), width=int(3 * SS), joint='curve')
    for e, nx in ((arc[0], arc[1]), (arc[-1], arc[-2])): head(d, e, math.atan2(e[1] - nx[1], e[0] - nx[0]), PAPER + (A(a_cup),), 14)
    c.comp(lay)

def draw_trace(c, v):
    lay = c.layer(); d = ImageDraw.Draw(lay); t_now = test_min(v) * 60; z = zoom(v)
    d.line(S([(GX0, YM), (GX1, YM)]), fill=pa(0.22), width=int(2 * SS))
    d.line(S([(GX0, YAX), (GX1, YAX)]), fill=pa(0.62), width=int(2 * SS))
    for m in range(0, 67, 5):
        x = tx(m * 60, v)
        if GX0 - 1 <= x <= GX1 + 1: d.line(S([(x, YAX), (x, YAX + 9)]), fill=pa(0.62), width=int(2 * SS))
    a_ghost = 1 - ramp(v, 1.1, 2.4)
    if a_ghost > 0:
        ts = np.linspace(0, FULL_MIN * 60, 400)
        U = [(GX0 + t * SX1, YM - M.A(t) / 2 * SX1 * 2 * M.K_ALPHA) for t in ts]; D = [(x, 2 * YM - y) for x, y in U]
        d.polygon(S(U + D[::-1]), fill=pa(0.07 * a_ghost)); d.line(S(U), fill=pa(0.3 * a_ghost), width=int(2.4 * SS), joint='curve'); d.line(S(D), fill=pa(0.3 * a_ghost), width=int(2.4 * SS), joint='curve')
    if v >= T_START:
        ts = np.linspace(0, t_now, 500)
        U = [(tx(t, v), up(M.A(t), v)) for t in ts]; D = [(x, 2 * YM - y) for x, y in U]
        solid = ramp(v, T_CLOSE + 0.1, T_CLOSE + 1.1)
        d.polygon(S(U + D[::-1]), fill=pa(0.14 + 0.86 * solid))
        d.line(S(U), fill=pa(1), width=int(3.4 * SS), joint='curve'); d.line(S(D), fill=pa(1), width=int(3.4 * SS), joint='curve')
        if v < T_CLOSE:
            w = M.A(t_now); pen = (tx(t_now, v), YM - w / 2 * sy(v) * phase(v))
            circle(d, pen, 9, fill=PAPER + (255,)); circle(d, pen, 4, fill=GROUND + (255,))
    c.comp(lay)

def marks(c, v):
    jobs = []; tm = test_min(v); R, K = M.R_S, M.K_S
    lay = c.layer(); ld = ImageDraw.Draw(lay)
    def seg(pts, al, w, col=PAPER): ld.line(S(pts), fill=col + (int(255 * al),), width=max(1, int(w * SS)), joint='curve')
    out = 1 - ramp(v, 26.5, 27.1)
    aR = ramp(v, 15.6, 16.1) * out if tm >= 6.0 else 0.0
    aK = ramp(v, 19.4, 19.9) * out if tm >= 8.5 else 0.0
    aK20 = aK * (1 - ramp(v, 22.5, 22.9))
    aA = ramp(v, 22.8, 23.4) * out
    xR, xK = tx(R, v), tx(R + K, v)
    if aR > 0:
        seg([(xR, dn(2, v) + 5), (xR, YAX - 3)], aR * 0.55, 1.8)
        seg([(GX0, YAX - 12), (xR - 3, YAX - 12)], aR, 6)
        jobs.append(('param', 'R', '6 min', (GX0 + (xR - GX0) / 2, YAX + 30), aR))
        for yy in (up(2, v), dn(2, v)): seg([(xR - 25, yy), (xR - 13, yy)], aR, 2.2)
        seg([(xR - 19, up(2, v)), (xR - 19, dn(2, v))], aR, 2.2)
        jobs.append(('right', '2 mm', None, (xR - 32, up(2, v) - 26), aR))
    if aK > 0:
        seg([(xK, dn(20, v) + 5), (xK, YAX - 3)], aK * 0.55, 1.8)
        seg([(xR + 3, YAX - 12), (xK - 3, YAX - 12)], aK * 0.6, 6)
        jobs.append(('param', 'K', '2.5 min', ((xR + xK) / 2 + 30, YAX + 30), aK))
    if aK20 > 0:
        y1, y2 = up(20, v), dn(20, v); x = xK + 18
        seg([(x, y1 + 6), (x, y2 - 6)], aK20, 2.4); head(ld, (x, y1), -math.pi / 2, pa(aK20), 13); head(ld, (x, y2), math.pi / 2, pa(aK20), 13)
        jobs.append(('left', '20 mm', None, (x + 16, YM), aK20))
    if aA > 0:
        x2, y2 = xR, up(2, v); ang = math.atan(M.dA(R) / 2 * sy(v) / sx(v))
        seg([(x2 - 40 * math.cos(ang), y2 + 40 * math.sin(ang)), (x2 + 200 * math.cos(ang), y2 - 200 * math.sin(ang))], aA, 2.4)
        seg([(x2, y2), (x2 + 160, y2)], aA, 1.8)
        rr = 80; seg([(x2 + rr * math.cos(-ang * i / 30), y2 + rr * math.sin(-ang * i / 30)) for i in range(31)], aA, 2.6)
        xl = max(x2 + rr * math.cos(ang / 2) + 16, tx(tm * 60, v) + 28)
        jobs.append(('left', 'alpha %d°' % round(M.measured()['alpha']), None, (xl, y2 - rr * math.sin(ang / 2) - 4), aA))
    fade_close = 1 - ramp(v, T_CLOSE, T_CLOSE + 0.6)
    xM = tx(M.T_MA, v); aM = ramp(v, 29.1, 29.6) * fade_close
    if aM > 0:
        y1, y2 = up(M.MA, v), dn(M.MA, v)
        seg([(xM, y1 + 8), (xM, y2 - 8)], aM, 2.4); head(ld, (xM, y1 + 2), -math.pi / 2, pa(aM), 14); head(ld, (xM, y2 - 2), math.pi / 2, pa(aM), 14)
        jobs.append(('param_r', 'MA', '%d mm' % round(M.MA), (xM - 18, YM - 34), aM))   # left of the arrow, out of the pen's path
    aL = ramp(v, 33.1, 33.6) * fade_close
    if aL > 0:
        x1, x2 = xM, tx(M.T_MA + 1800, v); yb = up(M.MA, v) - 20
        seg([(x1, yb + 11), (x1, yb), (x2, yb), (x2, yb + 11)], aL, 2.4)
        jobs.append(('param', 'LY30', '0%', ((x1 + x2) / 2, yb - 26), aL))
    c.comp(lay)
    return jobs

def frame(v):
    c = Canvas()
    draw_cup(c, v, 1 - ramp(v, T_CLOSE, T_CLOSE + 0.7))
    draw_trace(c, v); jobs = marks(c, v)
    im = c.im.resize((W, H), Image.Resampling.BOX).convert('RGBA')
    lay = Image.new('RGBA', (W, H), (0, 0, 0, 0)); d = ImageDraw.Draw(lay)
    d.text((72, 42), TITLE, font=F_TITLE, fill=pa(1))
    for a, b, s in CAPTIONS:
        al = (1.0 if a == 0 else ramp(v, a, a + FADE)) * (1.0 if b >= T_END else 1 - ramp(v, b - FADE, b))   # one line at a time: out, then in
        if al <= 0: continue
        lines, cur = [], ''
        for w_ in s.split():
            t = (cur + ' ' + w_).strip()
            if tlen(d, t, F_CAP) <= 936: cur = t
            else: lines.append(cur); cur = w_
        lines.append(cur); y = 128 + (1 - al) * 6
        for ln in lines: text(d, (72, y), ln, F_CAP, pa(0.96 * al)); y += 46
    a_cup = 1 - ramp(v, T_CLOSE, T_CLOSE + 0.7)
    if a_cup > 0:                                                         # three small labels on the cup
        p = G(R_O, math.radians(142)); q = (p[0] - 40, p[1] - 34)
        d.line([(p[0] - 4, p[1] - 3), q], fill=pa(0.8 * a_cup), width=2)
        s_ = 'cup, seen from above'; w_ = tlen(d, s_, F_LAB); text(d, (q[0] - w_ - 10, q[1] - 18), s_, F_LAB, pa(0.9 * a_cup))
        ab = a_cup * (1 - ramp(v, 7.9, 8.6))
        if ab > 0:
            w_ = d.textlength('blood', font=F_LAB); d.text((GXC - w_ / 2, GYC + (R_P + R_W) / 2 - 18), 'blood', font=F_LAB, fill=pa(0.9 * ab))
        w_ = d.textlength('pin', font=F_LAB); d.text((GXC - 40 - w_ / 2, GYC - 20), 'pin', font=F_LAB, fill=GROUND + (int(255 * a_cup),))
        s_ = 'movement exaggerated'; w_ = tlen(d, s_, F_NOTE); text(d, (GXC - w_ / 2, GYC + R_O + 20), s_, F_NOTE, pa(0.72 * a_cup * ramp(v, 0.2, 0.9)))
    if T_START <= v < T_CLOSE + 0.6:
        d.text((72, 664), '%d min' % int(test_min(v) + 1e-6), font=F_CLOCK, fill=pa(0.78 * (1 - ramp(v, T_CLOSE, T_CLOSE + 0.6))))
    a_ticks = ramp(v, 27.7, 28.3)
    if a_ticks > 0:
        for m in range(0, 67, 10):
            x = tx(m * 60, v); s_ = str(m) if m < 60 else '60 min'
            wv = d.textlength(s_, font=F_NOTE); d.text((x - (wv / 2 if m < 60 else 18), YAX + 14), s_, font=F_NOTE, fill=pa(0.72 * a_ticks))
    for kind, s_, val, (x, y), al in jobs:
        if kind in ('param', 'param_l', 'param_r'):
            wp = d.textlength(s_, font=F_PARAM); wv = d.textlength(val, font=F_VAL)
            x0 = x - (wp + 10 + wv) / 2 if kind == 'param' else x if kind == 'param_l' else x - (wp + 10 + wv)
            bp = d.textbbox((0, 0), s_, font=F_PARAM); bv = d.textbbox((0, 0), val, font=F_VAL)
            d.text((x0, y - (bp[1] + bp[3]) / 2), s_, font=F_PARAM, fill=pa(al)); d.text((x0 + wp + 10, y - (bv[1] + bv[3]) / 2), val, font=F_VAL, fill=pa(0.9 * al))
        else:
            bb = d.textbbox((0, 0), s_, font=F_VAL); wv = d.textlength(s_, font=F_VAL)
            d.text((x - wv if kind == 'right' else x, y - (bb[1] + bb[3]) / 2), s_, font=F_VAL, fill=pa(0.95 * al))
    a_tab = ramp(v, T_CLOSE + 0.5, T_CLOSE + 1.2)                          # the closing table
    if a_tab > 0: close_card(d, a_tab)
    d.rectangle([0, H - FOOT, W, H], fill=CREAM + (255,)); d.rectangle([0, H - FOOT, W, H - FOOT + 1], fill=RULE + (255,))
    tw = d.textlength(CREDIT, font=F_FOOT); bb = d.textbbox((0, 0), CREDIT, font=F_FOOT)
    d.text(((W - tw) / 2, H - FOOT / 2 - (bb[1] + bb[3]) / 2), CREDIT, font=F_FOOT, fill=MUTED + (255,))
    out = Image.alpha_composite(im, lay)
    if a_tab > 0: paste_qr(out, a_tab)
    return out.convert('RGB')

ROWS = [('R', '6 min', '4–8 min'), ('K', '2.5 min', '1–4 min'), ('alpha', '63°', '47–74°'), ('MA', '64 mm', '55–73 mm'), ('LY30', '0%', 'over 7.5% means lysis')]
TX = (72, 300, 500); TY0, TDY = 262, 58
def close_card(d, al):
    m = M.measured(); assert round(m['R_min']) == 6 and round(m['K_min'], 1) == 2.5 and round(m['alpha']) == 63 and round(m['MA']) == 64 and round(m['LY30']) == 0
    d.text((TX[1], TY0), 'this trace', font=F_HEAD, fill=pa(0.72 * al)); d.text((TX[2], TY0), 'normal, kaolin TEG', font=F_HEAD, fill=pa(0.72 * al))
    for i, (p, a, b) in enumerate(ROWS):
        y = TY0 + 44 + i * TDY
        f = F_PARAM if p != 'alpha' else lora(34, 600)
        d.text((TX[0], y), p, font=f, fill=pa(al)); text(d, (TX[1], y + 4), a, F_VAL, pa(0.95 * al)); text(d, (TX[2], y + 4), b, F_VAL, pa(0.95 * al))
    d.line([(72, TY0 + 36), (820, TY0 + 36)], fill=pa(0.3 * al), width=2)
QRS = [('Srivastava 2013', 'https://doi.org/10.1093/bjaceaccp/mks049'), ('Wells 2022', 'https://doi.org/10.1016/j.bjae.2022.07.003')]
_QR = {}
def qr_img(url, size=120):
    if url not in _QR:
        import cv2
        enc = cv2.QRCodeEncoder.create(); q = enc.encode(url)                 # 0 dark, 255 light
        q = np.pad(q, 3, constant_values=255); n = q.shape[0]
        mod = max(3, size // n); big = np.kron(q, np.ones((mod, mod), dtype=np.uint8))
        rgb = np.where(big[..., None] == 0, np.array(INK, np.uint8), np.array(PAPER, np.uint8)).astype(np.uint8)
        _QR[url] = Image.fromarray(rgb)
    return _QR[url]
def paste_qr(out, al):
    d = ImageDraw.Draw(out)
    for i, (name, url) in enumerate(QRS):
        q = qr_img(url); x, y = 858, 250 + i * 190
        tile = q.convert('RGBA'); tile.putalpha(int(255 * al)); out.alpha_composite(tile, (x, y))
        w_ = d.textlength(name, font=F_NOTE); d.text((x + q.width / 2 - w_ / 2, y + q.height + 8), name, font=F_NOTE, fill=pa(0.85 * al))

if __name__ == '__main__':
    import sys
    outd = '/tmp/claude-0/-home-claude/ff0f67d2-fdd3-511c-bf07-cd3391078e59/scratchpad/'
    for v in [float(a) for a in sys.argv[1:]]:
        frame(v).save(outd + 'g-%05.2f.png' % v); print('v', v, 'test min', round(test_min(v), 2), 'width', round(width_now(v), 1), 'zoom', round(zoom(v), 2))
```

```python
#!/usr/bin/env python3
# render.py <frames_dir> <part> <parts>: frames of teg2.py at 30 fps, every <parts>-th frame from <part>; resumable
import sys, os, teg2
OUT, PART, PARTS = sys.argv[1], int(sys.argv[2]), int(sys.argv[3]); os.makedirs(OUT, exist_ok=True)
N = int(round(teg2.T_END * 30)); made = 0
for i in range(PART, N, PARTS):
    p = os.path.join(OUT, 'f%04d.png' % i)
    if os.path.exists(p): continue
    tmp = p + '.tmp.png'; teg2.frame(i / 30).save(tmp, compress_level=1); os.replace(tmp, p); made += 1
print('part', PART, 'made', made, 'of', len(range(PART, N, PARTS)))
```

```python
#!/usr/bin/env python3
# qc_teg.py [video.mp4]: stress test of "How a TEG draws its trace".
# Layout: every drawn string's box against every other string, the frame edges, the trace outline and the pen, on every
# 2nd frame. Reading: each caption's time at full strength against its word count. Numbers: recomputed from the curve.
# With the encoded file: spec, colour as a phone decodes it, QR codes read back out of the closing frames, motion census.
import sys, math, subprocess, json
import numpy as np
from PIL import ImageDraw
import teg2, model as M
FPS = 30; N = int(round(teg2.T_END * FPS)); faults = []
REC = []
_orig = ImageDraw.ImageDraw.text
def rec(self, xy, text, fill=None, font=None, *a, **k):
    if self.im.size == (teg2.W, teg2.H) and text.strip():
        bb = font.getbbox(text); x, y = xy
        alpha = fill[3] / 255 if isinstance(fill, tuple) and len(fill) == 4 else 1.0
        REC.append((text, (x + bb[0], y + bb[1], x + bb[2], y + bb[3]), alpha))
    return _orig(self, xy, text, fill, font, *a, **k)
ImageDraw.ImageDraw.text = rec
def inter(a, b, pad=0): return not (a[2] + pad <= b[0] or b[2] + pad <= a[0] or a[3] + pad <= b[1] or b[3] + pad <= a[1])
def outline_pts(v):
    tm = teg2.test_min(v); pts = []
    if v >= teg2.T_START:
        for t in np.linspace(0, tm * 60, 300):
            x = teg2.tx(t, v); w = M.A(t); pts += [(x, teg2.up(w, v)), (x, teg2.dn(w, v))]
    return pts
worst_gap = (1e9, None)
for i in range(0, N, 2):
    v = i / FPS; REC.clear(); teg2.frame(v)
    vis = [(s, b, a) for s, b, a in REC if a > 0.35]
    for j, (s, b, a) in enumerate(vis):
        if b[0] < 40 or b[2] > teg2.W - 40 or b[1] < 20 or b[3] > teg2.H - teg2.FOOT - 4:
            if s not in (teg2.CREDIT,): faults.append((v, 'edge', s, [round(x) for x in b]))
        for s2, b2, a2 in vis[j + 1:]:
            if inter(b, b2, 2) and not (s in s2 or s2 in s) and not (abs(b[1] - b2[1]) < 2 and (b[2] <= b2[0] + 1 or b2[2] <= b[0] + 1)):
                faults.append((v, 'text on text', s, s2))
    pts = outline_pts(v); pen = None
    if teg2.T_START <= v < teg2.T_CLOSE:
        w = M.A(teg2.test_min(v) * 60); pen = (teg2.tx(teg2.test_min(v) * 60, v), teg2.YM - w / 2 * teg2.sy(v) * teg2.phase(v))
    for s, b, a in vis:
        if b[1] < 640: continue                                            # captions, title and cup labels live above the trace
        hit = [p for p in pts if b[0] - 3 <= p[0] <= b[2] + 3 and b[1] - 3 <= p[1] <= b[3] + 3]
        if hit and v < teg2.T_CLOSE + 0.6: faults.append((v, 'text on the trace outline', s, len(hit)))
        if pen and b[0] - 12 <= pen[0] <= b[2] + 12 and b[1] - 12 <= pen[1] <= b[3] + 12: faults.append((v, 'text under the pen', s))
    if i % 30 == 0: print('.', end='', flush=True)
print()
seen = {}
for f in faults: seen.setdefault((f[1], f[2]), []).append(round(f[0], 2))
for (kind, s), ts in seen.items(): print('FAULT %s: "%s" at %s s' % (kind, s[:40], ts[:6] + (['...'] if len(ts) > 6 else [])))
print('layout faults', len(seen))
# reading time: seconds at full strength per caption, against 3.5 words a second
for a, b, s in teg2.CAPTIONS:
    full = (b - (a + (teg2.FADE if a > 0 else 0)) - (teg2.FADE if b < teg2.T_END else 0)); words = len(s.split())
    print('caption %5.1f-%5.1f s: %2d words, %.1f s at full strength, %.1f words/s%s' % (a, b, words, full, words / full, '  SLOW TO READ' if words / full > 3.4 else ''))
m = M.measured(); print('numbers from the drawn curve: R %.2f min, K %.2f min, alpha %.1f deg, MA %.1f mm, LY30 %.2f%%' % (m['R_min'], m['K_min'], m['alpha'], m['MA'], m['LY30']))
print('phone size of the smallest text: %.2f pt (24 px)' % (24 * 390 / 1080))
if len(sys.argv) > 1:
    V = sys.argv[1]
    print(subprocess.run(['ffprobe', '-v', 'error', '-show_entries', 'stream=codec_name,profile,width,height,pix_fmt,r_frame_rate,nb_frames,color_space,color_transfer,color_primaries,color_range:format=duration,size', '-of', 'compact', V], capture_output=True, text=True).stdout.strip())
    d = open(V, 'rb').read(); print('faststart:', d.find(b'moov') < d.find(b'mdat'))
    DEC = ['-vf', 'scale=in_color_matrix=bt709:in_range=tv:out_range=pc:flags=accurate_rnd+full_chroma_int,format=rgb24', '-f', 'rawvideo', '-']
    def grab(i):
        buf = subprocess.run(['ffmpeg', '-v', 'error', '-ss', '%.4f' % ((i - 0.4) / FPS), '-i', V, '-frames:v', '1'] + DEC, capture_output=True).stdout
        return np.frombuffer(buf[:1080 * 1350 * 3], np.uint8).reshape(1350, 1080, 3)
    f0 = grab(0); g = tuple(int(x) for x in f0[1240:1270, 20:60].reshape(-1, 3).mean(0)); c = tuple(int(x) for x in f0[1300:1340, 10:40].reshape(-1, 3).mean(0))
    print('colour as a phone shows it: ground %s (app 122, 31, 61), footer %s (239, 233, 220)' % (g, c))
    import cv2
    last = grab(N - 1); det = cv2.QRCodeDetector()
    for k, y0 in enumerate((250, 440)):
        crop = np.ascontiguousarray(last[y0 - 10:y0 + 140, 848:1000][:, :, ::-1]); val = det.detectAndDecode(crop)[0]
        print('QR %d read from the encoded last frame: %s' % (k + 1, val or 'NOT READ'))
    # motion census on the decoded stream: largest single-frame change, and where it happens
    p = subprocess.Popen(['ffmpeg', '-v', 'error', '-i', V] + DEC, stdout=subprocess.PIPE); prev = None; steps = []; i = 0
    while True:
        buf = p.stdout.read(1080 * 1350 * 3)
        if len(buf) < 1080 * 1350 * 3: break
        f = np.frombuffer(buf, np.uint8).reshape(1350, 1080, 3).astype(np.int16)
        if prev is not None: steps.append((float(np.abs(f - prev).mean()), i))
        prev = f; i += 1
    p.wait(); steps.sort(reverse=True)
    print('decoded frames', i, '| largest frame-to-frame changes (mean level, frame):', [(round(a, 2), b, round(b / FPS, 2)) for a, b in steps[:6]])
    print('first frame has content (not a blank):', float(f0.std()) > 10)
```

## C89-C91, the v22 to v24 calls (his "3 then 4", "Continue", then "Is the Plot section foolproof?" and "Let's close that gap")

C89. PLOT YOUR OWN TRACE (v22). A fourth landing tab, Plot, between Drill and Read order (tabs are now
     Terms / Drill / Plot / Read order / Sources; the tab row's gap drops to 12 px under 360 px so five
     tabs fit a 320 px screen). The screen: an instrument toggle (ROTEM / TEG), an assay row (C91), a
     population row of eight (the six Oswald age bands, adult, labour; adult is the default), and the
     fields CT s, CFT s, A10 mm, MCF mm (or R min, K min, MA mm on TEG), 16 px type so an iPhone does not
     zoom them, 44 px tall, numeric keypad. The figure opens on the population's median drawn faint with
     its published ranges as brackets and no marks. Once CT, MCF and either CFT or A10 are typed the
     reader's trace is drawn beside it with CT, MCF and the typed CFT or A10 marked and printed as typed
     (series.pubv, an inline published-values hook in figure(); cards are untouched), a table lists each
     typed number, the population's published range for it and below / within / above, outside verdicts
     in the accent, and a summary line counts them. Curve rule: an A10 typed means the curve is drawn
     through CT, A10 and MCF by the engine's amplitude fit and the line says what clot formation time
     the curve gives (a typed CFT then prints in the table only, with the derived one named beside it,
     as the Song and Nakayama notes do); no A10 means the exponential through CT, CFT and MCF.
     Validation: CT and CFT 10 to 2,400 s, MCF 3 to 90 mm, A10 above 2 mm and below the MCF, a CFT with
     a maximum of 20 mm or under refused with "type A10 instead", each with a plain line in the accent
     and nothing drawn. Window 30 min, or 60 min when CT + CFT + 10 min pass 25 min; the firmness axis
     is sized to hold the typed maximum, the median and the range bracket (80 mm, or 90 when any passes
     76; a v24 fix, C91). TEG: R and K typed in minutes, drawn in seconds and printed in minutes on the
     marks (state.tegMin, plot only; the normal card's TEG tab still prints seconds), the faint
     comparator is the range-midpoint curve the normal card already draws (CT 360, CFT 150, MCF 64,
     labelled ILLUSTRATIVE), the brackets and the table use Srivastava's classic-device kaolin ranges
     (R 4-8 min, K 1-4 min, MA 55-73 mm; claims.json S3.T2.kaolin gained R_s 240-480 and K_s 60-240
     for the time axis), the population and assay rows hide, and the note says no TEG median was read
     and that TEG and ROTEM numbers are not interchangeable (Venema 2010, cited in Curry 2018). The
     intro carries the scope line (recognition aid, ranges set locally, nothing typed leaves the page);
     the note names the population, the assay and its source; a Sources line (Oswald, Lang, de Lange,
     Srivastava, Venema) opens the Sources tab. Layout follows C88: one column under 960 px in the
     order figure, table, note, instrument, assay, population, fields, hint; two columns from 960 px
     with the figure and table left and the controls right. Data in cards.py as PLOT (intro,
     populations with claim keys per assay, the TEG block, the hints, sources), shipped as cards.json
     "plot". Gates: gate_build 23; gate_ui (the tab, the empty opening, the typed set 120/200/45 flagged
     above/above/below against the register's adult ranges recomputed in Python, the within set, the
     A10 path through its A10 within 0.3 mm, the four refusals, the 60-minute window, every
     population's median and note, the TEG toggle's fields, marks, brackets and flags, the return to
     ROTEM clearing the fields, no storage, the Sources link, the layouts at 390, 820, 1180 and 1366
     px); stress measures the plot states at every width; overflow and monkey cover the screen, the
     monkey typing blanks, negatives, 99999 and letters into the fields.
C90. THE READ ORDER (v23). A fifth landing tab, Read order: three walkthroughs chosen by a chip row,
     child on bypass (five steps), postpartum (four) and adult cardiac (four), each with an intro line
     naming the algorithm, its entry condition and its sources. Each step prints "Step k of n", draws an
     existing card state with its legend (or a diagram state), asks what is read or given next, and
     offers four options shuffled per step with a fixed seed; a tap locks the options, a right tap fills
     the chip and the reveal opens "Yes.", a wrong tap strikes the chip, outlines the accepted answer and
     opens "Not this one. It is ..."; the reveal names the trigger with its number, its source and its
     evidence type (one centre's retrospective series, the randomised trial, the before-and-after series,
     the multicentre trial, the BSH grade). Then "Open the card" (the card carries "Back to the read
     order" and returns to the same step with the reveal on screen, the drill's C85 path generalised:
     backTo replaces fromDrill) and "Next" or "Finish"; the finish prints the first-tap score, a "First to
     last" recap built from the accepted answers, and "Again". The three orders and their states:
     CHILD (Faraoni 2015 Fig 6, with Nakayama 2015 Fig 1B at each step): 1 the four checks before the
     trace (hypothermia card, "the trace" state; the checks diagram was the first choice and was
     replaced because it printed the answer), 2 the heparinase ratio (heparin, "at the protamine
     trigger"), 3 FIBTEM A10 3 mm (bypass, "FIBTEM, before and after", Nakayama's cohort at 3.6 mm),
     4 EXTEM A10 38 mm with FIBTEM above 3 (bypass, "at Faraoni's triggers", ILLUSTRATIVE climb
     labelled as on the card), 5 EXTEM CT 111 s (factor-deficiency, "child after bypass").
     POSTPARTUM (Mallaiah 2015 Appendix 2, with the BSH grades): 1 EXTEM CT over 100 s (numbers, "CT"),
     2 FIBTEM A5 under 7 with EXTEM A5 under 47, 2C, the A5 at 10 minutes and the Clauss at 65
     (obstetric, "7 mm"), 3 above 12 mm with a normal EXTEM, no products, 2B, tranexamic acid 1B
     (obstetric, "19 mm"), 4 a low EXTEM with a normal FIBTEM, platelets, with Riddell's 5% under 75
     (low-platelets, "EXTEM and FIBTEM"). ADULT CARDIAC (Karkouti 2016 Fig 2 thresholds as the headline,
     Weber 2012 Fig 1 and Görlinger 2011 Fig 1 as the single-centre versions; the sequence stated as
     the single-centre algorithms' - residual heparin, fibrinogen, clotting factors, platelets - with
     the multicentre trial's ACT-within-10% entry condition, since Karkouti's Fig 2 lists its three
     triggers side by side; Essen's lysis step, CLI60 under 85% for tranexamic acid 2 g, is named in the
     intro and not asked): 1 residual heparin (heparin, "heparin 0.1 U/ml, in vitro"), 2 FIBTEM A10 8 mm
     (bypass, "adults, FIBTEM", Weber's 6 then 10 mm points), 3 EXTEM CT 90 s (factor-deficiency, "adult
     cardiac, 90 s"), 4 EXTEM A10 35 with FIBTEM over 8 or a functioning count under 75 (low-platelets,
     "EXTEM and FIBTEM"). Every number is already in the register; no new source and no card changed.
     Data in cards.py as READ (id, label, sources, intro, steps of card / state / ask / options with the
     accepted answer first / reveal) and READ_INTRO, shipped as cards.json "read" and "read_intro".
     Gates: gate_build 24 (three settings of three or more steps, every step a real card and state, four
     distinct options led by the accepted answer, a question mark, a reveal under 110 words ending in a
     citation that names one of the setting's sources, intros likewise, no picture repeated on more than
     two steps, texts clean of S-keys, em dashes, the banned words and the tells); gate_ui (the tab
     opening on the first setting at step 1, every step's figure, options, 44 px targets, the right and
     the wrong tap, the locked options, the citation, the way on, the finish with score and recap, the
     full run of every setting with Next between steps and its score, Again restarting at step 1, the
     setting chip switching intro and steps, Open the card and the return to the same step, the landing
     back button unchanged afterwards, the Sources link, no storage, the landing after a reload, the
     layouts at the four widths); stress measures all 13 step figures at every width; overflow and
     monkey cover the screen. His verdict on the two screens from the phone is still open.
C91. THE ASSAY ROW (v24), on his "Let's close that gap" after the answer to "Is the Plot section
     foolproof?" (the gap: the flags were EXTEM-only, so INTEM numbers were judged against EXTEM ranges
     and a normal INTEM clotting time of 180 s read "above"). An Assay row under Instrument: EXTEM /
     INTEM / FIBTEM, EXTEM by default, hidden on TEG. Each population now carries a claim key per assay
     (S1.T3.<band>.EXTEM and .INTEM, S1.T4.<band>.FIBTEM; the three de Lange labour rows) and the median,
     the brackets, the table's ranges and the note follow the assay chosen. INTEM uses the same fields
     and rules as EXTEM. FIBTEM has its own fields, CT s, A10 mm, MCF mm, with MCF required (1 to 60), CT
     optional (10 to 2,400 s) and A10 optional (0.5 mm to the MCF); the curve is the engine's fibrin
     shape from CT and MCF, beginning at the labour median's 39 s when no CT is typed, and the line says
     so; a typed A10 prints as typed at the curve's own A10 position, as the cards do. Oswald publishes no
     FIBTEM clotting time or clot formation time, so a typed FIBTEM CT on any population but labour is
     listed with "no range" and the summary line says no FIBTEM CT range is published for that
     population; the summary counts only the numbers that had a range. FIBTEM draws on a 40 mm firmness
     axis, or 80 when the typed maximum, the median or the range bracket passes 36 mm. FAULT FOUND AND
     FIXED on the way: the labour FIBTEM MCF range reaches 45 mm, and on the 40 mm axis the bracket
     ran into the label lane and its label landed on it (stress at 402 px); the axis is now sized to
     the range bracket as well as to the typed and median maxima, for every assay (class rule). Switching
     assay clears the fields only when the field set changes (EXTEM to INTEM keeps the numbers; to or
     from FIBTEM clears them). Data: PLOT.assays, populations carry "claims" per assay and "who" with an
     {assay} placeholder, hint_fibtem and fib_ct_line. Gates: gate_build 23 now checks all three assay
     rows per population (medians and ranges in the register), the assay list, the placeholder and the
     39 s line; gate_ui checks the row, INTEM 180/70/60 reading within against the INTEM ranges with the
     INTEM bracket, the FIBTEM fields, median, hint, axis, flags, the 39 s line, the marks, the
     above-MCF refusal, the no-range report, the labour FIBTEM CT range and the return to EXTEM; stress
     measures an INTEM set on every population and FIBTEM sets on every population with the widest on
     0-3 m and labour; overflow covers a labour FIBTEM state; the monkey taps the assay chips. TEG stays
     kaolin-only, said in its note; lysis is still not typed, so the plot never flags hyperfibrinolysis.
Also this thread: the acronym-safe lowercasing in the read-order verdicts and recap (lc1); stress.py's
chrome contrast check now covers the drill, plot and read-order type; the sweep is run in three parts
because all nine widths in one command pass the container's five-minute limit.

## C74-C88, the v12 to v21 calls (his: "Any changes you'd suggest before we go to GitHub?" then "Name is settled")

C74. Preview metadata for the public address: og:url https://gundoc9.github.io/reading-the-clot/,
     og:image and twitter:image absolute (…/reading-the-clot-card.png; LinkedIn does not resolve relative
     image paths), og:description and twitter:description now the link card's own line ("The TEG and
     ROTEM trace, normal beside abnormal, with what to give for each defect."; they had read "a dictionary
     … one term per card" since v1). If the repository is ever renamed these three lines change with it.
C75. The two typefaces are embedded: fonts.py subsets Lora (400, 500, 600, italic 400) and Poppins
     (400, 500) to the 208 characters the app uses and writes fonts.css (@font-face data URLs, WOFF,
     161 KB); build.py injects it at /*__FONTS__*/ and the Google Fonts links are gone. The landing's
     "Nothing leaves your device" is now true, the home-screen app works offline, and gate_build check 12
     asserts no external script, link, CSS url or image and six @font-face rules; check 12b asserts the
     absolute image address, og:url and the matching description. README wording updated. Side effect
     worth knowing: the container's system fonts rendered Poppins about 3% narrower (hinted advances)
     than the phone does; the embedded fonts render at the phone's widths, so the sweep now measures
     what the phone shows. One collision surfaced that way (C76).
C76. On the seven-tick time axes (30 and 60 min windows) the label before the last one ("50", "25")
     sat within 1 to 3 px of "60 min" / "30 min" at every phone width and overlapped at 360 px; that
     tick keeps its mark and loses its number. Class rule in the template: ticks.length >= 7.
C77. Five of the six new sources carry their titles, each verified by web search on the DOI record
     this thread (Görlinger 2011, Larsen 2011, Adelmann 2026, Dias 2025, Wikkelsø 2017).
C78. Shah 2026's title, from the PDF he attached after v12: "Platelet function in patients undergoing
     major non-cardiac vascular surgery (PLUGS): a prospective cohort study", Anaesthesia 2026;81:1236-1244,
     authors Shah A, Polley G, Bera K, et al. The PDF's Table 2 confirms the platelet-dysfunction card's
     Shah sentence (resistance 6 of 20 on aspirin, 14 of 20 on clopidogrel; eight patients retested after
     stopping clopidogrel with no significant change). He also attached Wikkelsø 2017, whose summary
     confirms the evidence card's numbers (deaths 3.9% v 7.4%, RR 0.52, 0.28-0.95, 8 trials, 717
     participants, low quality; red cells RR 0.86, 0.79-0.94). All 29 sources now print a full citation.
C79. After the upload, the live page's plain <meta name="description"> still read the v1 wording ("A
     dictionary … one term per card"), the line search engines print; v12 had fixed only the og and
     twitter descriptions. v14 sets it to "The TEG and ROTEM trace for anaesthetists, normal beside
     abnormal, with what to give for each defect. Every picture is computed from published medians and
     thresholds." and gate_build 12b now asserts all three descriptions carry the link card's phrase and
     none carries the v1 one. To go live he uploads the new index.html over the old (Add file > Upload
     files, Commit changes); nothing else in the repository changes.
C80. Kvisselgaard 2025 (Acta Anaesthesiol Scand 69:e70127, the authors' rapid revision of their 2025
     update after a discrepancy in the mortality patient numbers; he attached the PDF, read in full)
     is S32 and replaces Wikkelsø 2017 on the evidence card: the diagram row is now "Cochrane 2025"
     with deaths RR 0.76 (0.63-0.92) in 19 trials and RR 0.90 (0.72-1.12) in the 4 low-risk trials
     (threshold Kvisselgaard_outcomes carries the rest: 35 RCTs, 20 cardiac, red cells RR 0.94
     (0.87-1.01), FFP 0.52, platelets 0.69, re-operations 0.63 with the TSA information size reached,
     bleeding SMD -0.31, GRADE very low throughout, TSA 64%, ITACTIC and Kumar 2020 carrying 69% of the
     mortality weight and both null); the entry's last sentence and the guidelines note say so, and
     Wikkelsø 2017 stays in the sources as the result it replaces. The paper's own inconsistencies
     (3,096 patients in the abstract, 3,207 in the discussion; TSA 64% in the text, 61% in Table 1) are
     recorded in the claims src note and print nowhere. This is the paper the launch post may hang on
     (his call still open; Shah 2026 and Adelmann 2026 remain the alternatives), with the app in the
     first comment, never a link in the caption body.
C81. Riddell 2026 (Br J Anaesth 137:545-562, the Cardiff OBS group's narrative review of obstetric against
     trauma coagulopathy; he attached the PDF, read in full, numbers in HANDOFF-clot-papers-2.md section 1)
     is S33, "Read in full", on three cards. Obstetric card, "also" paragraph: coagulopathy is uncommon early
     in PPH (97% normal PT/aPTT at 1 L, normal to 3-4 L; fibrinogen under 2 g/L 2.4% at 1 L and 17% above
     2.5 L; platelets under 75 5% above 2.5 L), about half of it acute obstetric coagulopathy (plasmin,
     abruption, amniotic fluid embolism, fibrinogen given may do less than expected, the trace repeated),
     FIB-PPH and FIDEL null in 686 women of whom ten had a low fibrinogen, OBS UK due early 2027; the source
     is labelled on the card as a narrative review from the OBS group citing its own cohorts.
     Hyperfibrinolysis card, "also": the plasmin-driven obstetric form breaks down circulating fibrinogen and
     its products block new fibrin, so the fibrin-only trace is repeated after fibrinogen. Evidence card,
     trials note: OBS UK's date. Threshold Riddell_PPH carries the numbers with page references. Nothing in the
     figures changed. This is the paper the launch post hangs on (his "Go for both": v16 and the caption).
     Open query from Van de Velde 2026: OBS2 is 57 women there and 55 on the card; check Collins 2017 (S9)
     before changing either.
C82. FAULT FOUND BY THE 23 Sep STRESS TEST, class: resolve.js ran the engine with engine.js's placeholder
     constants (K_ALPHA 13.6, FIBTEM shape 0.69/45/600) while the shipped app runs on fit.json's (11.4,
     0.58/30/500), so every FIBTEM curve solved to a threshold A5 was 0.3 to 0.9 mm under it when the
     shipped engine drew it, and the obstetric card's 19, 15, 13 and 12 mm chips printed A5 18, 14, 12
     and 11. The eye caught it on the contact sheets; the gates had not, because the threshold check only
     asked whether the threshold value existed. resolve.js now loads fit.json before resolving, and
     gate_engine has a new check for every threshold-derived series (fibA5, fibA10, extA5, extA10): the
     drawn amplitude at the threshold's own time equals the threshold within 0.5 mm (768 checks; it
     failed the four obstetric states on v16 and passes v17). The 7 mm state and every EXTEM threshold
     were within rounding and unchanged in print.
C83. His 18 Sep word rule applied to the app text: "sit" and "sits" removed from the bypass adults-FIBTEM
     note and the evidence guidelines note (no "floor" existed). Register only: Collins 2014's 356 women
     and the 686 of FIB-PPH plus FIDEL, both already on the obstetric card, now have threshold entries
     (Collins2014_cohort, Riddell_PPH), so every number in the card text is declared. Also checked on
     23 Sep: every number in every entry, note, box and table against claims.json (two undeclared,
     above, both correct); every source's check status; Oswald's 37 °C tube warming and Wells's 20 to
     500 Hz against the OCR texts; the labour MCF range 42 to 78 against de Lange; all 67 states by eye
     on contact sheets; the six-width sweep, overflow and a 600-action monkey run, all green.
C84. THE DRILL (v18), the first of the five educational additions proposed 23 Sep, on his "Let's try it".
     A third landing tab, Terms / Drill / Sources, opens a drill screen: seventeen items, each a sourced
     state of an existing card drawn blind (the same figure with its legend removed; lane labels and
     brackets stay, since readings are part of reading), a one-line stem giving only the clinical context
     and the sources, then "Which card is this?" with four cards (the item's own plus three distractors)
     and, where the card has a What-to-give box, "What would you give?" with four products. A wrong tap
     is struck through, the accepted answer outlined, and the verdict carries the item's "why" line. Some
     items accept two cards where the trace alone cannot separate them (a long EXTEM wait after cardiac
     surgery: factor deficiency or heparin, the heparinase test decides; rivaroxaban: anticoagulants or
     factor deficiency; the 7 mm FIBTEM: obstetric or low fibrinogen) and each item lists cards a fair
     reader might also pick, which are never offered as distractors (the bypass card for a child after
     bypass; the three normal-trace cards for each other). Order is shuffled per session, options are
     shuffled by item so they are stable for the gates, "Open the card" goes to the card, the score is
     first-tap right out of seventeen, and nothing is stored. Items live in cards.py as DRILLS (card,
     state, stem, answers, why, exclude) and ship in cards.json. Gates: gate_build 20 (every item a real
     non-ILLUSTRATIVE, non-points, non-diagram state; answers real cards led by the item's own; exclusions
     disjoint from answers; three distractors left; stems and why lines free of S-keys, em dashes, the
     banned words and the paired-contrast skeleton), gate_ui (the tab order, four distinct options with
     the item's answer among them, 44 px targets, the verdict, the second question, Open the card, the
     score with the window hidden, and the app still opening on the landing after a reload), stress.py
     measures all 17 drill figures at every width, monkey taps the drill. Not built, in his order: plot
     your own trace against the matched normal; the read-order walkthroughs per setting; the time-to-
     decision clock; the "what people get wrong" line per card.
C85. His first use of the drill on the phone (23 Sep, "Seems to be ok. So you have to go back 2 steps to
     tap Drill after each question?"): "Open the card" left the drill with no way back except All terms
     and the Drill tab, which starts a new run. Now a card opened from the drill carries "Back to the
     drill" in place of "All terms" and returns to the same item with its verdict still on screen; a
     card opened from the landing keeps "All terms". Related links and prev/next inside a card opened
     from the drill keep the drill return. gate_ui checks both back labels and the return to the same
     item. Nothing else changed.
C86. WHAT PEOPLE GET WRONG (v20). One sourced line per card, in an accent-ruled block after the analogy,
     drawn from the errors this build found and the ones the sources warn about: LY30 read as LI30
     (numbers); a TEG 6s amplitude taken as a cup-and-pin one (trace); a threshold carried across
     instruments (names); a normal INTEM of 184 s read as a slow clot (assays); a baby or a labouring
     woman judged on the adult range (normal); a narrow EXTEM called low fibrinogen without FIBTEM
     (low fibrinogen); the guideline's 27 mm read as an A5 (low platelets); a labouring woman's 41%
     lysis called pathological (hyperfibrinolysis); plasma for a long wait before heparinase and FIBTEM
     (factor deficiency); INTEM judged on its range when HEPTEM is there (heparin); a normal trace
     clearing aspirin or clopidogrel (platelet dysfunction); expecting the trace to show the cold
     (hypothermia); a normal trace read as no anticoagulant (anticoagulants); the pre-protamine trace
     treated as a coagulopathy (bypass); fibrinogen above 12 mm (obstetric); components for a bleeding
     patient with a normal trace (normal-bleeding); the quarter fewer deaths (evidence). Text lives in
     cards.py as WRONG, attached to each card as "wrong". Gate 21: present on every card, under 60 words,
     ends in a citation naming a source the card carries (Oswald and Lang joined the assays card for
     it), no S-keys, banned words or tells; gate_ui checks the block follows the analogy.
C87. THE CLOCK (v20). On every chips or tabs card without its own time slider, a row under the chips:
     "The trace at 5 min · 10 min · 20 min · full". A stop draws the curve only that far (the existing
     partial-draw path), hides the marks the run has not reached, blanks every readout the run has not
     reached (CT if not yet clotted, CFT if the climb is unfinished, A5, A10, A20, the maximum, lysis),
     and prints one line on what that stop allows: five minutes, the clotting time and A5 (Curry 2018
     BSH, Wells 2022); ten minutes, A10 and the cardiac and paediatric triggers, with the litre a
     100 ml/min bleed loses in the wait (Milewski 2025, now S34, the thirty-second source, read in full,
     on the numbers card); twenty minutes, A20 with lysis still needing the 30-minute index (Larsen
     2011). "full" restores the run; a chip change resets to full; the 20-minute stop is greyed on
     15-minute windows; the row hides on diagram states. Lines live in cards.py as CLOCK and ship as
     "clock". Gates: gate_build 22 (stops 300/600/1200/full, lines cite listed sources, no tells);
     gate_ui (stops, active state, shortened trace, blanked readouts, restore, hidden on diagrams);
     stress measures the 5 and 10 minute figures of every chips card at every width; monkey taps it.
     FAULT FOUND AND FIXED on the way: under Reduce Motion the opening draw's 500 ms timer was not
     cancelled by a tap, so a chip or clock stop chosen in the first half-second was undone when it
     fired; stopAuto now clears it, and gate_ui runs a reduced-motion page to prove it.
C88. THE LAYOUT FOR EVERY SCREEN (v21), his "Go" to "will this be screen-optimised for whichever device
     it is opened on". Three bands, one file, nothing to choose: under 700 px the phone column exactly as
     before (440 px, unchanged pixels); from 700 px a single column widened to 620 px, which is an iPad
     held upright, so the figure grows past phone size; from 960 px the card and the drill split into two
     columns 40 px apart inside an 1120 px frame (left: figure, readouts, chips, clock, note; right:
     the table, the What-to-give box, entry, analogy, what-people-get-wrong, sources, related, prev and
     next), the landing list runs in two columns, the card title goes to 34 px and the sources list is
     capped at 720 px for reading. Done by wrapping the card and drill contents in two column divs
     (cols/col) so the phone DOM order is unchanged and every existing selector still holds. Gates:
     gate_ui opens 390, 820, 1180 and 1366 px pages and checks one column against two for the card and
     the drill, a figure at least 300 px wide, and no sideways scroll; the sweep now runs at 820, 1024
     and 1366 px as well (0 hard faults at all nine widths). README carries the line.

## 1. Calls made in v10 (same thread)

C54-C64 were made as proposed in HANDOFF-clot-v9-papers.md section 1, with these amendments:

C54 (Larsen 2011). Every Larsen row draws through all four of its published numbers (CT, CFT, A10,
     MCF) once A10 is read after CT (C65); no derived CFT was needed, so the derived-CFT gate does not
     apply to Larsen. Abnormal rows carry alpha_published (not drawn); normal, APTEM, HEPTEM and
     heparin-EXTEM rows carry alpha and are gated. The four chips: low-fibrinogen "dilution, in vitro"
     (undiluted faint, diluted EXTEM, FIBTEM at 1.9 mm), low-platelets "platelets 20, in vitro",
     hyperfibrinolysis "tPA, in vitro" (EXTEM with APTEM dashed; LI30 and ML in the compare table),
     heparin "heparin 0.1 U/ml, in vitro" (INTEM 351 s, HEPTEM 162 s). They replaced the ILLUSTRATIVE
     chips "EXTEM" (low-fibrinogen), "against normal" (low-platelets) and "more heparin" (heparin).
     Notes say "In vitro model, healthy donors, n = 11 (Larsen 2011, Table 2)".
C55 (Weber 2012). The Table 3 medians print as POINTS on the bypass card: "adults, EXTEM" (CT 97 and
     A10 42 at enrolment, filled; CT 74 and A10 48 after treatment, hollow) and "adults, FIBTEM" (A10
     6 then 10), each over the child's after-bypass curve as the shape (C68). Trials chip line carries
     the six-month deaths, 4% v 20%.
C56, C57. The Frankfurt, Essen and multicentre trigger sets sit in a new "adults" paragraph of the
     What-to-give box (rendered between the paediatric trigger and the "also" paragraph) on the
     low-fibrinogen, low-platelets, factor-deficiency, heparin and bypass cards. Görlinger's
     fibrinogen table is labelled a practice rule from 2006. The factor-deficiency card gained the chip
     "adult cardiac, 90 s" (EXTEM CT at the Karkouti trigger, rest of the curve at the adult median).
C58 (Mallaiah). The obstetric box's adults paragraph is Mallaiah's own algorithm with its outcome
     numbers; the "not read" tag is gone from the factor-deficiency card.
C59 (Seyve). Placed on the ANTICOAGULANTS card, not the clotting-time card, because the card exists and
     its two chips were ILLUSTRATIVE: they are replaced by "rivaroxaban 200", "dabigatran 200",
     "edoxaban 100", "apixaban 1,000", each with the donors' own blood (or the adult median where Seyve
     printed no baseline CFT) faint beside the drug row and the adult CT range bracket. Entry and box
     rewritten from Seyve. The Seyve rows carry alpha_published: the published angles sit 5 to 7
     degrees above the engine's 2 mm tangent, and are not drawn.
C60 (Adelmann). TEG 6s note on the trace card (heparinase channel up to 5 IU/ml); TEG side of the
     heparin box (analysable maximum amplitude 56% without heparinase, 95% with); the TEG kaolin tab
     on the normal card now carries the TEG 6s citrated-cartridge ranges as its brackets, labelled
     "R, TEG 6s" and "MA, TEG 6s" (CLAIMS.teg['S28.F2.TEG6s.citrated']; R printed in minutes).
C61 (evidence). The guidelines diagram was rewritten (viewBox 360x292): NICE, BSH 2018, ESAIC 2022,
     Cochrane review (Wikkelsø 2017, from Wikkelso_outcomes) and Elective surgery (Dias 2025, from
     Dias_outcomes), two-line rows. Trials note and entry updated.
C62 (Shah). The sentence sits on the PLATELET-DYSFUNCTION card's "also" paragraph, its subject, not
     on low-platelets as proposed.
C64. S-numbers: S26 Görlinger 2011, S27 Larsen 2011, S28 Adelmann 2026, S29 Dias 2025, S30 Wikkelsø
     2017, S31 Shah 2026. Weber, Karkouti, Mallaiah and Seyve are "Read in full".

New calls:

C65. A5, A10 and A20 are read 5, 10 and 20 min AFTER CT, the ROTEM definition and what the cards'
     key line prints; v9 read them from the start of the test. This was the cause of the C44
     inconsistencies. Every consumer moved: engine (amplitudeFit, singleParams, fibForA5, singleForA5),
     resolve.js (fibA10 and extA10 bisections), template (A5/A10/A20 marks, a5thr, trigger lines, the
     a10 bracket, readouts) and gate_engine. Refit: K_ALPHA 11.4 (was 13.32), FIBTEM shape
     w 0.58, tau1 30, tau2 500 (was 0.66/40/550); worst A10 1.5 mm, A20 0.8 mm, alpha 3.6 deg (adult
     INTEM 80.6 v 77). The alpha gate tolerance is 4 deg for that one row (minimax K 10.8 still leaves
     3.1). Nakayama's derived CFT is now 387 s (published 407); Song's is 328 s (published 235): Song's
     A5 median of 19 mm at CT + 5 min cannot sit on the same curve as a CFT of 235 s, so the curve
     follows the amplitudes and the note says so. gate_engine encodes that as a class rule: a row with a
     published A5 under 20 mm is checked for consistency with its A5, every other amplitude-fitted row
     against the published IQR or 30% of the median. gate_build check 19 reads any note that quotes a
     derived clot formation time and matches the number to the resolved p.CFT and the CFT_published.
C66. Lysis is timed to the published LI30: engine lysisEnd() sets the fall so that the width 30 min
     after CT is the published share of the maximum (cap 60 min; ML is still reached), and li30() now
     returns the ROTEM lysis index (residual %, 100 = no lysis), which is what the readouts and the key
     line print ("LI30: the width 30 min after CT as a share of the maximum"). Gate: |li30 - LI30| <= 3.
C67. A FIBTEM clot under 2 mm has no clotting time: fibShape starts the shape at the CT given (the
     donors' untreated 66 s for Larsen's dilution row) and the row carries CT_published 2278 for the
     record; the gate requires CT_published on any row with MCF under 2.
C68. Points rows (claims rows with points: true and A10, no CFT or MCF) resolve to p {CT, A10, points,
     CTpub}, draw as dots at +/-A10 at CT + 600 s (hollow when the series has hollow: true), a CT tick
     on the axis when the CT was published, lane labels from s.short, a dot glyph in the legend, blank
     compare cells for values that do not exist. A FIBTEM points row with no published CT sits at the
     labour FIBTEM CT of 39 s and the note says so. gate_engine expects exactly four points rows.
C69. The six new sources print author, journal, year, volume and pages only, because the addendum
     carried no titles; titles are to be added from the PDF first pages when those papers are next
     attached. Larsen, Görlinger and Wikkelsø titles were deliberately not written from memory.
C70. A state may carry its own firmness axis (state.ymax): the two FIBTEM-only states on the bypass
     card draw on 0-20 mm because on the shared 80 mm axis the 6 and 10 mm dots overlapped and the
     11.6 v 4.2 mm pair was two lines a few pixels apart. Only those two states use it. One word
     reverses it (remove ymax=20 from the two S(...) calls in cards.py).
C71. The time-axis bracket bar sits at y1 + 5 (was + 7): at 360, 390 and 768 px its lower edge was
     0.3 px above the "5 min" tick label's glyph box on the TEG kaolin tab. Class fix, all brackets.
C72. Entry trim on low-platelets to stay at the 80-word cap: "the clotting time holds".

Reversals so far: none. He has not yet reviewed v10 card by card; v11 was built on his "Go" to the assays card.

## 2. What each card gained (diff of cards.json v9 to v10)

- trace: TEG 6s note (heparinase channel); source Adelmann.
- normal: TEG kaolin tab brackets are the TEG 6s ranges, note updated.
- low-fibrinogen: chip "dilution, in vitro" (replaces "EXTEM"); entry rewritten; adults box paragraph
  (Karkouti, Weber, Görlinger 2006 rule, Mallaiah); sources + Mallaiah, Weber, Karkouti, Görlinger, Larsen.
- low-platelets: chip "platelets 20, in vitro" (replaces "against normal"); "liver, the medians" note
  now quotes 328 s and explains it; entry rewritten; adults paragraph; same five sources added.
- hyperfibrinolysis: chip "tPA, in vitro"; Essen CLI60 line in "also"; sources + Görlinger, Larsen.
- factor-deficiency: chip "adult cardiac, 90 s"; box "when" and adults paragraphs; Mallaiah tag removed;
  sources + Weber, Karkouti, Görlinger.
- heparin: chip "heparin 0.1 U/ml, in vitro" (replaces "more heparin"); adults paragraph; Adelmann TEG
  line in "also"; sources + Weber, Görlinger, Larsen, Adelmann.
- platelet-dysfunction: Shah sentence in "also"; sources + Karkouti, Görlinger, Shah.
- anticoagulants: four DOAC chips (replace "warfarin and three DOACs" and "apixaban"); entry, "when"
  and "also" rewritten from Seyve.
- bypass: chips "adults, EXTEM" and "adults, FIBTEM" (points); "before and after bypass" note quotes
  387 s; the two FIBTEM states on a 0-20 mm axis (C70); adults paragraph and "also"; sources + Weber,
  Karkouti, Görlinger.
- obstetric: adults paragraph (Mallaiah's algorithm); source + Mallaiah.
- evidence: entry, both notes, the guidelines diagram; sources + Dias, Wikkelsø.
- Sources tab: Weber, Karkouti, Mallaiah, Seyve now "Read in full"; six new entries (C69).

## 3. Engine and gate state (supersedes the engine sections of the v2 and v9 handoffs where they differ)

- engine.js: single curve A(t) = MCF(1 - exp(-((t - t0)/tau)^k)); A(CT) = 2, A(CT + CFT) = 20;
  A10 fitted at CT + 600 (k), or amplitude-anchored through A(CT + 300) = A5 and A(CT + 600) = A10 for
  rows flagged fit: 'amplitude' (Song, Nakayama post). FIBTEM two-term shape, t0 solved for A(CT) = 2,
  or t0 = CT when MCF <= 2. Lysis: plateau x (1 - ML/100 smoothstep), fall timed by lysisEnd (C66).
  alpha = atan(K_ALPHA x slope at CT). Constants are injected by build.py from fit.json; the literal
  in engine.js is a placeholder.
- fit.js: K_ALPHA by least squares over rows carrying CFT and alpha; FIBTEM shape over the S2 FIBTEM
  rows; report to fit.json. Rerun only after adding rows that carry alpha (Seyve and abnormal Larsen
  rows carry alpha_published and do not enter the fit).
- gate_engine.js (768 checks): constants equal the fit; every row recomputed with A5/A10/A20 at CT +;
  alpha within 4 deg; alpha and alpha_published never both; A(CT) = 2 unless MCF < 2 (then CT_published
  required); ML within 0.7; LI30 within 3 when published and under 100; derived CFT per C65; four
  points rows; monotone, lysis and slider checks; every drawn series claimed, threshold-derived or
  ILLUSTRATIVE; brackets resolve to a row range or a CLAIMS.teg range.
- gate_build.py (1641 in v26, 1633 in v25; 13. the film): word caps (entry 80, paragraph 70, analogy 40), voice tells, sources, related,
  twin, restatement, distinct pictures, credentials, scope, skin, script parse, targets, gesture
  ownership, hash navigation, stress at 402 px, quoted numbers, and check 19 (derived-CFT notes), 20 (drill), 21 (what people get wrong), 22 (clock), 23 (plot, every assay and population against the register) and 24 (read order).
- gate_ui.py (837 in v26, 771 in v25, including the film at four sizes, the drill, its return path, the clock, the reduced-motion timer, the three layout bands for the card, the drill, the plot and the read order, the plot's typed sets for every assay against the register recomputed in Python, and the read order's every step). stress.py / sweep.py measure text boxes against drawn edges at six widths;
  monkey.py and overflow.py unchanged.

## 4. Build commands (from clot-v24-source.zip unpacked to /home/claude/src with apply_v25.py and apply_v26.py run inside src/ and the film in src/film/, section R below; sheet.py and shoot paths
   are hard-wired to /home/claude/src, /home/claude/shots, /home/claude/shots-aub, /home/claude/shots-teal)

    cd /home/claude/src
    node fit.js                       # only after adding rows that carry alpha
    python3 cards.py                  # cards.json and repo/SOURCES.md
    python3 fonts.py                  # only after a template or text change adds characters; rewrites fonts.css
    CLOT_VERSION=v26 python3 build.py garnet /home/claude/out/reading-the-clot-v26.html   # dev build
    node gate_engine.js <html>; python3 gate_build.py <html>; python3 gate_ui.py <html>
    python3 sweep.py <html> 320 360 375 390   # then 430 768 820, then 1024 1366: nine widths in three runs, since one run of all nine passes the container's five-minute command limit
    python3 overflow.py <html>; python3 monkey.py <html> 500
    python3 shoot.py <html> /home/claude/shots           # then view every changed state
    CLOT_VERSION=v26 python3 build.py garnet             # final: html, icon, card, clot-repo/ in outputs
    CLOT_VERSION=v26 python3 sheet.py /mnt/user-data/outputs/review-sheet-clot-v26.png

Network is off in the container (no DOI checks, no fetches); the fonts come from /usr/share/fonts/truetype/google-fonts/, which fonts.py reads.

Dr Ganesh Sivasankara · MD · FRCA · FCARCSI · Consultant Anaesthetist
