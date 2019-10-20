# glsl-fbm
[Fractional Brownian Motion(fBM)](https://www.iquilezles.org/www/articles/fbm/fbm.htm) ported to an NPM package for [glslify](http://github.com/chrisdickinson/glslify). Also check out [GLSL Noise Algorithms](https://gist.github.com/patriciogonzalezvivo/670c22f3966e662d2f83)

## Installation
`npm install glsl-fbm`

## Usage ##
``` glsl

attribute vec3 position;
attribute vec2 uv;
uniform float time;

#pragma glslify: fbm = require(glsl-fbm)

void main() {
  vec3 pos = position;
  float height = fbm(vec3(uv, time));
  pos.y += height;
  
  gl_Position = uProjectionMatrix * uViewMatrix * uModelMatrix * vec4(pos, 1.0);
}
```