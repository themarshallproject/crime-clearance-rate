# FBI Crime Clearances and Clearance Rate, 1970 to 2020
---

*The Marshall Project is a nonpartisan, nonprofit news organization that seeks to create and sustain a sense of national urgency about the U.S. criminal justice system. <b>If you appreciate our data releases, [support our work](https://www.themarshallproject.org/donate).</b>*

---

In 2020, law enforcement agencies across the country solved about 10,000 murders, which is nearly 50% of all murders that took place in the same year. This puts the murder clearance rate in 2020 at below 50%.

But the murder clearance rate can vary significantly by year and by police agency. The Marshall Project's analysis of the FBI's Uniform Reporting Program (UCR) data found that murders and manslaughters are most likely to be solved. Some crimes, like motor vehicle theft, have a clearance rate of about 12%.

As part of [our investigation into the homicide clearance rate](https://www.themarshallproject.org/2022/01/12/as-murders-spiked-police-solved-about-half-in-2020), we compiled agency-level crime data that the FBI gathered from 1970 to 2020, including how many crimes the agencies reported and how many crimes were solved each year. You can download the data in this repository.

We would also love to hear about how you use this data and how we can improve our data releases. You can reach Weihua Li at [wli@themarshallproject.org](mailto:wli@themarshallproject.org) or David Eads at [deads@themarshallproject.org](mailto:deads@themarshallproject.org) with questions or comments.

The FBI publishes a much larger dataset with more information they collected from each law enforcement agency. You can access that through the FBI's [Crime Data Explorer tool](https://crime-data-explorer.fr.cloud.gov/pages/downloads). 

The data we analyzed was first compiled by Jacob Kaplan, chief data scientist for the Research on Police Reform and Accountability (RoPRA) project at Princeton University. Here are his [data release page](https://www.openicpsr.org/openicpsr/project/100707/version/V17/view) and guides on how to use [UCR](https://ucrbook.com/) and [NIBRS](https://nibrsbook.com) data.

---

The data file includes these fields:

* `ori`: Originating Agency Identifier for law enforcement agencies; you can find [a crosswalk file here](https://www.icpsr.umich.edu/web/NACJD/studies/35158).
* `agency_name`: Name of the law enforcement agency that reported the data.
* `state`: State the agency is located.
* `year`: Reporting year.
* `fips_state_county_code`: Six-digit FIPS code for the county that the reporting agency is in. One county can have multiple law enforcement agencies.
* `number_of_months_missing`: Some law enforcement agencies only report their data to the FBI for a number of months out of the year. If the value of this field is 0, it means there's no missing data for the year. But if, for example, the value is 6, that means the law enforcement agency only reported six-months worth of data to the FBI.

There are three columns for each index {crime}. You can find [the FBI's definition of each offense here](https://ucr.fbi.gov/crime-in-the-u.s/2010/crime-in-the-u.s.-2010/offense-definitions). Violent crime includes murder and manslaughter, rape, robbery, and aggravated assault. Property crime includes burglary, larceny-theft, motor vehicle theft, and arson. Total crime includes violent and property crime.

* `new_{crime}`: Number of new crimes that were reported to the police.
* `cleared_{crime}`: Number of crimes that police solved in the calendar year, which can include crimes that took place in previous years.
* `clearance_rate_{crime}`: The number of cleared crimes divided by the number of new crimes.
