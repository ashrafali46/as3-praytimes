as3-praytimes
=============

Pray Times provides a set of handy functions to calculate prayer times for any location around the world, based on a variety of calculation methods currently used in Muslim communities.

The code is originally written in JavaScript. This manual provides information on how to use the code on a web-page or a [JavaScript-based](http://praytimes.org/manual/) application to display prayer times.


<b>CalculationMethod:</b><br/>
   Muslim World League<br/>
   Islamic Society of North America (ISNA)<br/>	
   Egyptian General Authority of Survey<br/>
   Umm al-Qura University, Makkah<br/>
   120 min during Ramadan<br/>
   University of Islamic Sciences, Karachi<br/>
   Institute of Geophysics, University of Tehran<br/>	
   Shia Ithna Ashari, Leva Research Institute, Qum<br/>

<b>Latitude of your city<br/>
Longitude of your city<br/>
Rise Angle :</b> for sunrise and sunset offset default value is 0.833 + sun angle<br/> 
<b>Time Zone : </b>if NaN, calculate by date<br/>
<b>HighLats :</b><br/>
   Middle of night<br/>
   Angle/60th of night<br/>
   1/7th of night<br/>
   No adjustment<br/>

```ActionScript
var date:Date = new Date();
var pt:PrayTimes = new PrayTimes(CalculationMethod.TEHRAN, 35.6961, 51.4231, 0);
var dts:Vector.<Date> = pt.getTimes(date).toDates();
trace(pt.getTimes(date).toTimeFormatString());
for each(var d:Date in dts)
	trace(d, d.milliseconds);
	
//[trace] imsak: 05:16, fajr: 05:26, sunrise: 06:51, dhuhr: 13:08, asr: 16:42, sunset: 19:26, maghrib: 19:44, isha: 20:32, midnight: 00:26
//[trace] Sat Apr 1 05:15:39 GMT+0430 2017 791
//[trace] Sat Apr 1 05:25:39 GMT+0430 2017 791
//[trace] Sat Apr 1 06:50:56 GMT+0430 2017 77
//[trace] Sat Apr 1 13:08:09 GMT+0430 2017 786
//[trace] Sat Apr 1 16:41:56 GMT+0430 2017 21
//[trace] Sat Apr 1 19:25:57 GMT+0430 2017 125
//[trace] Sat Apr 1 19:44:11 GMT+0430 2017 57
//[trace] Sat Apr 1 20:31:53 GMT+0430 2017 259
//[trace] Sun Apr 2 00:25:48 GMT+0430 2017 458

```
