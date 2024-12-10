toxins = pd.read_csv("Ottaviani et al. 2020 Presentation data sheets.csv")
print(toxins)
#Imports the dataset as "toxins". Remeber to save the desired sheet as .csv

select = toxins.loc[[5460, 5458, 2568, 2548, 3050, 13514, 12740, 19442, 19443, 20723, 21963, 24226, 2542, 3756, 6427, 7145, 784, 8339, 3412, 21208, 14324, 13524, 8922, 15790, 20724, 2093, 2106, 3113, 4302, 4884, 497, 6196, 12739, 13899, 21659, 7992, 6356]]
#Creates the subset
