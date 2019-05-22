# Індивідуальне завдання

## Набір данних
Набір данних складається з денних логів трафіку в Чікаго.

З даного набору даних можна дізнатися багато цікавої інформації: регіонів з найвищою щільністю трафіку, сезонності та ін., яку пізніше можна використати для моделювання нової інфраструктури, або планування масових заходів.


## Написати R script для завантаження даних в R.
```{r}
f <- read.csv('ind.csv');
f
```
```cmd
```

###Підключимо необхідні бібліотеки
```{r}
library(ggmap)
library(tidyverse)
library(RColorBrewer)
library(lubridate)
```


###Виведемо самері 
```{r}
places <- read.csv(file="ind.csv",head=TRUE)
summary(places)
```
```cmd
```
##№ Підготуємо дати
```{r}
places$Date.of.Count <- as.factor(places$Date.of.Count)
places$Date.of.Count <-strptime(places$Date.of.Count,format="%m/%d/%Y")
places$Date.of.Count <-as.Date(places$Date.of.Count,format="%m-%Y")

places[, "month"] <- format(places[,"Date.of.Count"], "%m" )

head(places)
```
```cmd
```

###Візуалізуємо по датам
```{r}

aggr <- aggregate(x = places$Total.Passing.Vehicle.Volume,
                     FUN = sum,
                     by = list(Group.date = places$month))
plot(aggr, type="o", col="blue")

```
```cmd
```

###реєструємо АПІ для гугл карт
```{r}
register_google(key = "AIzaSyBVj1Y8sJgH7rUBkzFqaG5fV3VZV7jfRzc")
```
###Карта
```{r}
ggmap(map.tokyo, zoom = 11) +
geom_point(data = places, aes(x = Longitude, y = Latitude, fill = Total.Passing.Vehicle.Volume), size = 1, shape = 20, inherit.aes = FALSE) + scale_color_gradient(low="blue", high="red")
```
```cmd
```

###Щільність транспорту
```{r}
ggmap(map.tokyo, zoom = 11) +
stat_density_2d(data = places,
                  aes(x = Longitude,
                      y = Latitude,
                      fill = stat(level)),
                  alpha = .1,
                  bins = 25,
                  geom = "polygon") +
  scale_fill_gradientn(colors = brewer.pal(7, "YlOrRd"))
```
```cmd
```

## Висновки
### 1. Найбільш напруженим сезоном з точки зору трафіку в Чікаго - є осінь.
### 2. Очікуванно центр міста є найбільш загруженим.
### 3. В центрі міста денна кількість транспорту може сягати 165 200 авто, в той час як середня кількість по місту - ~20 000.