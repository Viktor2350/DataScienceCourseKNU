# Для лабораторної роботи необхідно завантажити zip файл з даними за посиланням: «https://www.dropbox.com/s/i9wi47oyhfb7qlh/rprog_data_specdata.zip?dl=0».
```{r}
setwd("C:/Users/ryjuk/Downloads")
```
# 1. Написатифункціюpmean,якаобчислюєсереднєзначення(mean) забруднення сульфатами або нітратами серед заданого переліка моніторів. Ця функція приймає три аргументи: «directory», «pollutant», «id». Directory – папка, в якій розміщені дані, pollutant – вид забруднення, id – перелік моніторів. Аргумент id має значення за замовчуванням 1:332. Функція повинна ігнорувати NA значення.

```{r}
pmean("specdata", "sulfate", 1:3)
```
Результат:[1] 4.389262

```{r}
pmean("specdata", "sulfate", 1:10)
```
Результат: [1] 4.064128

```{r}
pmean("specdata", "sulfate", 55)
```
Результат: [1] 3.587319

```{r}
pmean("specdata", "nitrate")
```
Результат: [1] 1.702932

# 2. Написати функцію complete, яка виводить кількість повних спостережень (the number of completely observed cases) для кожного файлу. Функція приймає два аргументи: «Directory» та «id» та повертає data frame, в якому перший стовпчик – ім’я файлу, а другий – кількість повних спостережень.
```{r}
complete("specdata", 1)
Результат:
  id nobs
1  1  117
complete("specdata", c(2, 4, 8, 10, 12))
Результат
  id nobs
1  2 1041
2  4  474
3  8  192
4 10  148
5 12   96
complete("specdata", 50:60)
Результат:
   id nobs
1  50  459
2  51  193
3  52  812
4  53  342
5  54  219
6  55  372
7  56  642
8  57  452
9  58  391
10 59  445
11 60  448
```
# 3. Написати функцію corr, яка приймає два аргументи: directory (папка, де знаходяться файли спостережень) та threshold (порогове значення, за замовчуванням дорівнює 0) та обчислює кореляцію між сульфатами та нітратами для моніторів, кількість повних спостережень для яких більше порогового значення. Функція повинна повернути вектор значень кореляцій. Якщо ні один монітор не перевищує порогового значення, функція повинна повернути numeric вектор довжиною 0. Для обчислення кореляції між сульфатами та нітратами використовуйте вбудовану функцію«cor» з параметрами за замовчуванням.

```{r}
cr <- corr("specdata", 150)
head(cr); summary(cr)
Результат:
[1] -0.01895754 -0.14051254 -0.04389737 -0.06815956 -0.12350667 -0.07588814
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
-0.21057 -0.04999  0.09463  0.12525  0.26844  0.76313 
cr <- corr("specdata", 400)
head(cr); summary(cr)
Результат:
[1] -0.01895754 -0.04389737 -0.06815956 -0.07588814  0.76312884 -0.15782860
    Min.  1st Qu.   Median     Mean  3rd Qu.     Max. 
-0.17623 -0.03109  0.10021  0.13969  0.26849  0.76313
cr <- corr("specdata", 5000)
head(cr); summary(cr); length(cr)
Результат:
numeric(0)
   Min. 1st Qu.  Median    Mean 3rd Qu.    Max. 
                                                
[1] 0
```
