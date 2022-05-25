# 1. . Створити змінні базових (atomic) типів. Базові типи: character, numeric,  integer, complex, logical:
---
```{r}
z = 1 + 2i
у = as.integer(5)
x = 11
t = TRUE
c = as.character(3.14)
s = "GOLF"
```
# 2. Створити вектори, які: містить послідовність з 5 до 75; містить числа 3.14, 2.71, 0, 13; 100 значень TRUE
---
```{r}
vector1 <- 5:75
vector2 <- c(3.14, 2,71, 0, 13)
vector3 <- c(rep(x = TRUE, times = 100))
```
# 3. Створити наступну матрицю за допомогою matrix, та за допомогою cbind або rbind"
---
```{r}
m1 <- matrix(c(0.5, 1.3, 3.5, 3.9, 131, 2.8, 0, 2.2, 4.6, 2, 7, 5.1), nrow = 4, ncol = 3, byrow = TRUE)
print(m1)
r1 <- c(0.5,1.3,3.5)
r2 <- c(3.9,131, 2.8)
r3 <- c(0, 2.2, 4.6)
r4 <- c(2, 7, 5.1)
m2 <- rbind(r1, r2, r3, r4)
Pезультат:
 m1
     [,1]  [,2] [,3]
[1,]  0.5   1.3  3.5
[2,]  3.9 131.0  2.8
[3,]  0.0   2.2  4.6
[4,]  2.0   7.0  5.1

Pезультат:
 m2
   [,1]  [,2] [,3]
r1  0.5   1.3  3.5
r2  3.9 131.0  2.8
r3  0.0   2.2  4.6
r4  2.0   7.0  5.1
```
# 4. Створити довільний список (list), в який включити всі базові типи.:
---
```{r}
list<- list("KNUP", c(23,32,17), TRUE, 32.23, 1+4i,5L)
```
# 5. Створити фактор з трьома рівнями «baby», «child», «adult».
---
```{r}
f <- factor(c("baby", "child", "adult", "child", "baby", "adult"), 
            levels = c("baby", "child", "adult"))

```  
# 6. Знайти індекс першого значення NA в векторі 1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11. 
---
```{r}
i <- c(1, 2, 3, 4, NA, 6, 7, NA, 9, NA, 11) 
match(c(NA),i)
sum(is.na(i))

Pезультат: [1] 5
Pезультат: [1] 3
```
# 7. Створити довільний data frame та вивести в консоль.:
---
```{r}
name <- c("Ivan","Viktor","Alex","Maksym","Pavel")
age <- c(20,23,32,55,79)
city <- c("BT","Kyiv","Dnipro","Mariupol","Bucha")
peoples <- data.frame(Name = name, Age = age, City = city)
```
# 8. Змінити імена стовпців цього data frame.:
---
```{r}
names(peoples) <- c('FirstName', 'Years', 'Place')
Результат:
  FirstName Years    Place
1      Ivan    20       BT
2    Viktor    23     Kyiv
3      Alex    32   Dnipro
4    Maksym    55 Mariupol
5     Pavel    79    Bucha
```
