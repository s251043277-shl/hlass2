library(tidyverse)
library(plotly)

data_filtered_res <- X031.assignment.2 %>% 
  filter(Pressure == 300, Temperature == 373)

machine1_data_res <- data_filtered_res %>% 
  filter(Machine == 1) %>% 
  pull(PartResistance)

machine2_data_res <- data_filtered_res %>% 
  filter(Machine == 2) %>% 
  pull(PartResistance)

t_test_result_res <- t.test(machine1_data_res, machine2_data_res)
print(t_test_result_res)

plot_df_res <- data_filtered_res %>% 
  select(Machine, PartResistance) %>% 
  mutate(Machine = factor(Machine, levels = c(1, 2), labels = c("Machine 1", "Machine 2")))

p_res <- plot_ly(plot_df_res, y = ~PartResistance, color = ~Machine, type = "box", 
             colors = c("#0072B2", "#D55E00")) %>% 
  layout(title = list(text = "Part Resistance: Machine 1 vs. Machine 2 (P=300, T=373)", font = list(size = 18, color = "#000000")),
         yaxis = list(title = list(text = "Part Resistance", font = list(size = 18, color = "#000000")),
                      tickfont = list(size = 14, color = "#000000")),
         xaxis = list(title = list(text = "Machine", font = list(size = 18, color = "#000000")),
                      tickfont = list(size = 14, color = "#000000")),
         plot_bgcolor = "#ffffff",
         paper_bgcolor = "#ffffff",
         boxmode = "group")

htmlwidgets::saveWidget(p_res, file = "media/plots/machine_part_resistance_boxplot_p300_t373.html", selfcontained = TRUE)

