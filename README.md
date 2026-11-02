# Disco Fish

A WebGL2 scene I built as the final project for COSC 452 (Computer Graphics) at the University of Tennessee, Knoxville, Spring 2023. A copper goldfish swims inside a glass egg, surrounded by bubbles, in front of a lake skybox.

Live on my site: [swasti-mishra.com/projects](https://www.swasti-mishra.com/projects)

## What's in it

- **Goldfish:** per-pixel Phong lighting (ambient, diffuse and specular computed per fragment), with a tangent-space normal map for the scales' bumpy detail.
- **Egg and bubbles:** real-time reflection and refraction shaders. A Fresnel term blends between the two based on viewing angle, sampling the skybox cube map as the environment.
- **Skybox:** the same cube map, rendered onto an inside-out cube as the background.
- **Controls:** sliders for camera position and focus, plus buttons to switch between the inner and outer egg views.

## Run it

It needs to be served over HTTP, since it loads models, shaders and textures with `fetch`. From the repo root:

```bash
python3 -m http.server 8000
```

Then open <http://localhost:8000>.

## Along the way

The final project builds on these earlier COSC 452 assignments, which are also in this repo:

- **Lab 1, Basic WebGL2:** `lab1/step0` to `lab1/step3`
- **Lab 2, Shading and Basic GLSL:** `lab2/step0` to `lab2/step4`
- **Midterm:** `midterm/` and `midterm/step1`
- **Lab 3, Texture Mapping in GLSL:** `lab3/step1` to `lab3/step4`

## Layout

- `final/`: the project itself (`index.html` and `js/main.js`).
- `lab1/`, `lab2/`, `lab3/`, `midterm/`: the smaller assignments leading up to it, one folder per step. Each is a runnable page at `<folder>/` (for example `/lab3/step4/`).
- `shared/js/`: helper libraries for loading shaders, OBJ files and vertex data, from the course (used with my instructors' permission), plus [gl-matrix](https://github.com/toji/gl-matrix).
- `shared/resources/`: models, shaders and textures the scene loads.

## Credits

- Goldfish model: ["Goldfish"](https://sketchfab.com/3d-models/goldfish-071e439aee854058946e537949bf665e) by Jean-Christophe Sekinger, licensed [CC-BY-4.0](http://creativecommons.org/licenses/by/4.0/). See `shared/resources/finalProjectFiles/goldfish/license.txt`.
- Bubble model: ["Bubble"](https://sketchfab.com/3d-models/bubble-db5b743912b54121ba84b2a4421e3478) by haisanberg, licensed [CC-BY-4.0](http://creativecommons.org/licenses/by/4.0/).
- Lake cube map: from [Zoe Wood's CSC 471 materials](http://users.csc.calpoly.edu/~zwood/teaching/csc471/finalW19/nmlui/index.html) at Cal Poly.
- Glass shader: adapted from [McNopper's OpenGL examples](https://github.com/McNopper/OpenGL/tree/master/Example11).
- Course helper libraries: COSC 452, Spring 2023, taught by Jian Huang.
- [gl-matrix](https://github.com/toji/gl-matrix) by Brandon Jones and Colin MacKenzie IV (MIT).

## License

My own code (`final/`) is under the MIT license, see `LICENSE`. The third-party models, textures and libraries above keep their own licenses.
