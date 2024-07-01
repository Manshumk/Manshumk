DATA_PATH = "dataset/Training.csv"


data = pd.read_csv(DATA_PATH).dropna(axis = 1) 



disease_counts = data["prognosis"].value_counts() 


temp_df = pd.DataFrame({ 


    "Disease": disease_counts.index, 


    "Counts": disease_counts.values 

})

  

plt.figure(figsize = (18,8)) 


sns.barplot(x = "Disease", y = "Counts", data = temp_df) 


plt.xticks(rotation=90) 

plt.show()
