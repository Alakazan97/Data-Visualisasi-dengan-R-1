# Data-Visualisasi-dengan-R-1

# Dalam hal ini saya akan mencoba mengetahui beberapa hal terkait beberapa harga rumah, tipe rumah, rumah termahal.

#### apa yang ingin saya dapatkan dalam percobaan kali ini adalah.
      1. penjualan rumah berdasarkan lokasi neighborhood,
      2. Dominan kuallitas keseluruhan dari rumah yang ingin dijual,
      3. Mengetahui kluster harga rumah yang dijual, apakah ada harga jual rumah yang jauh melebihi atau tudak,
      4. mengetahui tipe rumah yang terjual di tiap tahunnya, dan
      5. mengetahui kapasitas garasi setiap rumahnya yang terjual setiap tahunya. 
      
#### Dalam analisis ini saya menggunakan
     1. gambar visualisasi analisis saja
     
#### Harapan dari hasil analisis visualisasi ini 
     1. Dapat membantu agen penjualan rumah tipe rumah apa saja yang kebanyakan dibeli, dalam tahunan
     2. Neighborhood mana saja yang sangat banyak pembeli rumahnya, secara keseluruhan
     3. kluster harga rumah setiap Neighborhood,
     4. pembeli lebih memilih kualitas rumah dengan nilai berapa.
     
# Mengetahui Data set yang akan saya analisis
#### 
     1. sumber data ini saya ambil dari kaggle dengan link: https://www.kaggle.com/c/house-prices-advanced-regression-techniques/data?select=train.csv
     2. Data Train yang saya gunakan terdiri dari 81 kolom dan 1460 baris
     3. Deskripsi setiap kolomnya
        SalePrice - the property's sale price in dollars. This is the target variable that you're trying to predict.
        MSSubClass: The building class
        MSZoning: The general zoning classification
        LotFrontage: Linear feet of street connected to property
        LotArea: Lot size in square feet
        Street: Type of road access
        Alley: Type of alley access
        LotShape: General shape of property
        LandContour: Flatness of the property
        Utilities: Type of utilities available
        LotConfig: Lot configuration
        LandSlope: Slope of property
        Neighborhood: Physical locations within Ames city limits
        Condition1: Proximity to main road or railroad
        Condition2: Proximity to main road or railroad (if a second is present)
        BldgType: Type of dwelling
        HouseStyle: Style of dwelling
        OverallQual: Overall material and finish quality
        OverallCond: Overall condition rating
        YearBuilt: Original construction date
        YearRemodAdd: Remodel date
        RoofStyle: Type of roof
        RoofMatl: Roof material
        Exterior1st: Exterior covering on house
        Exterior2nd: Exterior covering on house (if more than one material)
        MasVnrType: Masonry veneer type
        MasVnrArea: Masonry veneer area in square feet
        ExterQual: Exterior material quality
        ExterCond: Present condition of the material on the exterior
        Foundation: Type of foundation
        BsmtQual: Height of the basement
        BsmtCond: General condition of the basement
        BsmtExposure: Walkout or garden level basement walls
        BsmtFinType1: Quality of basement finished area
        BsmtFinSF1: Type 1 finished square feet
        BsmtFinType2: Quality of second finished area (if present)
        BsmtFinSF2: Type 2 finished square feet
        BsmtUnfSF: Unfinished square feet of basement area
        TotalBsmtSF: Total square feet of basement area
        Heating: Type of heating
        HeatingQC: Heating quality and condition
        CentralAir: Central air conditioning
        Electrical: Electrical system
        1stFlrSF: First Floor square feet
        2ndFlrSF: Second floor square feet
        LowQualFinSF: Low quality finished square feet (all floors)
        GrLivArea: Above grade (ground) living area square feet
        BsmtFullBath: Basement full bathrooms
        BsmtHalfBath: Basement half bathrooms
        FullBath: Full bathrooms above grade
        HalfBath: Half baths above grade
        Bedroom: Number of bedrooms above basement level
        Kitchen: Number of kitchens
        KitchenQual: Kitchen quality
        TotRmsAbvGrd: Total rooms above grade (does not include bathrooms)
        Functional: Home functionality rating
        Fireplaces: Number of fireplaces
        FireplaceQu: Fireplace quality
        GarageType: Garage location
        GarageYrBlt: Year garage was built
        GarageFinish: Interior finish of the garage
        GarageCars: Size of garage in car capacity
        GarageArea: Size of garage in square feet
        GarageQual: Garage quality
        GarageCond: Garage condition
        PavedDrive: Paved driveway
        WoodDeckSF: Wood deck area in square feet
        OpenPorchSF: Open porch area in square feet
        EnclosedPorch: Enclosed porch area in square feet
        3SsnPorch: Three season porch area in square feet
        ScreenPorch: Screen porch area in square feet
        PoolArea: Pool area in square feet
        PoolQC: Pool quality
        Fence: Fence quality
        MiscFeature: Miscellaneous feature not covered in other categories
        MiscVal: $Value of miscellaneous feature
        MoSold: Month Sold
        YrSold: Year Sold
        SaleType: Type of sale
        SaleCondition: Condition of sale
        

