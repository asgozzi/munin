# pweather_

Plugin to monitor data reported from a pywws-compatible weather station.


##Examples

![pweather_temp](http://www.vp44.net/storage/images/github/munin/weather_temp-month.png)

![pweather_hum](http://www.vp44.net/storage/images/github/munin/weather_hum-month.png)

![pweather_pres](http://www.vp44.net/storage/images/github/munin/weather_pres-month.png)


##Dependencies

- pywws

##Usage

+ (pywws) add/replace section in **weather.ini**:


> [live]

> services = []

> plot = []

> text = ['munin.txt']

> twitter = []

> yowindow = 


+ (pywws) create template munin.txt


>  #live# 

> CurTempOut.value #temp_out#

> CurTempIn.value #temp_in#

> CurHumOut.value #hum_out#

> CurHumIn.value #hum_in#

> CurPres.value #rel_pressure#

+ enable plugins


> ln -s /usr/share/munin/plugins/pweather\_ /etc/munin/plugins/pweather_temp

> ln -s /usr/share/munin/plugins/pweather\_ /etc/munin/plugins/pweather_pres

> ln -s /usr/share/munin/plugins/pweather\_ /etc/munin/plugins/pweather_hum

+ set munin.txt path in plugin configuration file for munin-node
