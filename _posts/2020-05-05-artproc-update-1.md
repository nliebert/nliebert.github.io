---
layout: post
title: ARTPROC Update #1
subtitle: June 2020
tags: [computing, artproc]
---

ARTPROC is my oldest ongoing project.

![Main Window](/assets/img/artproc1.jpg)

The main program isn't anything spectacular. There's a QB64 [InForm](https://www.qb64.org/inform/) GUI loaded with buttons that allows me to run compiled [Processing](https://processing.org) sketches with the click of a button.

```REALbasic
  SHELL "start mondrian.exe"
```

The above code executes *mondrian.exe* until the *mondrian.exe* window is closed. It's not fancy, but it works. The real trick is in the Processing code.

```Processing
void draw() {
  background(255);
  for(int i = 0; i < num_lines; i++) {
    XLine x = xlines.get(i);
    YLine y = ylines.get(i);
    x.draw_line();
    y.draw_line();
  }
  checkAndFill();
  delay(20);
  saveFrame("records/mondrian/mondrian-###.jpg");
}
```

The *draw()* section of the Processing code is the part that actually draws the sketch that's set up elsewhere in the code. The part that's really useful here is the *saveFrame()* section, which, as you may have guessed, saves the frame. Given a regularly updated sketch, this provides multiple different images as output. I can then work with these.

![Mondrian 186](/assets/img/mondrian-186.jpg)

There are similar *saveFrame()* function in every Processing source file, even those I've written in Python mode, though those are done using a *save()* function instead.

Below are some of the images I've made using ARTPROC.

![Polygon 057](/assets/img/polygons-057.jpg)

![Cloud 405](/assets/img/cloud-405.jpg)

![Barycentric 270](/assets/img/bary-270.jpg)
