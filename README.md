# Module-9-Visualization-in-R

# Load necessary libraries
library(lattice)
library(ggplot2)

# Load the dataset
affairs <- read.csv("C:/Users/kinda/OneDrive/Documents/Affairs.csv")

# View the structure of the dataset
str(affairs)

# 1. Base R Visualization: Histogram of affairs

hist(affairs$affairs, 
     main = "Base R: Histogram of Affairs", 
     xlab = "Number of Affairs", 
     col = "pink", 
     border = "black")


# 2. Lattice Visualization: Density Plot by Marital Status

densityplot(~ affairs | factor(yearsmarried), 
            data = affairs, 
            main = "Lattice: Affairs by Marital Status", 
            xlab = "Number of Affairs", 
            col = "black")


# 3. ggplot2 Visualization: Scatter Plot of Affairs by Gender

library(ggplot2)
ggplot(affairs, aes(x = age, y = affairs)) +
  geom_point(color = "black") +
  labs(title = "ggplot2: Age vs. Number of Affairs", 
       x = "Age", 
       y = "Number of Affairs")

