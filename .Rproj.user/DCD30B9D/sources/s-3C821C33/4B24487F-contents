# Miguel Soler

#Libraries

install.packages("readxl")
library("readxl")
library("dplyr")
library("janitor")
library("arsenal")


# 1. Lea adecuadamente las bases de datos. Vea el siguiente ejemplo y lea los datos para el 2015, etc
# de los años 2015 hasta el año 2018.

install.packages("readxl")
library("readxl")

data2015 <- read_excel("./avocado.xlsx", sheet = "Registros2015")
data2016 <- read_excel("./avocado.xlsx", sheet = "Registros2016")
data2017 <- read_excel("./avocado.xlsx", sheet = "Registros2017")
data2018 <- read_excel("./avocado.xlsx", sheet = "Registros2018")

# 2. Elabore un Data Frame donde compare los nombres de las variables en 
#las bases de datos del 2015 hasta el 2018. 

tablesComparison = all_equal(data2015,data2016,data2017,data2018)   
tablesComparison

# 3. Arregle los nombres de las columnas si es necesario. Una todas las bases de datos 
#en un solo Data Frame: Qué precauciones debe tener?

# A nivel de precacuciones se debe tener en cuenta que las tablas tengan las mismas dimensiones
# y nombres de variables iguales 

colnames(data2016) <- c("Registro Número","Date","AveragePrice","Total Volume","4046","4225","4770","Total Bags","Small Bags","Large Bags","XLarge Bags")






