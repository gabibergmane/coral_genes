from scipy import stats
T, p = stats.ttest_ind(select3['mean_day'], select3['mean_night'])
print(T)
print(p)
