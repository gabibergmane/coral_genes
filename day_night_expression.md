select2["mean_day"] = (select2["D1"]+select2["D2"]+select2["D3"])/3
select2["mean_night"] = (select2["N1"]+select2["N2"]+select2["N3"])/3
select3 = select2.drop(["avg_day", "avg_night"], axis=1)
select3

select3.plot.scatter("mean_day", "mean_night").set(
    xlabel="mean day expression",
    ylabel="mean night expression")

from sklearn.linear_model import LinearRegression
X=select3[["mean_day"]]
y=select3["mean_night"]

from sklearn.model_selection import train_test_split
train_X, test_X, train_y, test_y = train_test_split(X, y, random_state=42)

day_night_model = LinearRegression(fit_intercept=True)
day_night_model.fit(train_X, train_y)

pred=pd.DataFrame({"mean_day":[0,2000]})
pred["mean_night"] = day_night_model.predict(pred)
sns.lineplot(data=pred, x="mean_day", y="mean_night", c="red", linestyle=":")

day_night_model.score(test_X, test_y)
