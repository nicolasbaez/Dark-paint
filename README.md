# Dark-paint
Waves from beyond

![buh](https://github.com/nicolasbaez/Dark-paint/blob/main/xp010.gif)
```javascript
w = 500;
h = 255;
k = 0;
setup = (_) => createCanvas(w, w);
draw = (_) => {
  background(0);
  noFill();
  for (i = 0; i < w; i += 3) {
    stroke(0, noise(i, k) * h, noise(k, i) * h);
    beginShape();
    for (j = 0; j < w; j += 32) curveVertex(j, i + noise(j, k) * w);
    endShape();
  }
  k += 0.01;
};
function keyPressed() {
  if (key === "s") {
    saveGif("xp010.gif", 150, { delay: 0, units: "frames" });
  }
}
