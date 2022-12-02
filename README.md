# Raycasting

## Definition

### Ray
![img](https://www.splashlearn.com/math-vocabulary/wp-content/uploads/2022/08/Ray-in-Math-2.png)

The definition of ray in math is that it is a part of a line that has a fixed starting point but no endpoint.

### Ray Casting

![img](https://www.researchgate.net/publication/268441139/figure/fig5/AS:669495446237187@1536631561194/Illustration-of-raycasting-A-ray-is-cast-from-the-viewer-through-a-pixel-on-the.png)
Ray casting is the most basic of many computer graphics rendering algorithms that use the geometric algorithm of ray tracing. Ray tracing-based rendering algorithms operate in image order to render three-dimensional scenes to two-dimensional images. Geometric rays are traced from the eye of the observer to sample the light (radiance) travelling toward the observer from the ray direction.

### Viewport to Canvas
![CodeCogsEqn (1)](https://user-images.githubusercontent.com/119586404/205045020-60246351-2cca-4305-8763-4a440ce35c17.png)

![Picture2](https://user-images.githubusercontent.com/119586404/205046114-666228a9-4beb-420e-93ff-32449f82a888.png)

A viewport is a polygon viewing region in computer graphics.

A canvas is a container that holds various drawing elements (lines, shapes, text, frames containing others elements, etc.). 

![img](https://i0.wp.com/dab1nmslvvntp.cloudfront.net/wp-content/uploads/2014/03/1393985491canvas-coordinate-space.png)

What the difference between the canvas and viewport is the starting point. The viewport follows the Cartesian coordinate system. Because this is a polygon viewing region of 3D dimension.


### Intersection between Sphere and Vector
![Picture1](https://user-images.githubusercontent.com/119586404/205041795-8c8ce7ca-9663-41dc-a2f4-37a59f88f00c.png)

```
P = O + t(V - O)
```
The ray passes through O, its direction (from O to V), P is any point in the ray as where t is any real number.

The V is a point in viewport.

```
Distance(P, C) = r
Sqrt(Pow(P - C, 2)) = r
Pow(P - C, 2) = Pow(r, 2)
```
If C is the center and r is the radius of a sphere, the P on the surface of that sphere must satisfy the above equation.

The Sqrt returns the square root of a number.

The Pow returns the value of a base raised to a power.
```
P = O + t(V - O)

Sqrt(Pow(P - C, 2)) = r

Sqrt(Pow(O + t(V - O) - C, 2)) = r

Pow(O + t(V - O) - C, 2) = Pow(r, 2)

Pow(CO + t(V - O), 2) = Pow(r, 2)

Pow(CO, 2) + Pow(t(V - O), 2) + 2*t(V - O)*CO = POW(r, 2)

Pow((V - O), 2)*Pow(t, 2) + 2*(V - O)*t + Pow(CO, 2) - Pow(r, 2) = 0

a = Pow((V - O), 2)
b = 2*(V - O)
c = Pow(CO, 2) - Pow(r, 2)

a*Pow(t, 2) + b*t + c = 0
```
![img](https://user-images.githubusercontent.com/119586404/205035694-de533b10-2e65-4c98-a477-1c336f81d3e3.png)


The t1, t2 are real numbers when a ray is tangent line on sphere.
They can be used for finding points on sphere using the below equation.
```
P = O + t(V - O)
```

```
if t < 0 {
  // behind the origin
}
if 0 <= t <= 1 {
  // between the origin and the viewport
} 
if t > 0 {
  // in front of the viewport
}
```

## References
[Ray casting](https://en.wikipedia.org/wiki/Ray_casting)

[Figure 1 - uploaded by Patric Ljung](https://www.researchgate.net/figure/Illustration-of-raycasting-A-ray-is-cast-from-the-viewer-through-a-pixel-on-the_fig5_268441139)

[Viewport](https://en.wikipedia.org/wiki/Viewport)

[Canvas](https://en.wikipedia.org/wiki/Canvas_(GUI)#:~:text=In%20computer%20science%20and%20visualization,canvas%20used%20in%20visual%20arts.)

[Ray in Math: Meaning, Definition, Examples](https://www.splashlearn.com/math-vocabulary/geometry/ray)

[Drawing in HTML5 using Canvas with Save as image feature](https://www.debugpoint.com/drawing-in-html5-using-canvas-with-save-as-image-feature/)

[Quadratic formula](https://en.wikipedia.org/wiki/Quadratic_formula)

[HTML Canvas Tutorial](https://sathyalog.wordpress.com/2014/05/22/html-canvas-tutorial/)