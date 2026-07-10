S = [1, 2, 5, 6, 8]
d = 9

dp = {0: [[]]}

for num in S:

    new_dp = dict(dp)

    for total in dp:

        new_total = total + num

        if new_total <= d:

            if new_total not in new_dp:
                new_dp[new_total] = []

            for subset in dp[total]:
                new_dp[new_total].append(subset + [num])

    dp = new_dp

if d in dp:

    print("Possible subsets are:")

    for subset in dp[d]:
        print(subset)

else:

    print("No subset found")