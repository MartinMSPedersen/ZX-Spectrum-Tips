```
10 DIM m(255)
15 LET a=COS (PI/4)
20 FOR y=1 to 141 STEP 5
25 LET e=a*y
27 let c=y-70
29 Let c=c*c
30 FOR x=1 TO 141
34 LET d=x-70
40 LET z=80*EXP (-0.001*(c+d*d))
50 LET x1=x+e
60 LET y1=z+e
70 IF y1>=m(x1) THEN LET m(x1)=y1: PLOT x1,y1
80 NEXT x
90 NEXT y
```

