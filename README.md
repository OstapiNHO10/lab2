# lab2
def simplify_busy_schedule(schedule):
    schedule.sort(key=lambda x: x[0])
    simplified_schedule = []

    for start, end in schedule:
        if not simplified_schedule or start > simplified_schedule[-1][1]:
            simplified_schedule.append([start, end])
        else:
            simplified_schedule[-1][1] = max(simplified_schedule[-1][1], end)

    return simplified_schedule

schedule = [(0, 1), (3, 5), (4, 8), (10, 12), (9, 10)]
print(simplify_busy_schedule(schedule))
