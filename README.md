# zad1 Utworz list?? temp z??ozon?? z siedmiu element??w. Ka??dy element jest wektorem z??o??onym z 5 losowych liczb rzeczywistych (postaraj si?? u??y?? funkcji lapply).
createVec <- function(count){
  sample(1:25, 5, rep=FALSE)
}
temp <- lapply(1:7, createVec)

# Do listy temp do????cz nazwy dni tygodnia. 
temp[[length(temp)+1]] <- c("Pon", "Wt","Sr","Czw","Pi","So","Nie")
# Dla listy temp
# zad1a Wygeneruj wektor z minimalnymi temperaturami ka??dego dnia.
sapply(temp[1:7], FUN= min)

tabela.danych <- data.frame(sapply(temp[1:7], FUN= min),temp[8])
names(tabela.danych)<- c("min temp","dzien")
# zad1b Wygeneruj wektor z maksymalnymi temperaturami ka??dego dnia.
sapply(temp[1:7], FUN= max)

tabela.danych <- data.frame(sapply(temp[1:7], FUN= max),temp[8])
names(tabela.danych)<- c("max temp","dzien")

# zad2 Wczytaj zbi??r USArrests.csv

ds <- read.csv("https://raw.githubusercontent.com/vincentarelbundock/Rdatasets/master/csv/datasets/USArrests.csv")

# nast??pnie podaj wektor, kt??rego elementy to sumy przest??pstw ka??dego rodzaju.

sapply(ds[2:5], sum)

# zad3 Napisz funkcj??, kt??ra dla danego wektora zwr??ci warto??ci powy??ej ??redniej tego wektora.

meanVec <- function(vec) {
  return(mean(vec))
}

usedcars <- read.csv("https://raw.githubusercontent.com/stedy/Machine-Learning-with-R-datasets/master/usedcars.csv")

sapply(usedcars["price"], meanVec)

sapply(usedcars["mileage"], meanVec)


