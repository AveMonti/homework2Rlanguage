#zad1 Utworz listę temp złozoną z siedmiu elementów. Każdy element jest wektorem złożonym z 5 losowych liczb rzeczywistych (postaraj się użyć funkcji lapply).
createVec <- function(count){
  sample(1:25, 5, rep=FALSE)
}
temp <- lapply(1:7, createVec)

# Do listy temp dołącz nazwy dni tygodnia. 
temp[[length(temp)+1]] <- c("Pon", "Wt","Sr","Czw","Pi","So","Nie")
#Dla listy temp
#zad1a Wygeneruj wektor z minimalnymi temperaturami każdego dnia.
sapply(temp[1:7], FUN= min)

tabela.danych <- data.frame(sapply(temp[1:7], FUN= min),temp[8])
names(tabela.danych)<- c("min temp","dzien")
#zad1b Wygeneruj wektor z maksymalnymi temperaturami każdego dnia.
sapply(temp[1:7], FUN= max)

tabela.danych <- data.frame(sapply(temp[1:7], FUN= max),temp[8])
names(tabela.danych)<- c("max temp","dzien")

#zad2 Wczytaj zbiór USArrests.csv
#https://raw.githubusercontent.com/vincentarelbundock/Rdatasets/master/csv/datasets/USArrests.csv
ds <- read.csv("https://raw.githubusercontent.com/vincentarelbundock/Rdatasets/master/csv/datasets/USArrests.csv")
# następnie podaj wektor, którego elementy to sumy przestępstw każdego rodzaju.
sapply(ds[2:5], sum)

#zad3 Napisz funkcję, która dla danego wektora zwróci wartości powyżej średniej tego wektora.
