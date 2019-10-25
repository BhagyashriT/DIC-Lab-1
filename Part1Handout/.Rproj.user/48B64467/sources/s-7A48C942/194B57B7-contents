library(ggplot2)
df <- read.csv("./WHO_NREVSS_Public_Health_Labs.csv",header = T, sep = ",",skip = 1)
newDf <- df[,c(6,7,8,10,11,12)]
contributions <- colSums(newDf)
contributions <- as.data.frame(contributions)
allTypes <- c("Influenza A(H1N1)","Influenza A(H3N2)","Influenza A(Subtype Unknown)","Influenza B Victoria","Influenza B Yamagata","Influenza B(Image not determined)")
contributions <- data.frame(types = allTypes, contribs = contributions[,1])
pie2 = ggplot(contributions, aes(x = factor(1), y=contributions,fill=factor(types))) + geom_bar(width = 1,stat="identity")+coord_polar(theta = "y") + geom_text(aes(label = contributions),vjust="outward")
pie2                                                  
install.packages("plotly")
library(plotly)

layout.matrix <-(mat = matrix(c(1,2),nrow = 1,ncol = 2))
layout.matrix
p <- plot_ly(contributions, labels = ~types, values = ~contribs, type = 'pie',domain = list(x = c(0, 0.5),y=c(0,1)),showlegend = T) %>%
  layout(title = 'Influenza Positive Specimens',
         xaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE),
         yaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE))
p
genetic = read.csv("./Genetic07.csv")
slice1 <-genetic[c(6,7,8),]
p2 <- plot_ly(slice1, labels = ~Sequence.Genetic.Group, values = ~Distinct.count.of.Cdc.Id.., type = 'pie',domain = list(x = c(0.5, 0.8),y=c(0.5,0.7)),showlegend=T) %>%
  layout(title = 'Influenza A(H3N2)',
         xaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE),
         yaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE))

slice2 <- genetic[c(1,2,3),]
p3 <- plot_ly(slice2, labels = ~Sequence.Genetic.Group, values = ~Distinct.count.of.Cdc.Id.., type = 'pie',domain = list(x = c(0.5, 0.8),y=c(0.2,0.4)),showlegend=T) %>%
layout(title = 'Influenza A(H3N2)',
       xaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE),
       yaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE))

slice3 <- genetic[5,]
p4 <- plot_ly(slice3, labels = ~Sequence.Genetic.Group, values = ~Distinct.count.of.Cdc.Id.., type = 'pie',domain = list(x = c(0.8, 1),y=c(0.5,0.7)),showlegend=T) %>%
  layout(title = 'Influenza A(H3N2)',
         xaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE),
         yaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE))

slice4 <- genetic[4,]
p5 <- plot_ly(slice4, labels = ~Sequence.Genetic.Group, values = ~Distinct.count.of.Cdc.Id.., type = 'pie',domain = list(x = c(0.8, 1),y=c(0.2,0.4)),showlegend=T) %>%
  layout(title = 'Influenza A(H3N2)',
         xaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE),
         yaxis = list(showgrid = FALSE, zeroline = FALSE, showticklabels = FALSE))
p5
pl = subplot(p,p2,p3,p4,p5,shareX=F,shareY=F)%>%
  layout(showlegend = F)
pl

