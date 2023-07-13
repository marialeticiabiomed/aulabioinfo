install.packages("ggplot2")
library(ggplot2)

library(readxl)
dadosleticia <- read_excel("Bioinfo/dadosleticia.xlsx")
View(dadosleticia)

data= dadosleticia
data$CD3mm2 <- as.double(as.character(data$CD3mm2))
ggplot(data,aes(x =Nome, y =CD3mm2, color =Nome)) + 
  
geom_point(aes(size=CD3mm2, color= CD3mm2))+
  scale_colour_gradient(low="pink",high="purple")+
  labs(x= "Patients", y="CD3mm2", title="Mean CD3+ cell count in pregnant women with COVID-19", 
       color="") 
rlang::last_trace()

#Dúvidas:
renomear as pacientes p/ paciente 1,2,3
Nome da escala de cor
ordenar a escala do size
