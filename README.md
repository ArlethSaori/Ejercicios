# Ejercicios
## 1.
> library(dplyr)
> especies <- data.frame(
+     especie = c("Ajolote", "Rana", "Serpiente", "Tortuga"),
+     habitat = c("Lago", "Río", "Bosque", "Lago"),
+     tamano = c(30, 10, 150, 50),
+     peso = c(150, 25, 1000, 500)
+ )
> 
> especies
> Especies_Lago <- filter(especies, habitat == "Lago")
> Especies_Lago
> Especies_ordenadas <- arrange(especies, desc(tamano))
> Especies_ordenados
## 2.
> install.packages("ggplot2")
> library(ggplot2)
> install.packages("gcookbook")
> library(gcookbook)
> iris[, c("Sepal.Length", "Sepal.Width")]
> ggplot(iris, aes(x=Sepal.Length, y=Sepal.Width)) + geom_point()
> iris[, c("Sepal.Length", "Sepal.Width", "Species")]
> ggplot(iris, aes(x=Sepal.Length, y=Sepal.Width, colour=Species)) + geom_point()
## 3.
> calificaciones <- data.frame( estudiante = c("Ana", "Carlos", "Lucía", "Jorge", "Ana", "Carlos", "Lucía", "Jorge"), asignatura = c("Matemáticas", "Matemáticas", "Matemáticas", "Matemáticas", "Historia", "Historia", "Historia", "Historia"), calificacion = c(95, 85, 92, 88, 78, 82, 85, 90) )
> promedios_calificaciones <- calificaciones %>% group_by(estudiante) %>% summarise(promedio = mean(calificacion))
> print(promedios_calificaciones)
## 4. 
> alturas <- data.frame(
+     nombre = c("Laura", "Pedro", "Sara", "Miguel"),
+     altura_cm = c(160, 175, 150, 180)
+ )
> alturas$altura_m <- alturas$altura_cm / 100
> print(alturas)
## 5.
> ventas <- data.frame(
  mes = c("Enero", "Febrero", "Marzo", "Abril", "Mayo", "Junio"),
  ventas = c(12000, 15000, 13000, 16000, 17500, 14000)
)
> library(ggplot2)
> ggplot(ventas, aes(x = mes, y = ventas)) + geom_bar(stat = "identity", fill = "skyblue") + labs(title = "Ventas mensuales", x = "Mes", y = "Ventas")

## 6. 
> productos <- data.frame(
+     producto = c("A", "B", "C", "D"),
+     precio = c(20, 35, 50, 10),
+     cantidad_vendida = c(100, 200, 150, 250)
+ )
> 
> productos <- productos %>%
+     mutate(ingresos = precio * cantidad_vendida)
> print(productos)

## 7.
> data(mtcars)
> mtcars
> ggplot(mtcars, aes(x = as.factor(cyl), y = mpg)) + geom_boxplot(fill = "lightblue") + labs(title = "Distribución de millas por galón según el número de cilindros", x = "Número de cilindros", y = "Millas por galón (mpg)") 
