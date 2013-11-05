 Introduction
===============

Imagine a system for time reporting in a company, which can produce data in the XML format. These data refer to what has each of the employees worked with during each week of his/her professional time.
Each employee reports time for a week by listing all projects he/she took part in and how much time has it taken.

Example fragment of the data:
```
	<Items>
		<WeekId>201330</WeekId>
		<ResourceId>XY0005</ResourceId>
		<ResourceName>Jan Kowalski</ResourceName>
		<ProjectId>136</ProjectId>
		<ProjectName>Projekt 1</ProjectName>
		<Number>33.00</Number>
	</Items>
	<Items>
		<WeekId>201330</WeekId>
		<ResourceId>XY0005</ResourceId>
		<ResourceName>Jan Kowalski</ResourceName>
		<ProjectId>504</ProjectId>
		<ProjectName>Projekt 2</ProjectName>
		<Number>7.00</Number>
	</Items>
```

which shows a file with two entries in the time reporting registry. Both of them refer to the same employee, with XY0005 as identifier, and whose name is "Jan Kowalski". 
Both of them refer to the same week of work as well (denoted as 201330). The rest means that Jan Kowalski has worked for 33 hours in project called "Projekt 1" and the rest of 7 hours in project called "Projekt 2".

Description of the fields:
- WeekId - identifier of a calendar week in the yyyyww format, sometimes there's an additional letter at the end, e.g. 201343 or 201343A
- Resourceid - unique identifier of an employee
- ResourceName - ... his/her name
- ProjectId - unique identifier of the project
- ProjectName - ... and its name
- Number - amount of hours


 Goal
======

Devise a tool in XSLT, which takes the time data in XML described above and aggregates/sums some of the information into readable reports/summaries.

The produced reports should be XHTML files (or HTML), which one can easily open in a web browser and clearly see the information.

 Interesting reports
---------------------

Report 1. For each employee separately; for all weeks together; and projects whose id doesn't start with digit 1 or 2; a summary of all projects sorted descending on total amount of hours, e.g.

```
Jan Kowalski
 project        | hours
----------------+----------
  407 Projekt 1 |       33
  436 Projekt 4 |       16
  504 Projekt x |        4

Stanislaw August
 project        | hours
----------------+----------
  436 Projekt 4 |       10.5
  407 Projekt 1 |        6
```

Report 2. For each project separately; regardless of weeks; total amount of hours spent by each emplyoee (descending), e.g.


```
136 Projekt 1
person         |    hours
---------------+-----------------
Jan Kowalski   |       195
Adam Nowak     |       185
Anna Maj       |        46

504 Projekt 2
person         |    hours
---------------+-----------------
Filip Bak      |        55
Adam Nowak     |        10.5
```

Report 3. For each week (chronologically) percent of time spent by all employess on projects whose id starts with digit 1 or 2, e.g.


```
 week           |  hours   |  percent of hours
----------------+----------+------------------
  201328        |     64   |      3.2 %
  201329        |     58   |      2.9 %
  201330        |    116   |      5.8 %
```

Report 4. For each employee, sum for all weeks, how much time is spent on projects, where he/she is the sole member (no-one else reports time).
That is, only the entries should be counted, for which there's no other entry for the same project and week number from other emplyoees.

```
  person        |   total work time       |   of which, amount of hours spent as sole member
----------------+-------------------------+---------------------------------------------------
Jan Kowalski    |            1540         |                   334
Adam Asnyk      |            1500         |                    67
Adam Malysz     |             650         |                    34
```

 Version of the solution
=========================

<table>
  <tr>
   <th> minimum </th>
    <td> A single XSLT transformation, which produces at least 2 of the suggested reports (into a single HTML file)</td>
   </th>
   </tr>
   <tr>
   <th> advanced </th>
    <td> For each report a separate XSLT transformation, which produces pre-aggregated data in an intermediate format (XML).
         And another XSLT transformation - common for each report, which converts the intermediate data into readable HTML.
    </td>
   </tr>
</table>

Additional challenge - one can spend some time on the aesthetics of the generated reports - e.g. add alternating color backgrounds in tables, bar charts (in style of [
[http://i1-mac.softpedia-static.com/screenshots/JProfiler_1.jpg?1375414801]).

 Simple data to work with 
==========================

In the same directory you can find files with the data - a short one (Polish: maly) and a longer one (Polish: duzy).

