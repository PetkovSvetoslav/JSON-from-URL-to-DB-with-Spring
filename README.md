# JSON-from-URL-to-DB-with-Spring

Micro-service that gets the Covid-19 statistics 
from the URL https://api.covid19api.com/summary

Use Spring Boot, MySql

For DB We create a basic Summary with @Embedded two table:
Country(lyke a List from many Countryes) and static Global.
Premium is empty object but is @Embedded to Country.

We create the required SummaryRepository, CountryRepository(with query/metod findByCountryCode)
and SummaryService(with query/metod saveCovidData) with SummaryServiceImpl to work.

We have a rest endpoint /country/{COUNTRYCODE) 
where the country code is that two letter string, like BG for Bulgaria and DE for Germany
This is create With anotation
@GetMapping("/country/{countryCode}")
@ResponseBody
and Regex for Capital letters only
that return countryRepository method for finding Country Code.

Start:
@SpringBootApplication
public class JsonToDbApplication