# Persiapan data
####
     1. saya menggunakan R dengan versi 4.1.2
     2. menggunakan package : 
        library(tidyverse)
        library(ggplot2)
        library(ggsci)
        library(ggpubr)
     3. hasil code, saya lampirkan disini. 
     
#  1. Penjualan rumah berdasarkan lokasi neighborhood & kualitas keseluruhan rumah yang terjual. 
#### 
    pada analisis kali ini saya menggunakan variabel, neighborhood dan banyaknya penjualan dari data itu. 
    dengan mendapatkan hasil seperti ini.

![home sale based location](https://user-images.githubusercontent.com/92445676/155240351-9947a73d-9ed9-446f-944c-a017a5197655.png)
    Berdasarkan hasil analisis visualisasi penjualan rumah berdasarkan lokasi, kita dapatkan 4 tempat terbanyak yaitu:
    North Ames dengan 225 rumah terjual
    Collage Creek dengan 150 rumah terjual
    Old Town dengan 113 rumah terjual
    dan, Edwards 100 rumah terjual.
    sisa lokasi menempati penjualan rumah dengan nilai dibawah 100 rumah dilain lokasi yang tadi disebutkan. 

![oqual h](https://user-images.githubusercontent.com/92445676/155240876-ea0d7505-e357-4ac4-993d-41180b54b1ec.png)
    berdasarkan hasil Analisis visualisasi itu, bahwa rumah yang terjual memiliki nilai kualitas keseluruhannya:
    nilai rumah dengan angka 5 menunjukan rumah tersebut memiliki kualitas rata-rata dengan banyak 395 rumah.
    nilai rumah dengan angka 6 menunjukan rumah tersebut memiliki kualitas diatas rata-rata dengan banyak 374 rumah. 
    nilai rumah dengan angka 7 menunjukan rumah tersebut memiliki kualitas baik dengan banyak 319 rumah. 
    
 #  2. Kluster harga rumah setiap Neighborhood di Ames. 
#### 
    pada analisis kali ini saya menggunakan variabel, neighborhood dan saleprice penjualan dari data itu. 
    dengan mendapatkan hasil seperti ini.
![cluster](https://user-images.githubusercontent.com/92445676/155241938-04921dc6-1f53-464d-af51-6a709a115d3e.png)
    berdasarkan hasil analisis diatas, kisaran harga rumah yang dijual di Ames memiliki rentah harga $180000-$400000. 
    Adapula neighborhood yang memliliki harga rumah lebih mahal, yaitu pada lokasi Northridge Heights, Stone Brook, dan Northridge.
    dan rumah dengan harga tertinggi ada di lokasi Northridge.
    
#  3. Mengetahui tipe rumah yang terjual di tiap tahunnya 
#### 
    pada analisis kali ini saya menggunakan variabel, OverallQual, OverallCond, dan housestyle penjualan dari data itu. 
    dengan mendapatkan hasil seperti ini.
![housetype](https://user-images.githubusercontent.com/92445676/155243430-d67d55ca-2128-4104-a845-caff182f58ce.png)
    berdasarkan hasil analisis diatas, trend kebanyakan rumah yang terjual mememiliki style rumah dengan 1 lantai atau 2 lantai. 
    dominasi yang kuat terjadi dari tahun 2006 hingga 2010 dengan mayoritas penjualan rumah dengan 1 lantai.  
    disusul dengan rumah yang memiliki 2 lantai. 
    nilai dari kondisi keseluruhan rumah yang terjual kebanyakan dari rentang nilai 5 keatas. 

#  4. Mengetahui kapasitas garasi setiap rumahnya yang terjual setiap tahunya. 
#### 
    pada analisis kali ini saya menggunakan Garagecars & garagearea penjualan dari data itu. 
    dengan mendapatkan hasil seperti ini.
![garage](https://user-images.githubusercontent.com/92445676/155243572-0a5f1cf3-cd24-49eb-9882-1974f5a392c2.png)
    berdasarkan hasil analisis diatas, dalam setiap bulan, banyak pembeli rumah menginginkan dengan garasi dengan kapasitas 1 hingga 3 mobil. dengan nilai yang memiliki korelasi positif antara luas garasi dengan kapasitas mobil pada garasi tersebut. 





      
