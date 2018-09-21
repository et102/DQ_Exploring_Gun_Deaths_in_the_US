# Data Readme

This README explains how to make best use of the data from the Stanford Open Policing Project. We provide an overview of the data, and a list of best practices for working with the data. 

Our analysis code and further documentation are available at [https://github.com/5harad/openpolicing](https://github.com/5harad/openpolicing).

### Overview of the data file structure

For each state in the dataset, we provide data in three formats: 

1. The data converted to our standardized format, with a single CSV for each state. We describe the meaning of each column below. It will be easiest to start with the standardized format for most analyses. 
2. The raw data as originally received from the state. Raw data may be in a variety of formats — CSV, XLS, etc — and may contain multiple files. 
3. The raw data converted to CSV format, with no other processing. There may be multiple CSV files. 

The clean data are available for direct download from the Stanford Open Policing Project website; please contact us for access to the raw data.

### Description of standardized data

Each row in the standardized data for each state provides information for one state patrol stop. All standardized data files contain the following columns. If a column cannot be computed using the data a state has provided, it is set to NA. Some states also have additional columns (e.g., an ID for the officer making the stop), which we do not use in our analysis, but which we include here because they might be useful to other researchers. These extra columns are explained in the state notes. 

For several fields (e.g., driver_race) we include a "raw" column which records the original data values from which we infer standardized values. For example, driver_race_raw might be “White Hispanic” which we code as “Hispanic” in the standardized driver_race field. We include the raw columns because our data processing pipeline is extensive, requiring judgment calls and subjective decisions. We aim to make our data processing as transparent as possible. Other analysts may choose to process the raw data differently if their needs or judgments differ.

<table>
  <tr>
    <td>Column name</td>
    <td>Column meaning</td>
    <td>Example value</td>
  </tr>
  <tr>
    <td>id</td>
    <td>The unique ID we assign to each stop. Contains the state and year. </td>
    <td>VT-2011-00012</td>
  </tr>
  <tr>
    <td>state</td>
    <td>The two-letter code for the state in which the stop occurred.</td>
    <td>VT</td>
  </tr>
  <tr>
    <td>stop_date</td>
    <td>The date of the stop, in YYYY-MM-DD format. Some states do not provide the exact stop date: for example, they only provide the year or quarter in which the stop occurred. For these states, stop_date is set to the date at the beginning of the period: for example, January 1 if only year is provided.</td>
    <td>2011-11-27</td>
  </tr>
  <tr>
    <td>stop_time</td>
    <td>The 24-hour time of the stop, in HH:MM format.</td>
    <td>20:15</td>
  </tr>
  <tr>
    <td>location_raw</td>
    <td>The original data value from which we compute the county (or comparably granular location) in which the stop occurred. Not in a standardized format across states. </td>
    <td>Winooski
</td>
  </tr>
  <tr>
    <td>county_name</td>
    <td>The standardized name of the county in which the stop occurred.</td>
    <td>Chittenden County</td>
  </tr>
  <tr>
    <td>county_fips</td>
    <td>The standardized 5-digit FIPS code in which the stop occurred.</td>
    <td>50007</td>
  </tr>
  <tr>
    <td>district</td>
    <td>In several states (e.g., Illinois) the stop county cannot be inferred, but a comparably granular location can. This comparably granular location is stored in the district column. Most states do not have this column. </td>
    <td>ILLINOIS STATE POLICE 01</td>
  </tr>
  <tr>
    <td>fine_grained_location</td>
    <td>Any higher-resolution data about where the stop occurred: e.g., milepost or address. Not standardized across states. </td>
    <td>90400 I 89 N; EXIT 15 MM90/40</td>
  </tr>
  <tr>
    <td>police_department</td>
    <td>The police department or agency that made the stop. Not in a standard format across states.  </td>
    <td>WILLISTON VSP</td>
  </tr>
  <tr>
    <td>driver_gender</td>
    <td>The driver’s gender, as recorded by the trooper. M, F, or NA.</td>
    <td>M</td>
  </tr>
  <tr>
    <td>driver_age_raw</td>
    <td>The original data value from which we compute the driver’s age when they were stopped. May be age, birth year, or birth date. Not in a standard format across states.  </td>
    <td>1988</td>
  </tr>
  <tr>
    <td>driver_age</td>
    <td>The driver’s age when they were stopped. Set to NA if less than 15 or greater than or equal to 100. </td>
    <td>23</td>
  </tr>
  <tr>
    <td>driver_race_raw</td>
    <td>The original data value from which the driver’s standardized race is computed. Not in a standard format across states.</td>
    <td>African American</td>
  </tr>
  <tr>
    <td>driver_race</td>
    <td>The standardized driver race. Possible values are White, Black, Hispanic, Asian, Other, and NA, with NA denoting values which are unknown. Asian refers to Asian, Pacific Islander, and Indian. Native Americans/American Indians are included in the "other" category. Anyone with Hispanic ethnicity is classified as Hispanic, regardless of their recorded race.</td>
    <td>Black</td>
  </tr>
  <tr>
    <td>violation_raw</td>
    <td>The violation committed by the driver, in the language of the original data. Not in a standard format across states. Some stops have multiple violations. </td>
    <td>Speeding (10–19 MPH Over Prima Facie Limit *)</td>
  </tr>
  <tr>
    <td>violation</td>
    <td>The violation committed by the driver, standardized into categories which are consistent across states. </td>
    <td>Speeding</td>
  </tr>
  <tr>
    <td>search_conducted</td>
    <td>A TRUE/FALSE value indicating whether a search was performed. </td>
    <td>TRUE</td>
  </tr>
  <tr>
    <td>search_type_raw</td>
    <td>The justification for the search, in the language of the original data. NA if no search was performed. Not in a standard format across states. Some states have multiple justifications for a search. </td>
    <td>CONSENT SEARCH CONDUCTED
</td>
  </tr>
  <tr>
    <td>search_type</td>
    <td>The normalized justification for the search. Where possible, this is standardized into categories which are consistent across states. For example, if something is clearly a consent search, search_type is referred to as “Consent”. </td>
    <td>Consent</td>
  </tr>
  <tr>
    <td>contraband_found</td>
    <td>A TRUE/FALSE value indicating whether a search was performed and contraband was found. FALSE if no search was performed. </td>
    <td>TRUE</td>
  </tr>
  <tr>
    <td>stop_outcome</td>
    <td>The outcome of the stop. Many states have idiosyncratic outcomes — for example, “CHP 215” in California — so this column is not standardized across states. “Citation” and “Warning” are the values which occur most commonly across states. If the stop has multiple outcomes, the most severe outcome is used. For example, if a stop resulted in a citation and a warning, stop_outcome would be “Citation”. </td>
    <td>Citation</td>
  </tr>
  <tr>
    <td>is_arrested</td>
    <td>A TRUE/FALSE value indicating whether an arrest was made.</td>
    <td>TRUE</td>
  </tr>
</table>
