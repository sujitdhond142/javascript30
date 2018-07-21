## Day 02 - JS and CSS clock

### Beautiful Analog clock made with JS and CSS.

### Challenge Solution steps

-  We get date with Date() and store min ,sec ,hours in variables
-  We get clock hands with query selector
-  Intially clock hands are at 9 so we add 90 to each angle and then calculate angles made by each hand from 12 o' clock position
-  Each second counts for 6 deg rotation in clock so we can get angle of second hand by simply 
``` 
secondAngle = second*6+90;
```
- Each seond also counts for rotation in minute hand. We calculate minute hand as follows:
```
minuteAngle = minute*6+second/10+90;
```
- Each hour counts for 30 deg rotation. We calculate hour hand angle as follows:
```
hourAngle = hour*30+minute/2+90;
```
- At last we apply rotation to clock hands
