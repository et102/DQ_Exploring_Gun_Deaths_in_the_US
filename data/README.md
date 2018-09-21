# Data Readme

This README explains how to make best use of the data from the Stanford Open Policing Project. We provide an overview of the data, and a list of best practices for working with the data. 

Our analysis code and further documentation are available at [https://github.com/5harad/openpolicing](https://github.com/5harad/openpolicing).

### Overview of the data file structure


### Description of gun.csv

<table>
  <tr>
    <th>Column name</th>
    <th>Column meaning</th>
    <th>Example</th>
  </tr>
  <tr>
    <td>year</td>
    <td>the year in which the fatality occurred.</td>
    <td> - </td>
  </tr>
  <tr>
    <td>month</td>
    <td>Tthe month in which the fatality occurred.</td>
    <td>1-12</td>
  </tr>
  <tr>
    <td>intent</td>
    <td>the intent of the perpetrator of the crime.</td>
    <td>Suicide, Accidental, NA, Homicide, or Undetermined.</td>
  </tr>
  <tr>
    <td>police</td>
    <td>whether a police officer was involved with the shooting.</td>
    <td>0 (false) or 1 (true)</td>
  </tr>
  <tr>
    <td>sex</td>
    <td>the gender of the victim.</td>
    <td>M or F</td>
  </tr>
  <tr>
    <td>age</td>
    <td>the age of the victim.</td>
    <td> - </td>
  </tr>
  <tr>
    <td>race</td>
    <td>the race of the victim.</td>
    <td> Asian/Pacific Islander, Native American/Native Alaskan, Black, Hispanic, or White </td>
  </tr>
  <tr>
    <td>hispanic</td>
    <td>a code indicating the Hispanic origin of the victim.</td>
    <td> - </td>
  </tr>
  <tr>
    <td>place</td>
    <td>where the shooting occurred. Has several categories, which you're encouraged to explore on your own.</td>
    <td> home, street..,etc </td>
  </tr>
  <tr>
    <td>education</td>
    <td>educational status of the victim.</td>
    <td>     1 -- Less than High School
    2 -- Graduated from High School or equivalent
    3 -- Some College
    4 -- At least graduated from College
    5 -- Not available </td>
  </tr>
</table>


### Description of census.csv

<table>
  <tr>
    <th>Column name</th>
  </tr>
  <tr>
    <td>year</td>
  </tr>
  <tr>
    <td>Sex</td>
  </tr>
  <tr>
    <td>Hispanic Origin</td>
  </tr>
  <tr>
    <td>Geography</td>
  </tr>
  <tr>
    <td>Total</td>
  </tr>
  <tr>
    <td>Race Alone - White</td>
  </tr>
  <tr>
    <td>Race Alone - Hispanic</td>
  </tr>
  <tr>
    <td>Race Alone - Black or Afrian American</td>
  </tr>
  <tr>
    <td>Race Alone - American Indian and Alaska Native</td>
  </tr>
    <tr>
    <td>Race Alone - Asian</td>
  </tr>
  <tr>
    <td>Race Alone - Hawaiian and Other Pacific Islander</td>
  </tr>
  <tr>
    <td>Two or More Races</td>
  </tr>
  </table>

  Id	Year	Id	Sex	Id	Hispanic Origin	Id	Id2	Geography	Total	Race Alone - White	Race Alone - Hispanic	Race Alone - Black or African American	Race Alone - American Indian and Alaska Native	Race Alone - Asian	Race Alone - Native Hawaiian and Other Pacific Islander	Two or More Races