# exercise
plot1.
data <- read.table("household_power_consumption.txt", header=T, sep=";")
data = data[data$Date=="1/2/2007"|data$Date=="2/2/2007",]
data$date_time = paste(data$Date,data$Time)
data$date_time = strptime(data$date_time,"%d/%m/%Y %H:%M:%S")

png(filename="plot1.png",width = 480, height = 480)
hist(as.numeric(data$Global_active_power),col = "red",xlab="Global Active Power (kilowatts)",main="Global Active Power")
dev.off()
plot2.
data <- read.table("household_power_consumption.txt", header=T, sep=";")
data = data[data$Date=="1/2/2007"|data$Date=="2/2/2007",]
data$date_time = paste(data$Date,data$Time)
data$date_time = strptime(data$date_time,"%d/%m/%Y %H:%M:%S")

png(filename="plot2.png",width = 480, height = 480)
plot(data$date_time,data$Global_active_power, type="l",ylab="Global Active Power (kilowatts)",xlab="")
dev.off()
plot3.
data <- read.table("household_power_consumption.txt", header=T, sep=";")
data = data[data$Date=="1/2/2007"|data$Date=="2/2/2007",]
data$date_time = paste(data$Date,data$Time)
data$date_time = strptime(data$date_time,"%d/%m/%Y %H:%M:%S")

png(filename="plot3.png",width = 480, height = 480)
plot(data$date_time,data$Sub_metering_1, type="l",ylab="Global Active Power (kilowatts)",xlab="")
lines(data$date_time,data$Sub_metering_2, type="l",col="red")
lines(data$date_time,data$Sub_metering_3, type="l",col="blue")
legend("topright", legend=c("Sub_metering_1", "Sub_metering_2","Sub_metering_3"),
       col=c("black","red", "blue"), lty=1:1)
dev.off()
plot4.
data <- read.table("household_power_consumption.txt", header=T, sep=";")
data = data[data$Date=="1/2/2007"|data$Date=="2/2/2007",]
data$date_time = paste(data$Date,data$Time)
data$date_time = strptime(data$date_time,"%d/%m/%Y %H:%M:%S")

png(filename="plot4.png",width = 480, height = 480)
par(mfrow=c(2,2),mai=c(0.7,0.7,0.7,0.7))
plot(data$date_time,data$Global_active_power, type="l",ylab="Global Active Power (kilowatts)",xlab="")
plot(data$date_time,data$Voltage, type="l",ylab="Voltage",xlab="datatime")
plot(data$date_time,data$Sub_metering_1, type="l",ylab="Global Active Power (kilowatts)",xlab="")
lines(data$date_time,data$Sub_metering_2, type="l",col="red")
lines(data$date_time,data$Sub_metering_3, type="l",col="blue")
legend("topright", legend=c("Sub_metering_1", "Sub_metering_2","Sub_metering_3"),
       col=c("black","red", "blue"), lty=1:1,cex=0.8)
plot(data$date_time,data$Global_reactive_power, type="l",ylab="Global_reactive_power",xlab="datatime")
dev.off()
