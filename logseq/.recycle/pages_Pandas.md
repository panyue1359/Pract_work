- ## 问题
- A value is trying to be set on a copy of a slice from a DataFrame
	- 避免使用df["column name"][index]，建议使用df.loc[index,"column name"]