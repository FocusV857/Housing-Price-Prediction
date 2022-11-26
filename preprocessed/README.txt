对于categorical.csv
1.删除了['Alley','PoolQC','Fence','MiscFeature']，因为缺失值在80%以上
2.['BsmtQual','BsmtCond','BsmtExposure','BsmtFinType1','BsmtFinType2',
'GarageType','GarageFinish','GarageQual','FireplaceQu','GarageCond'] 用“NA”填充
3.['MSZoning','Utilities','Exterior1st','Exterior2nd','MasVnrType',
'Electrical','KitchenQual','Functional','SaleType']用该属性出现最多的值填充
4.['Utilities','Street','Condition2','RoofMatl','Heating'] low variance，drop

对于numerical.csv
1.NAN：LotFrontage 用中位数填充
2.NAN：GarageYrBlt 用YearBuilt填充
3.对于其他缺失值用0填充
4.对于GarageYrBlt晚于YrSold的，也用YearBuilt填充（ID=2593）
5.对于YearSold早于YearBuilt的，用YearBuilt填充（ID=2550）
6.添加Age_House、TotalBsmtBath、TotalBath、TotalSA特征

对于categorical_to_numerical.csv
1.对于表示程度的categorical，转换为数值即可
2.对于表示类别的categorical，采用one-hot encoding

对于df_final:
合并了numerical.csv和categorical_to_numerical.csv