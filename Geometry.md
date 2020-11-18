A normal pentagon star can be inscribed by a circle, creating 5 sectors of equal length, with radian measure of 2pi/5 for each

https://martiancraft.com/img/blog/articles/small/20170320_stars_starcircle@2x.png

To find the coordinates of the points where the star and circle touch, we can use two methods:

we can represent it as a polar function through: 

r = sec((2/n) * arcsin(sin((n/2)theta))

in this method, we will return all non-differentiable points 

This can be found easily through how a polar function is represented and made, with coordinates being based on a unit circle of 
(theta, r)

By examining the angle of elevation makde with the x-axis, we get the following coordinates starting from the top and travelling clockwise:

(12pi/5, 1), (0, 1), (8pi/5, 1), (16pi/5, 1), (4pi/5, 1)

We observe that the radius is 1 for all of them, showing that there lies an equidistant point in the center

https://martiancraft.com/img/blog/articles/small/20170320_stars_starwithtriangle@2x.png

As with all triangle-like shapes, we can extrapulate the coordinates through trig.

As such, we assume understanding of the following:

The terms used in describing a right-angled triangle are:

    Hypotenuse - the edge of the triangle that is opposite the right angle
    𝜃 (theta) - the non-right angle you’re interested in
    Opposite - the edge of the triangle opposite 𝜃
    Adjacent - the edge of the triangle next to 𝜃
    

Setting up relations: 
  where assuming the origin of a cartesian coordinate system is devised at the center of the star
  
  top left: 
    4pi/5
    (cos(tan^-1(tan(4pi/5)), sin(tan^-1(tan(4pi/5))
   top right:
    0    
    (cos(tan^-1(tan(0)), sin(tan^-1(tan(0))
   top:
    12pi/5
    will just be (0,1) 
   bottom left:
    16pi/5
     (cos(tan^-1(-pi/5 + tan(16pi/5)), sin(tan^-1(-pi/5 + tan(16pi/5)) 
   bottom right:
     8pi/5
     (cos(tan^-1(pi/5 + tan(8pi/5)), sin(tan^-1(pi/5 + tan(8pi/5)) 
     
 Another way of reaching this solution, is through examining a regular polygon, 
  
 

For any reguar polygon, the internal angles can be found through teh following formula:

((n - 2) * 𝛑) / n, where n is number of sides

This gives us 3pi/2, which is equal to the exterior angle as well

As trig only works with right angle triangles, we must split the outer isocoles triangle formed by the pentagon and circle vertically.

https://martiancraft.com/img/blog/articles/small/20170320_stars_trigonometry@2x.png

The new angle will be (3pi/5)/2, or 0.3pi

https://martiancraft.com/img/blog/articles/small/20170320_stars_innercircle@2x.png

However, as stated from the polar function above, the length of the star's edge will be equal to r = 1, yet this does not equate to the radius of the circle, as the radius to the inside of the pentagon has not been accounted for in this model. 

A work around is through doing the same method to finding the smallest circle we can inscribe around the star, and translating that to the pentagon, finding the radius through the circle formula, and then adding it to the previous r we found.

A pre-existing solution exists, from wolframm alpha for any n-sided regular star, the circumradius can be found by:

https://mathworld.wolfram.com/images/equations/StarPolygon/NumberedEquation1.gif

Where p is the number of points, and q is the polygon density, or points per sector, where in this case: p/q = 5/2

With the new circumradius at 1.22, the trig equations are assembled as:

distanceIn = opp / tan(theta)

Arriving with the same points from the previous method

With our coordinates, problems arise when trying to immediately translate them

Assuming that the M4 portal works in rows and columns, there is only the 1st quadrant to work with

Secondly, in order to properly scale, the largest number must be 1

Before continuing, a clarification must be made

FeedBack consists of 4 stars, and as the board is 64 pixels long and 32 tall, 16 pixels of length is the most to work with, and as the star's  circle will be inscribed by a square, width must equal height.

The cortesian coordinate system will be 16x16, and each subsequent star will be shifted 16(n -1) pixels to the right.


   
    
    
  
