# Angle-of-inclination-predictor
This model was made using the YOLOv8 model from the ultralytics library.
I proceeded to explore the ultraytics library and its functions. After many iterations of trying to define the most accurate way to define the angle of incli- nation i arrived on this.
Since when a book is inclined, YOLOv8 tends to identify it as multiple books, I take only the box with the highest confidence value and reject the rest.
Using the coordinates of this box, I arrive at: Angle of inclination = Arctan(height/width)
consider a case where the book is at 90 degrees. Using my above formula we will never achieve 90 as the book has an aspect ratio. To account for this, I decided a threshold to this arctan value, above which the angle of inclination will be considered as 90.
After looking through the general aspect ratios of books and trying thresh- olds out on test images, I arrived at a threshold of 75 degrees.
