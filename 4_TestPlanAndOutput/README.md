# Algorithm

1) Enable motors

2) Scan

3) Is distance to obstacle greater than 20 cm?

a) If yes = > move forward

b) If no:

b.i) Stop, scan left side and store left distance in a variable

b.ii) Scan right side and store right distance in another variable

b.iii) Are the two distances smaller than 5 cm? (By subtrating the two distances the robot is able to get out of a corner without being stuck)

(b.iii.1) If yes => turn around and move forward

(b.iii.2) If no:

(b.iii.2.a) Is right distance smaller than left distance?

(b.iii.2.a.i) If yes => turn left and move forward

(b.iii.2.a.ii) If no => turn right and move forward
