# Miguel Soler

#Libraries

install.packages("readxl")
install.packages("plyr")
install.packages("sqldf")
library("readxl")
library("dplyr")
library("plyr")
library("janitor")
library("arsenal")
library("sqldf")



# 1. Lea adecuadamente las bases de datos. Vea el siguiente ejemplo y lea los datos para el 2015, etc
# de los años 2015 hasta el año 2018.

install.packages("readxl")
library("readxl")

data2015 <- read_excel("./avocado.xlsx", sheet = "Registros2015")
data2016 <- read_excel("./avocado.xlsx", sheet = "Registros2016")
data2017 <- read_excel("./avocado.xlsx", sheet = "Registros2017")
data2018 <- read_excel("./avocado.xlsx", sheet = "Registros2018")
otherVariables <- read_excel("./avocado.xlsx", sheet = "Nuevas Variables")

# 2. Elabore un Data Frame donde compare los nombres de las variables en 
#las bases de datos del 2015 hasta el 2018. 

tablesComparison = all_equal(data2015,data2016,data2017,data2018)   
tablesComparison

# 3. Arregle los nombres de las columnas si es necesario. Una todas las bases de datos 
#en un solo Data Frame: Qué precauciones debe tener?

# A nivel de precacuciones se debe tener en cuenta que las tablas tengan las mismas dimensiones
# y nombres de variables iguales 

colnames(data2015) <- c("RegistroNumero","Date","AveragePrice","TotalVolume","4046","4225","4770","TotalBags","SmallBags","LargeBags","XLargeBags","type","year","region")
colnames(data2016) <- c("RegistroNumero","Date","AveragePrice","TotalVolume","4046","4225","4770","TotalBags","SmallBags","LargeBags","XLargeBags","type","year","region")
colnames(data2017) <- c("RegistroNumero","Date","AveragePrice","TotalVolume","4046","4225","4770","TotalBags","SmallBags","LargeBags","XLargeBags","type","year","region")
colnames(data2018) <- c("RegistroNumero","Date","AveragePrice","TotalVolume","4046","4225","4770","TotalBags","SmallBags","LargeBags","XLargeBags","type","year","region")
colnames(otherVariables) <- c("RegistroNumero","Date","type","year","region")

mergedYears = rbind(data2015,data2016,data2017,data2018)

mergeData = merge(mergedYears,otherVariables)

View(mergeData)

## inner join
#filtered <- sqldf("SELECT RegistroNumero, Date, type, year, region 
#              FROM otherVariables
#              JOIN mergedYears USING(RegistroNumero)")

unique(dataMerged)

# 4. Con la función subset seleccione los datos correspondientes a las regiones de "NewYork", "Boston", "Orlando" 
#y con esta nueva base de datos elabore una tabla donde compare las medidas descriptivas 

filteredRegions = mergeData %>% filter( region == 'NewYork' | region == 'Boston' | region == 'Orlando' ) 

summary(filteredRegions$TotalVolume)

# El promedio de aguacates vendidos es de 391192 en las regiones de Newyork, boston y orlando.
# El minimo de aguacates vendidos para las regiones de Newyork, boston y orlando es de 1611
# El máximo de aguacates vendidos para las regiones de Newyork, boston y orlando es de 2959541

# 5. Con los datos del punto anterior (es decir con los registros correpondientes a "NewYork", "Boston", "Orlando")
#Elabore e INTERPRETE una tabla cruzada con la función tabyl donde 
#se observe el porcentaje de registros de acuerdo a la Ciudad (region) y a 
#tipo de augacate (Type) asegúrese de que salga porcentaje del total columnas.
#INTERPRETE ESTA TABLA RESALTE LAS CARACETRÍSTICAS MÁS IMPORTANTES


round(prop.table(table(filteredRegions$type, filteredRegions$region),1),2) 
round(prop.table(table(filteredRegions$type, filteredRegions$region),2),2) 
round(prop.table(table(filteredRegions$type, filteredRegions$region)),2) 

# En la ciudad donde se comercia la mayor cantidad de aguacates convencionales es Orlando
# seguido por Boston y finalmente newyork 