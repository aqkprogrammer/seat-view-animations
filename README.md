# Seat View Animations

Two mobile UI prototypes that let you **see the view before you pay for the seat**, recreated from a pair of Instagram reels as an interaction study. Plain HTML, CSS and `<canvas>` — no framework, no build step.

**Live demo:** https://aqkprogrammer.github.io/seat-view-animations/

| Demo | What it does |
|------|--------------|
| [Airline window view](https://aqkprogrammer.github.io/seat-view-animations/airline-window-view.html) | Pick a window seat on the plane map, then scrub the flight from Barcelona to Paris: coast → Pyrenees → sunset → Paris at night, through a real cabin window with a working shade. Row 11 shows the "sold as a window seat, but there's no window" case. |
| [Cinema seat view](https://aqkprogrammer.github.io/seat-view-animations/cinema-seat-view.html) | Pick a cinema seat, hold it to see the screen from exactly there, with distance, field of view and offset from centre. Hop between seats and watch the perspective animate. |

## Run locally

Open any `.html` file directly in a browser, or serve the folder:

```bash
npx serve .
```

The pages are laid out as a 430 × 900 phone frame on desktop and go full-screen on a real phone.

## Airline demo controls

- **Tap a window seat** (A or F) on the map. Scroll down for the later rows.
- **Shade:** drag it up or down, tap it, or use the *Close / Open shade* button. Cabin lighting around the window follows the view and dims when the shade is down.
- **Timeline:** drag the knob to scrub; the round button next to the clock pauses autoplay. Altitude, ground speed, distance to CDG and outside temperature follow the scrubber.
- **Over the wing:** rows 12–17 show the wing in the window, with nav light and strobe.
- **Sound:** the speaker button toggles a generated cabin-noise ambience (off by default).
- **ⓘ** shows the credit for the photo currently in the window.

## Cinema demo controls

- **Tap** a seat to select it, **hold** it (or tap the eye button) to open the view from that seat.
- In the view, tap the **minimap**, use the **arrow keys**, tap the **left/right edges** or **swipe up/down** to move seats.
- The verdict label changes with position: *Sweet spot*, *Close to screen*, *Off to the side*, *Recliner · back row*.
- Double-click the screen for the still's credit.

## Photos

The window views and the cinema "film" are real photos hotlinked from Wikimedia Commons. If a photo cannot load (offline, blocked), the demo falls back to procedurally drawn scenery on `<canvas>`.

| Stop | Photo | Author · licence |
|------|-------|------------------|
| BCN | [Aerial view of Barceloneta Beach and Port Vell](https://commons.wikimedia.org/wiki/File:Aerial_view_of_Barceloneta_Beach_and_Port_Vell_in_Barcelona,_Spain_(51226238126).jpg) | dronepicr · CC BY 2.0 |
| Pyrenees | [Pyrenees aerial](https://commons.wikimedia.org/wiki/File:Pyrenees_aerial.jpg) | kallerna · CC BY-SA 4.0 |
| Sunset | [Above The Clouds](https://commons.wikimedia.org/wiki/File:Above_The_Clouds_(110289131).jpeg) | Faldrian · CC BY 3.0 |
| Paris | [Paris, Île-de-France, December 11, 2008](https://commons.wikimedia.org/wiki/File:Paris,_%C3%8Ele-de-France_December_11,_2008.jpg) | Joi Ito · CC BY 2.0 |
| Cinema film | ["Ein beeindruckender Teil der Sahara" 01 (Erg Chebbi)](https://commons.wikimedia.org/wiki/File:%22Ein_beeindruckender_Teil_der_Sahara%22._01.jpg) | Holger Uwe Schmitt · CC BY-SA 4.0 |

To use the demos fully offline, download those files into an `img/` folder and point the `src` values in the two HTML files at them.

## Project layout

```
index.html                 hub page linking both demos
airline-window-view.html   seat map + window view (single file, inline CSS/JS)
cinema-seat-view.html      seat picker + view from seat (single file, inline CSS/JS)
```

## Licence

Code: MIT. Photos: as credited above (CC BY / CC BY-SA, via Wikimedia Commons).
