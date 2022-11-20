def calculate_angle(h, m):
    if (h < 0 or m < 0):
        print('Invalid input')

    if (h > 12):
        h -= 12
    if (m > 60):
        m -= 60

    hour_angle = 0.5 * (h * 60 + m)
    minute_angle = 6 * m

    angle = abs(hour_angle - minute_angle)

    angle = min(abs(360 - angle), angle)

    return angle


time = input("Enter time in hh:mm format: ")

h, m = map(int, time.split(":"))

print(calculate_angle(h, m))
