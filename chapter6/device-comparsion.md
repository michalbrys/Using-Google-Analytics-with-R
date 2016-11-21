## Device comparsion

Let's check how users are engaged on different types of device. To do this, we'll plot 2 charts - describing how many sessions were made from different types of devices and what is avgSessionDuration \(in seconds\) on a particular device type.

```
# device comparsion

# install libraries
# install.packages("googleAuthR")
# install.packages("googleAnalyticsR")
# install.packages("ggplot2")

# load libraries
library("googleAuthR")
library("googleAnalyticsR")
library("ggplot2")

# authorize the connection with Google Analytics servers
ga_auth()

## pick a profile with data to query
#ga_id <- account_list[275,'viewId']

# or give it explicite using tool http://michalbrys.github.io/ga-tools/table-id.html in format 99999999
ga_id <- 00000000

gadata <- google_analytics(id = ga_id, 
                           start="2015-01-01", end="2016-06-30", 
                           metrics = c("sessions", "avgSessionDuration"),
                           dimensions = c("date", "deviceCategory"),
                           max = 5000)


# plot sessions with deviceCategory
ggplot(gadata, aes(deviceCategory, sessions)) +   
  geom_bar(aes(fill = deviceCategory), stat="identity")

# plot avgSessionDuration with deviceCategory
ggplot(gadata, aes(deviceCategory, avgSessionDuration)) +   
  geom_bar(aes(fill = deviceCategory), stat="identity")
```

![](/assets/7_bar_chart.png)

In this case the longest sessions were made from mobile devices.

## Source code

The complete source code of the examples showed above is in my GitHub repository:

[github.com\/michalbrys\/R-Google-Analytics\/blob\/master\/7\_device\_comparsion.R](https://github.com/michalbrys/R-Google-Analytics/blob/master/7_device_comparsion.R)

