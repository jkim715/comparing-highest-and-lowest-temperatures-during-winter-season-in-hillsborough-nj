#project 1 comparing high and low temperatures by month in hillsborough nj during the winter 

setwd("C:\\Users\\Jonathan\\Pictures\\R Programming")
getwd()

project1 <- read.csv("temperature-hillsborough-nj-winter-2023.csv")
project1

#subsetting each month
dec_2023 <- project1[1:11,]
colnames(dec_2023) <- c("Date", "Highest", "Lowest")
dec_2023
summary(dec_2023)

jan_2024 <- project1[12:42,]
colnames(jan_2024) <- c("Date", "Highest", "Lowest")
jan_2024
summary(jan_2024)

feb_2024 <- project1[43:71,]
colnames(feb_2024) <- c("Date", "Highest", "Lowest")
feb_2024
summary(feb_2024)

mar_2024 <- project1[72:89,]
colnames(mar_2024) <- c("Date", "Highest", "Lowest")
mar_2024
summary(mar_2024)

#plotting each month

library(ggplot2)

dec_2023_date_order <- as.Date(dec_2023$Date, format = "%m/%d")

dec_2023_plot <- ggplot(data = dec_2023) + geom_point(aes(x = dec_2023_date_order, y = Highest, color = "Highest Temperature"), size = 2) +
  geom_line(aes(x = dec_2023_date_order, y = Highest), color = "Red", group = 1) +
  geom_point(aes(x = dec_2023_date_order, y = Lowest, color = "Lowest Temperature"), size = 2) +
  geom_line(aes(x = dec_2023_date_order, y = Lowest), color = "Blue", group = 1) +
  scale_colour_manual(name="Temperature", values = c("Highest Temperature"="Red", "Lowest Temperature"="Blue")) +
  xlab("Date") + ylab("Temperature (Fahrenheit)") +
  ggtitle("Highest & Lowest Temperature (Decemeber 2023)") +
  theme(axis.title.x = element_text(color = "DarkGreen", size = 15),
        axis.title.y = element_text(color = "DarkGreen", size = 15),
        axis.text.x = element_text(size = 10),
        axis.text.y = element_text(size = 10),
        plot.title = element_text(color = "DarkBlue", size = 20))
dec_2023_plot

jan_2024_date_order <- as.Date(jan_2024$Date, format = "%m/%d")

jan_2024_plot <- ggplot(data = jan_2024) + geom_point(aes(x = jan_2024_date_order, y = Highest, color = "Highest Temperature"), size = 2) +
  geom_line(aes(x = jan_2024_date_order, y = Highest), color = "Red", group = 1) +
  geom_point(aes(x = jan_2024_date_order, y = Lowest, color = "Lowest Temperature"), size = 2) +
  geom_line(aes(x = jan_2024_date_order, y = Lowest), color = "Blue", group = 1) +
  scale_colour_manual(name="Temperature", values = c("Highest Temperature"="Red", "Lowest Temperature"="Blue")) +
  xlab("Date") + ylab("Temperature (Fahrenheit)") +
  ggtitle("Highest & Lowest Temperature (January 2024)") +
  theme(axis.title.x = element_text(color = "DarkGreen", size = 15),
        axis.title.y = element_text(color = "DarkGreen", size = 15),
        axis.text.x = element_text(size = 10),
        axis.text.y = element_text(size = 10),
        plot.title = element_text(color = "DarkBlue", size = 20))
jan_2024_plot

feb_2024_date_order <- as.Date(feb_2024$Date, format = "%m/%d")

feb_2024_plot <- ggplot(data = feb_2024) + geom_point(aes(x = feb_2024_date_order, y = Highest, color = "Highest Temperature"), size = 2) +
  geom_line(aes(x = feb_2024_date_order, y = Highest), color = "Red", group = 1) +
  geom_point(aes(x = feb_2024_date_order, y = Lowest, color = "Lowest Temperature"), size = 2) +
  geom_line(aes(x = feb_2024_date_order, y = Lowest), color = "Blue", group = 1) +
  scale_colour_manual(name="Temperature", values = c("Highest Temperature"="Red", "Lowest Temperature"="Blue")) +
  xlab("Date") + ylab("Temperature (Fahrenheit)") +
  ggtitle("Highest & Lowest Temperature (February 2024)") +
  theme(axis.title.x = element_text(color = "DarkGreen", size = 15),
        axis.title.y = element_text(color = "DarkGreen", size = 15),
        axis.text.x = element_text(size = 10),
        axis.text.y = element_text(size = 10),
        plot.title = element_text(color = "DarkBlue", size = 20))
feb_2024_plot

mar_2024_date_order <- as.Date(mar_2024$Date, format = "%m/%d")

mar_2024_plot <- ggplot(data = mar_2024) + geom_point(aes(x = mar_2024_date_order, y = Highest, color = "Highest Temperature"), size = 2) +
  geom_line(aes(x = mar_2024_date_order, y = Highest), color = "Red", group = 1) +
  geom_point(aes(x = mar_2024_date_order, y = Lowest, color = "Lowest Temperature"), size = 2) +
  geom_line(aes(x = mar_2024_date_order, y = Lowest), color = "Blue", group = 1) +
  scale_colour_manual(name="Temperature", values = c("Highest Temperature"="Red", "Lowest Temperature"="Blue")) +
  xlab("Date") + ylab("Temperature (Fahrenheit)") +
  ggtitle("Highest & Lowest Temperature (March 2024)") +
  theme(axis.title.x = element_text(color = "DarkGreen", size = 15),
        axis.title.y = element_text(color = "DarkGreen", size = 15),
        axis.text.x = element_text(size = 10),
        axis.text.y = element_text(size = 10),
        plot.title = element_text(color = "DarkBlue", size = 20))
mar_2024_plot
