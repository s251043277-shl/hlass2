library(tidyverse)
library(plotly)

data_filtered_len <- X031.assignment.2 %>% 
  filter(Pressure == 300, Temperature == 373)

machine1_data_len <- data_filtered_len %>% 
  filter(Machine == 1) %>% 
  pull(PartLength)

machine2_data_len <- data_filtered_len %>% 
  filter(Machine == 2) %>% 
  pull(PartLength)

t_test_result_len <- t.test(machine1_data_len, machine2_data_len)
print(t_test_result_len)

plot_df_len <- data_filtered_len %>% 
  select(Machine, PartLength) %>% 
  mutate(Machine = factor(Machine, levels = c(1, 2), labels = c("Machine 1", "Machine 2")))

p_len <- plot_ly(plot_df_len, y = ~PartLength, color = ~Machine, type = "box", 
             colors = c("#0072B2", "#D55E00")) %>% 
  layout(title = list(text = "Part Length: Machine 1 vs. Machine 2 (P=300, T=373)", font = list(size = 18, color = "#000000")),
         yaxis = list(title = list(text = "Part Length", font = list(size = 18, color = "#000000")),
                      tickfont = list(size = 14, color = "#000000")),
         xaxis = list(title = list(text = "Machine", font = list(size = 18, color = "#000000")),
                      tickfont = list(size = 14, color = "#000000")),
         plot_bgcolor = "#ffffff",
         paper_bgcolor = "#ffffff",
         boxmode = "group")

htmlwidgets::saveWidget(p_len, file = "media/plots/machine_part_length_boxplot_p300_t373.html", selfcontained = TRUE)

