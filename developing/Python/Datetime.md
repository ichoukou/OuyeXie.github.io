# Timezone

```
import pytz  
dt.replace(tzinfo=pytz.utc).astimezone(pytz.timezone('Asia/Shanghai'))  
```
 
 - https://pypi.python.org/pypi/python-dateutil/2.5.0
 - [Datetime中offset-naive与offset-aware时间的计算](http://www.dannysite.com/blog/185/)
 - [Can't subtract offset-naive and offset-aware datetimes](http://stackoverflow.com/questions/796008/cant-subtract-offset-naive-and-offset-aware-datetimes)
 - [datetime的时区(time zone)转换](http://agile-boy.iteye.com/blog/719047)