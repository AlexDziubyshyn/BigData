# Big Data Lab 1

## Task 1
### За допомогою download.file() завантажте любий excel файл з порталу http://data.gov.ua та зчитайте його (xls, xlsx – бінарні формати, тому встановить mode = “wb”. Виведіть перші 6 строк отриманого фрейму даних.
```{r}

download.file("http://data.gov.ua/dataset/1703061d-e0c4-4393-8a29-fc154d2705fe/resource/506977cc-1793-41ee-b14e-6d2bab7c02f4/download/pasport-naboru-danikh.xlsx", "auto", TRUE,"wb")
save_file <- read_xlsx("save_file.xlsx")


```


### Немного магии с подключением джавы на Mac OS (для xlsx парсинга нужна JVM), из которой ничего не вышло. 
```{r}
Sys.setenv(DYLD_FALLBACK_LIBRARY_PATH="/Library/Java/JavaVirtualMachines/openjdk-11.0.2.jdk/Contents/Home/jre/lib/server/")
library(rJava);
library(xlsx);
```

### Сам вывод по-идее должен быть таким
```{r}
head(save_file, n = 6)
```

## Task 2
### За допомогою download.file() завантажте файл getdata_data_ss06hid.csv за посиланням https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Fss06hid.csv та завантажте дані в R. Code book, що пояснює значення змінних знаходиться за посиланням https://www.dropbox.com/s/dijv0rlwo4mryv5/PUMSDataDict06.pdf?dl=0 Необхідно знайти, скільки property мають value $1000000+
```{r}

fileUrl <- 'https://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Fss06hid.csv'
download.file(fileUrl, destfile = "./file2.csv", method = "curl", mode="wb")

file2 <- read.csv("task2.csv")
sum(file2$VAL == 24, na.rm = TRUE)

[1] 53
```


## Task 3
### Зчитайте xml файл за посиланням http://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Frestaurants.xml Скільки ресторанів мають zipcode 21231?
```{r}
library(XML)
download.file("http://d396qusza40orc.cloudfront.net/getdata%2Fdata%2Frestaurants.xml","file3.xml", "auto", TRUE,"wb")
file3 <- xmlRoot(xmlTreeParse("file3.xml", useInternal = TRUE ))
sum(xpathSApply(file3, "//zipcode", xmlValue) == 21231)

[1] 127
```

