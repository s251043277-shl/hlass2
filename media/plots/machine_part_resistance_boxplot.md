library(tidyverse)
library(plotly)

data_filtered <- X031.assignment.2 %>%
  filter(Pressure == 100, Temperature == 303)

machine1_data <- data_filtered %>%
  filter(Machine == 1) %>%
  pull(PartResistance)

machine2_data <- data_filtered %>%
  filter(Machine == 2) %>%
  pull(PartResistance)

t_test_result <- t.test(machine1_data, machine2_data)
print(t_test_result)

plot_df <- data_filtered %>%
  select(Machine, PartResistance) %>%
  mutate(Machine = factor(Machine, levels = c(1, 2), labels = c("Machine 1", "Machine 2")))

p <- plot_ly(plot_df, y = ~PartResistance, color = ~Machine, type = "box",
             colors = c("#0072B2", "#D55E00")) %>%
  layout(title = list(text = "Part Resistance: Machine 1 vs. Machine 2 (P=100, T=303)", font = list(size = 18, color = "#000000")),
         yaxis = list(title = list(text = "Part Resistance", font = list(size = 18, color = "#000000")),
                      tickfont = list(size = 14, color = "#000000")),
         xaxis = list(title = list(text = "Machine", font = list(size = 18, color = "#000000")),
                      tickfont = list(size = 14, color = "#000000")),
         plot_bgcolor = "#ffffff",
         paper_bgcolor = "#ffffff",
         boxmode = "group")

htmlwidgets::saveWidget(p, file = "media/plots/machine_part_resistance_boxplot.html", selfcontained = TRUE)

