from scipy.stats import spearmanr
rho, p = spearmanr(select3['mean_day'], select3['mean_night'])
print(rho)
print(p)
