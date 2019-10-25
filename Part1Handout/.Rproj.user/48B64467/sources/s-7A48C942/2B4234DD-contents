install.packages('plotly')
library(plotly)
df <- read.csv("StateDataforMap_2018.csv")
state_abbs <- state.abb[match(df$STATENAME,state.name)]
newdf <- data.frame(state = df$STATENAME,levels = substr(df$ACTIVITY.LEVEL,7,8),levelLabel = df$ACTIVITY.LEVEL.LABEL,state_codes = state_abbs)

newdf <- newdf[-c(9,52,53,54),]
newdf
g <- list(
  scope = 'usa',
  projection = list(type = 'albers usa'),
  showlakes = TRUE,
  lakecolor = toRGB('white')
)

p <- plot_geo(newdf, locationmode = 'USA-states') %>%
  add_trace(
    z = ~levels, text = ~levelLabel,locations = ~state_codes,colors = 'Purples')%>%
    layout(geo = list(scope = 'usa',projection = list(type = 'albers usa')), title = '201-19 Influenza Season week 4 ILI Activity level indicator \n (Hower to breakdown)')
p

