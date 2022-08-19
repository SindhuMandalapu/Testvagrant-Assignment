# Testvagrant-Assignment
def having_2_concecutive_loses(teams_details,n):
    count_of_n_concecutive_loses = {}
    for team in teams_details:
        count = 0
        for i in range(len(team[2])):
            if team[2][i] == "no":
                count = count + 1
                if (count == n):
                    count_of_n_concecutive_loses[team[0]] = team[1]
                    break
            else:
                count = 0
    return count_of_n_concecutive_loses

no_of_teams = int(input())
teams_details = []
for _ in range(no_of_teams):
    name = input()
    points = int(input())
    match_details = input().split(" ")
    team_details = []
    team_details.append(name)
    team_details.append(points)
    team_details.append(match_details)
    teams_details.append(team_details)
n = int(input())    
n_concecutive_loses = having_2_concecutive_loses(teams_details,n);
print(n_concecutive_loses)
avg_points = n_concecutive_loses.values()
print(sum(avg_points)/len(avg_points))
