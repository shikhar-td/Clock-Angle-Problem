def calculate_angle(h, m):
# if the entered value isin negative then its invalid
    if (h < 0 or m < 0):
        print('Invalid input')
        
#changing the values in 12 Hour format
    if (h > 12):
        h -= 12
    if (m > 60):
        m -= 60
#calculating Hour angle
    hour_angle = 0.5 * (h * 60 + m)
#calculating minute angle
    minute_angle = 6 * m

# calculating minimun minimum and absolute angle
    angle = abs(hour_angle - minute_angle)

    angle = min(abs(360 - angle), angle)

# returning  minimum angle
    return angle

#taking input from user
time = input("Enter time in hh:mm format: ")

h, m = map(int, time.split(":"))

print(calculate_angle(h, m))
