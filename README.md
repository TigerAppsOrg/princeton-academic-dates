# Princeton Academic Calendar Feed

🚀 **You can use Codespaces to work on this project and run it.** 🚀

Outline of project:

- `script.py` should output `.json` and/or `.csv` in `data` folder
- The script should retrieve this page from the Registrar (https://registrar.princeton.edu/academic-calendar-and-deadlines/academic)
- And find a link to a `.ics` file (see `academic-calendar.ics` as an example)
- Use the `icalendar` library (https://icalendar.readthedocs.io/en/latest/) to parse the file and extract the events
- You can use `sandbook.ipynb` as a sandbook to play around with ideas; this will also work in Codespaces
- Define a format for the output of the academic calendar, formalizing date types, etc.
- Write a module to parse the event names in the `.ics` file and extract the relevant information and output it in your format
- **If the data doesn't seem useful**, then try to instead use `beautifulsoup` to parse the page and extract the data from the table, this is going to be less reliable, but if the dates in the ICS seem wrong, then this is the way to go

Using the events above, and by trying to provide for each its title, date (start and end, if it is a range or period), and then tags, like maybe "start", "end", "add-drop", "classes", "midterms", "readingWeek", "deansDate", "finals", "graduation", "commencement", "registration", etc.

Here is what the output could look like, taking Spring 2023 as an example which are the dates above:
```
{
"acadyear": 2019,
"season": "fall",
"term": "F2019",
"events": [
  {
    "title": "Undergraduate Add/Drop Begins at 6:30 am",
    "date": "2020-01-23",
    "tags": ["start", "add-drop"]
  },
  {
    "title": "Spring Term Classes Begin at 8 am",
    "date": "2020-01-30",
    "tags": ["start", "classes"]
  },
  {
    "title": "Undergraduate Deadline to Add/Drop Courses Without a Fee Ends at 5:00 pm",
    "date": "2020-02-10",
    "tags": ["end", "add-drop"]
  },
...
```
or something like that


```
