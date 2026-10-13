# Casa Larga: what one prompt gave

A lot of people asked me for the prompt behind [my floor plan demo](https://sam1983aing.github.io/casa-serra/). There isn't one. That page took about 70 prompts over two weeks.

So I wrote the prompt I would start with today and tested it once, on a fresh Claude Code session (Opus 5.5) that knew nothing about my project. This repo is what came back, exactly as it came. Nothing was fixed by hand.

**Live:** https://sam1983aing.github.io/casa-larga/

## How the test went

1. I pasted the prompt below. The session wrote no code. It proposed three house layouts with sizes, a camera path stop by stop, said which one it would pick, and waited.
2. I answered with one line: "A. The palette is right. Invent a name and a place."
3. About an hour later it had built the first checkpoint and stopped again: the plan sheet, the walls rising, the walk to the front door, and materials sweeping across the entrance hall while the next room stays a drawing.

That is all this page does. It stops inside the front door. The house and the place name are invented.

## The prompt

Swap the parts in `[brackets]` for your own subject. For this test they were: a house, the entrance hall, the living room, the kitchen and the courtyard, a house that costs millions.

```text
I want to build a scroll-driven landing page for [an architecture studio, a house, a hotel, your subject].

The idea: the page opens on a flat floor plan, like a sheet an architect prints. Black ink on paper, room names, dimensions. Nothing looks 3D. When the visitor scrolls, the walls rise out of the drawing, the camera comes down to the front door and walks through [the rooms you want, in order] at eye height. Each room stays a line drawing until the camera gets there, then the real materials sweep across it.

What I care about:
- The floor plan is not a picture. It is the real 3D model, cut at about 1.2 m and seen from straight above through a very long lens. The drawing and the building are the same thing.
- The camera travels deep into the space, room after room. It does not orbit the building from outside.
- It should feel like [a house that costs millions, your level of ambition]: big rooms, real furniture, late afternoon light.
- three.js, GSAP ScrollTrigger and Lenis, plain files, no build step. Free CC0 materials for the textures.

Before you write any code, propose the layout of the building with sizes I can picture, and the camera path stop by stop. Give me two or three directions to choose from and wait for my answer. Then build in checkpoints. First checkpoint only: the plan sheet, the walls rising, and the walk to the first room. Record it and show me before you go further.
```

The last paragraph matters as much as the idea. Without it you get a finished page you did not choose.

## What to take from it

This is one run, so yours will look different. It is a good start, and it is not the page in my post. The difference is what happened after: asking for options I could watch, giving every room a score out of ten, and going again.

## Run it yourself

Plain files, no build step. The code is readable, so open it and look around.

```bash
python3 -m http.server 8231
```

Then open http://localhost:8231. It needs a server because browsers block modules and textures from a double-clicked file.

three.js 0.170, GSAP 3.12.5 and Lenis 1.1.14 load from jsDelivr. The twelve texture maps in `assets/textures/` are CC0 scans from [Poly Haven](https://polyhaven.com).
