# aulabioinfo
dados gestantes com covid

install.packages("ggplot2")
library(ggplot2)

library(readxl)
dadosleticia <- read_excel("Bioinfo/dadosleticia.xlsx")
View(dadosleticia)

data= dadosleticia
data$CD3mm2 <- as.double(as.character(data$CD3mm2))
ggplot(data,aes(x =data$Nome , y = data$CD3mm2, color = data$Nome)) + 
  geom_point(size =3) +
  theme(axis.title.x=element_blank(),
        axis.text.x=element_blank(),
        axis.ticks.x=element_blank())+
  labs(y="CD3mm2", title="Mean CD3+ cell count in pregnant women with COVID-19", 
       color="patients") 
rlang::last_trace()

