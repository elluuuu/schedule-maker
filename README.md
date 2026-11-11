# Weekly schedule maker

A one-page web tool for making weekly event schedules as images for Instagram and Telegram. You enter the week's events, check the preview, and download PNGs. It runs entirely in the browser: no install, no account, no server.

Built for Ukrainian help centres in Finland, but any centre can use it. The interface is in Ukrainian and English, and the text on the images can be changed to any language.

## Using it

1. Open the tool's link (see "Putting it online" below).
2. Under **Тиждень / Week**, set the Monday of the week, which days are open, and the opening hours.
3. Under **Щоденні послуги / All-day services**, list services that run all day, such as information or psychological support. These go on the cover image.
4. Under **Події / Events**, pick a day tab and add events. Each event has a start and end time, a name, a category, an optional room, an optional note (for example "діти 6–13"), and an optional label for "registration needed" or "group full". Tick ≈ for approximate times.
5. Check the warnings above the preview. The tool flags missing names, bad times, events outside opening hours, and duplicates.
6. Choose **Instagram 1080×1350** or **Telegram 1080×1920**, then download all images as a ZIP or one at a time.

Events are sorted by time automatically and split across as many images as needed. Tick **За приміщеннями / By room** for a day to group its events by room, for example by floor.

## Saving and sharing a week

Everything you type is saved in your own browser, so it is still there when you come back on the same computer.

To keep a copy or hand the schedule to a colleague, use **Зберегти файл тижня / Save week file**. It saves a `.json` file that anyone can open in the tool with **Відкрити файл тижня / Open week file**.

**Наступний тиждень / Next week** moves the dates forward 7 days and keeps the events, since many repeat each week. Edit what changed and download.

## Logos

Logos are uploaded in the tool under **Вигляд і логотипи / Look and logos** and are stored only in the browser of whoever uploads them. They are deliberately not part of this repository, so the repository can't be used to make posts that look official without permission.

Use the original logo files, not screenshots, so they stay sharp.

## Putting it online with GitHub Pages

1. Create a new public repository on GitHub.
2. Upload `index.html` and this `README.md`.
3. Go to **Settings → Pages**, set **Source** to "Deploy from a branch", choose the `main` branch and the `/ (root)` folder, and save.
4. After a minute or two the tool is live at `https://<your-username>.github.io/<repository-name>/`.

You can also just open `index.html` from your computer in a browser.

## Changing it

The whole tool is one file, `index.html`, with no build step. The main places to look:

- `sample()` holds the example week and the default categories and colours.
- `T` holds the interface text in Ukrainian and English.
- `drawCover()` and `drawSlide()` draw the images. Sizes and spacing are in the `M` object.

Colours, categories, and the text that appears on the images can all be changed in the tool itself without touching the code.

## Limits worth knowing

- A Telegram album holds up to 10 images and an Instagram carousel up to 20. The tool warns you if a week goes over. Both platforms change their limits from time to time, so check if the warning seems wrong.
- The font (Golos Text) and the ZIP library load from the internet, so the tool needs a connection the first time it opens.
