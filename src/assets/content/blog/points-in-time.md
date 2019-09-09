---
title: Points in time and our names for them
author: Doogie
date: 2019-08-01
hero_image: "/src/assets/content/images/time-abstract.jpg"
---

Somehow humans always seem to have some problems to wind their heads around the concept of time itself. For us ‚time‘ is and always has been a topic of longer discussions.

Actually time is something very simple: It is a dimension, that everything constantly travels along in the same direction. We cannot change the speed or direction of our travel along this time axis. It’s just always there.

Now we’ve invented names for certain points in time. But due to our limit thinking of „day and night“, we’ve come up with [several systems](https://en.wikipedia.org/wiki/Time_zone) that assign different names for the same point in time. For example January 1st, 1970 12:00 o’clock GMT (or UTC) is the same as January 1st, 1970, 14:00 o’clock in UTC-02:00 (Brazil). This is actually the same point in time in the universe. But depending in which time zone you currently are, you’d assign this [instant](https://docs.oracle.com/javase/8/docs/api/java/time/Instant.html) a different name.

Computers generally calculate in [milliseconds since the epoc](http://currentmillis.com/), ie. the number of milliseconds that have passed since one defined moment in time. This has the advantage, that two of those millis can easily be subtracted from each other, to get the difference between the two points in time. But this format needs to be converted to your local representation, according to your local time zone.