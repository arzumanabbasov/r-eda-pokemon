# install required libraries
install.packages(c("readr", "RColorBrewer", "ggplot2", "treemapify", "dplyr"))

# load required libraries
library(readr)
library(RColorBrewer)
library(ggplot2)
library(treemapify)
library(dplyr)

# loading dataset
pokemon <- read_csv("Pokemon.csv")

# show dataset
head(pokemon)

## Analyzing Dataset

# information about data
cat("Number of rows: ", nrow(pokemon))
cat("\nNumber of columns: ", ncol(pokemon))
cat("\nNumber of rows with null values: ", sum(is.na(pokemon)))

# creating new dataset with types and number of pokemons
types <- as.data.frame(table(pokemon$`Type 1`))
# show new dataset
head(types)

# create treemap visualization of types and number of pokemons
treemap_types <- ggplot(types, aes(area = Freq, fill = Var1, label = paste(Var1, Freq, sep = "\n"))) +
  geom_treemap() +
  geom_treemap_text(colour = "white", place = "centre", size = 15)
print(treemap_types + mynamestheme + labs(title = "Types and Number of Pokemons"))

# create new dataset with Types and Total columns
types_by_total <- as.data.frame(aggregate(pokemon$Total, list(pokemon$`Type 1`), FUN = mean))
# show new dataset
head(types_by_total)

# create bar chart presenting types_by_total dataset
barplot(types_by_total$x, names.arg = types_by_total$`Group.1`, xlab = "Types", ylab = "Total", col = "darkblue")

# create new dataset with generation and number of pokemons
generation <- as.data.frame(table(pokemon$Generation))

# create pie chart for generations
pie(generation$Freq, labels = generation$Var1, main = "Generations", col = brewer.pal(6, "PuBu"))

# analyze how many pokemons are legendary or not
legbar <- ggplot(data = pokemon, aes(x = Legendary)) + geom_bar(fill = "deepskyblue4")
print(legbar + mynamestheme + labs(title = "Is Legendary?", y = "Number of pokemons", x = "True or False"))

# General information about pokemon's physical abilities
cat("Minimum of Sp Attack: ", min(pokemon$`Sp. Atk`))
cat("\nMaximum of Sp Attack: ", max(pokemon$`Sp. Def`))
cat("\nMinimum of HP: ", min(pokemon$HP))
cat("\nMaximum of HP: ", max(pokemon$HP))
