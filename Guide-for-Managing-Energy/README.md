# Notes on Solar Power and the BeLL

Here are some calculations and notes that should help people to understand what kind of Solar Power solution they will need to support their BeLL System.


# Interesting points to consider before calculations

"The terms power and energy are frequently confused. Power is the rate at which energy is generated or consumed. For example, when a light bulb with a power rating of 100W is turned on for one hour, the energy used is 100 watt hours (W·h)..."
-- http://en.wikipedia.org/wiki/Watt#Confusion_of_watts.2C_watt-hours.2C_and_watts_per_hour

"Starter batteries are designed to deliver short, high-current bursts for starting the engine, and are designed to discharge only a very small part of their capacity. A daily cycle of using most the capacity would corrode a car battery very quickly, the plates and the chemistry are designed to stay nearly 100% fully charged most of the time."
-- http://voltaicsystems.com/blog/choosing-a-lead-acid-battery-for-solar-charging/

"Deep cycle batteries are designed with larger plates and different chemistry to avoid the corrosive effect of frequently using the full capacity. They are designed to be regularly deeply discharged using most of its capacity."
-- http://voltaicsystems.com/blog/choosing-a-lead-acid-battery-for-solar-charging/


# Calculating amount of energy the tablets store at full charge

The 7" OLE tablet batteries have energy of 3.5Ah running at 3.7V.

3.5Ah x 3.7V = 13 Watt Hours per Tablet battery charge

13 Watt Hours x 35 tablets =  455 Watt Hours of energy required to charge 35 Tablets


# Calculating the energy requirements of a parent battery that could fully charge the Tablet batteries  

If the tablets are receiving 12V from a 12V battery, the energy capacity of that battery would require 38Ah.

355 Watt Hours / 12v = 29.6Ah

But this is not quite correct, there is efficiency loss in the Tablet batteries that must be taken into account. The tablet batteries may be able to deliver 13 Watt Hours but you have to give more power due to the efficiency loss.

The efficiency of the Lithium Ion batteries in tablets are...
"Charge/discharge efficiency  80–90%[3]"
-- http://en.wikipedia.org/wiki/Lithium-ion_battery

So the power capacity of a 12V parent battery would need to be ...

(355 Watt hours / .8 efficiency) / 12V = 37Ah

Again, this is not quite correct. There is efficiency loss in converting the 12V the battery provides to the 5V the Tablets require to charge. I'm guessing for now that there is an efficiency of .8.

37Ah / .8 efficiency = 46Ah

So in conclusion, a parent battery @12V that can charge 35 tablets would need 46Ah of energy capacity.  Luckily, the deep cycle (not a starter battery as found in cars) lead acid battery recommended in the blog post by Voltaic Systems is a 12V 51Ah battery. This battery sells for around $500.
-- http://www.xantrex.com/power-products/backup-power/xpower-powerpack-1500.aspx
-- http://www.amazon.com/Xantrex-802-1500-XPower-Portable-Powerpack/dp/B00005RHQQ


# Solar Power example 1: Calculating the power requirements to charge a parent battery in 8 hours

Let's say we get 8 hours of direct sunlight and the lead acid battery operates at 80% efficiency.  How many Watts would a solar panel need to provide for the battery to have potential energy of 46Ah?

"If lead acid batteries are maintained properly, they will function at 80-90% efficiency."
-- http://voltaicsystems.com/blog/choosing-a-lead-acid-battery-for-solar-charging/

(46Ah / .8 efficiency) / 8 hours = 7.2A @ 12V = 86.4 Watts  

Here's an example of a 100 Watt solar panel for $380.
-- http://www.amazon.com/Instapark-PowerBox-Fold-n-Go-Solar-powered-Controller/dp/B007VWW8X2/ref=sr_1_8?ie=UTF8&qid=1359556099&sr=8-8&keywords=100watt+solar+panel

Total up front cost of power supply for 35 tablets: $880

Power supply cost per tablet: $25

Tablet price: $65 for a OLE 7" Tablet

Total up front cost of one tablet: $90

* Recurring fee of $500 depending on the battery life (2 years?)



# Solar Power example 2: Calculating the power requirements to charge a parent battery in 40 hours

* This calculation assumes the Nook Simple Touch has the same battery as the OLE 7" Tablet but only has to be charged once a week.

Let's say we get 40 hours of direct sunlight and the lead acid battery operates at 80% efficiency.  Usage of this would mean you get to charge the parent battery during the weekdays and then the parent battery powers the tablets over the weekend.  How many Watts would a solar panel need to provide for the battery to have potential energy of 46Ah?

(46Ah / .8 efficiency) / 40 hours = 1.4A @ 12V = 16.8 Watts   

Here's an example of a 16.8 Watt solar panel for $160.
-- http://www.voltaicsystems.com/16wattkit.php

Total up front cost of power supply for 35 tablets: $680

Tablet Price: $80 for a Nook Simple Touch

$680 / 35 tablets = $19 cost of power per tablet

Total up front cost of one tablet: $99

* Recurring fee of $500 depending on the battery life (2 years?)


# Solar Power Example 3: Calculating the power requirements to charge tablets directly in 16 hours (over the weekend with no parent battery)

* This calculation assumes the Nook Simple Touch has the same battery as the OLE 7" Tablet but only has to be charged once a week.

Because we are bypassing a parent battery, we can take out one of the efficieny losses.  

46Ah / 16 hours = 2.875A @ 5V = 14.3 Watts

Here's an example of a 16.8 Watt solar panel for $160.
-- http://www.voltaicsystems.com/16wattkit.php

Total up front cost of power supply for 35 tablets: $160

Tablet Price: $80 for a Nook Simple Touch

$160 / 35 tablets = $4.50 cost of power per tablet

Total up front cost of one tablet: $84.50


# Notes on low power issues from National Grid

"Most United States, Canada and Mexico domestic power suppliers run at 120 V. Household circuit breakers typically provide a maximum of 15 A or 20 A of current to a given set of outlets."

120V x 15A = 1800 Watts

How much power is being provided to outlets is important to know.  At some of the schools where we observe "low power", this may be the case because of how many devices they are trying to charge (light bulbs, fans, refrigerators, computers, etc.).  For example, if the tablets can charge their battery in an hour, then the max number of tablets you can charge in a house in North American would be...

1800 Watts in a house / 13 Watts per tablet = 138.5 tablets can be charged in one house. In Ghana, I'd assume that power capacity would be much lower than 1800 Watts. This is something to keep in mind.