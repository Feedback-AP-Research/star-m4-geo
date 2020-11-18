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

If split down the middle directly, 8 pixels of length will be on the left, and 8 to the right, however there can not exist a center point at 8.5. 

To solve this, one pixel will forever be off as a gap between stars, to create a better user experience, and placing the center at 8 from 1 to 15.

So, the new dimensions will be 15 x 15

The cortesian coordinate system will be 16x16, and each subsequent star will be shifted 16(n -1) pixels to the right.

    x1 = 0
    x2 = .224514
    x3 = .363271
    x4 = .587785
    x5 = .951057
    y1 = -1
    y2 = -.309017
    y3 = .118034
    y4 = .381966
    y5 = .809017
    
The scaler values are proportial to radius r, thus all vertices (10) can be defined as:

    top tip: (x1*r, y1*r)
    top right tip: (x2*r, y2*r)
    bottom left tip: (x5*r, y2*r)
    bottom right tip: (x3*r, y3*r)
    top left tip: (x4*r, y5*r)
    NE: (x1*r, y4*r)
    NW: (-x4*r, y5*r)
    S: (-x3*r, y3*r)
    SW: (-x5*r, y2*r)
    SE: (-x2*r, y2*r)
    
where r is equal to half of what it previous was of 1, 1/2, as the diameter is now 1

With a circumradius of 7 to the center point, the inital coordinate system will be mapped from (0, 0) to (7,7) origin. 

Lastly, the values must be scaled from radius 1/2 to radius 7, or 14:1 diameter ratio

To determine the amount to scale by, whatever is applied to x must be applied to the y dimension, thus the larger difference in extremas will be included in the ratio. 


Examining y and x extremas:
ymax = .809017
ymin = -1 
xmax = .951057
xmin = 0

The largest value, to focus on, is ymax, with delta ymax being 1.809017

By setting a ratio of 14/1 = 1.809017/r
r = 0.12857142857
Thus, the new model can be found by multiplying the vertices points by 7.77777777786

value_new = (value_old * 7.77) + 7
 
 This may go a bit over, as technically the center point still counts as part of the radius, but in the model it is ignored. Either way, the slight invariance is balanced out when the product is rounded to the nearest whole number. 
 
 Plugging it in, the new values are found to be:
  
    x1*r = 8 
    x2*r = 8.7444 ~ 9
    x3*r = 9.8226 ~ 10
    x4*r = 11.567 ~ 11
    x5*r = 14.3897 ~ 15
    y1*r = -15 
    y2*r = 4.032 ~ 4
    y3*r = 7.8547 ~ 8
    y4*r = 9.967875 ~ 10
    y5*r = 13.286 ~ 13   
 
    top tip: (8, 15)
    top right tip: (9, 4)
    bottom left tip: (15, 4)
    bottom right tip: (10, 8)
    top left tip: (11, 13)
    NE: (8, 10)
    NW: (-11, 13)
    S: (-10, 8)
    SW: (-15, 4)
    SE: (-9, 4)
    
    From the leftover transformation there are a couple negative values that need to be cleaned up, as they are not really negative,
    
    -10 => 10 - 7 = 3 => 7 - 3 = 4 
    -11 => 11 - 7 = 4 => 7 - 4 = 3
    -15 => 15 - 7 = 8 => 7 - 6 = 1
    -9 => 9 - 7 = 2 => 7 - 2 = 5
 Updating to:
    NW: (3, 13)
    S: (4, 8)
    SW: (1, 4)
    SE: (5, 4)
    






