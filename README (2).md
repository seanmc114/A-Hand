# A Hand.

A Loops Learning Tool: an organiser for Synge Street students (trial prototype).

No server, no logins. Everything is saved on the student's own phone. The QR code maker is built in, so nothing loads from outside except the fonts.

## Files
```
index.html
manifest.webmanifest
icon/icon.png
icon/icon-192.png
icon/icon-512.png
icon/apple-touch-icon.png
```

## Put it online (GitHub Pages)
1. New repo, e.g. `a-hand`.
2. Upload `index.html` and `manifest.webmanifest` to the root, and the four icon files into a folder called `icon`.
3. Settings → Pages → Deploy from branch → `main` / root.
4. Link: `https://<your-user>.github.io/a-hand/`
5. In the app: Settings (gear) → Teacher preview → **App link** → paste that link → Save link. QR codes then point to the right place.

## Sharing the app
Drawers → **Share** shows a QR code of the app link. A student scans it with the phone camera and A Hand opens.

## Making a class deck (teacher)
1. Settings → **Make a class deck**, or Drawers → Practice → "Teacher? Make a class deck".
2. Name it (e.g. *Spanish: food*).
3. Add words, one per line: `el pan = bread`. Up to 40 words.
4. Tap **Make the QR code**. Show it on the board.
5. Students scan it with their phone camera and tap **Add to my Practice**.

"Copy the link" gives the same deck as a link for Teams or email.

## Setting up a student (Day 1)
The first time the app opens: welcome, then **Set up** (3 steps).
1. Scan the class timetable code, or take a photo of his own timetable (projector or printout). The photo stays on the phone and sits above his week while he copies each box. Or fill it in by hand.
2. Your week: tap each class to set subject, room (number pad) and teacher. "Same as Monday" copies a day. "Use this room and teacher for every Maths class" fills the rest.
3. First name (optional), letters, paper colour.

Change it later in Settings → Edit my timetable.

## Making a class timetable (teacher)
Settings → **Make a class timetable**. Fill in the week, name it (e.g. *1st Year A*), then tap **Make the QR code**. Students scan it, tap **Use it**, then change their own option subjects.

Bell times are built in: 8:40 start, break 10:40–10:50, lunch 12:50–1:30. Mon/Tue finish at 3:30 (9 classes), Wed–Fri at 2:50 (8 classes). They're in `P_ALL` and `BREAKS`.

## Teacher preview
Settings (gear, top right):
- Open every drawer
- Clock: Real time / In class (Wed 10:30) / At home (Wed 19:30)
- Show the welcome, Bring the signs back
- Start fresh (wipe all)

## Where to swap content
In the last `<script>` of `index.html`:
- `TT` and `PERIODS`: sample timetable
- `WORDBANK`: general word bank (swap in the school list)
- `EXAMWORDS`: command words, meanings, examples
- `TYPES`: task types, steps and minutes
- `SIGNS`: page signs
- `DRAWERS`: medals needed to open each drawer
- **LOOPS ENGINE SEAM**: `playDeck` / `answer` / `nextCard` are a simple spaced-repetition game. Swap in the Loops engine there. It gets a deck `{name, cards:[{f,b,box,due}]}`, updates `box`/`due` per card, then calls `practiceDone()`.
