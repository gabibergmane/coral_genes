select2=select.drop("Gene", axis=1)
select2.rename(columns={'AJ2': 'D1', 'AJ3': 'D2', 'AJ4':'D3', 'AN2':'N1', 'AN3':'N2', 'AN4':'N3'}, inplace=True)
sns.boxplot(select2,
           order=["D1", "N1", "D2", "N2", "D3", "N3"],
           )
