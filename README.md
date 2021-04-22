# Test for Analytics

Design tests for Analytics functionality on a Battery Monitoring System.

Fill the parts marked '_enter' in the **Tasks** section below.

## Analysis-functionality to be tested

This section lists the Analysis for which _tests_ must be written.

Battery Telemetrics are collected and stored on a server.
Data for a month is stored in a [csv file](https://en.wikipedia.org/wiki/Comma-separated_values).

Analysis must be done on this csv file to find the following:
- minimum
- maximum
- count of breaches (how many times did it cross the threshold in a month?)
- record trends (date & time when the reading was continuously increasing for 30 minutes)

A PDF report of the analysis must be stored every week.
Notification must be sent when a new report is available.

## Tasks

### List Dependencies

List the dependencies of the Analysis-functionality.

1. Access to the Server containing the telemetrics in a csv file
2. Having a Notification function to nofity the off - limit values via. email or console
3. Function/ method to support creation of PDF
4. Access to read csv for calculation purpose
5. Accessing date and time form the system


### Mark the System Boundary

What is included in the software unit-test? What is not? Fill this table.

| Item                      | Included?     | Reasoning / Assumption
|---------------------------|---------------|---
Battery Data-accuracy       | No            | We do not test the accuracy of data
Computation of maximum      | Yes           | This is part of the software being developed
Off-the-shelf PDF converter | Yes           | To store the analysis from the csv to the PDF
Counting the breaches       | Yes           | For checking when When battery parameters crossess the threshold
Detecting trends            | Yes           | Whenever the reading continuously increases for 30 minutes, for Date and Time
Notification utility        | Yes           | To get the information about the off limits/ high values so that appropriate actions can be taken for the battery

### List the Test Cases

Add to these tests:

1. Write minimum and maximum to the PDF from a csv containing positive and negative readings
2. Write "Invalid input" to the PDF when the csv doesn't contain expected data
3. For "no breaches" the default count of breaches should be returned '0/Null'
4. Check whether the input file is .csv or not
5. Write reading along with date and time to the PDF if the trends increase continuously if its been 30 minutes
6. If the reading is not increased write to the PDF "No Trends".
7. Write to the PDFs total count of breaches
8. Write an appropriate Message to the console and verify it
9. Write an appropriate format for sending a mail 

### Recognize Fakes and Reality

Consider the tests for each functionality below.
In those tests, identify inputs and outputs.
Enter one part that's real and another part that's faked/mocked.

| Functionality            | Input        | Output                      | Faked/mocked part
|--------------------------|--------------|-----------------------------|---
Read input from server     | csv file     | internal data-structure     | Fake the server store
Validate input             | csv data     | valid / invalid             | None - it's a pure function
Notify report availability | pdf file     | Console/ email              | Fake the notification
Report inaccessible server | csv file     | No access to the server     | Fake
Find minimum and maximum   | csv data     | Return minimum and maximum values              | None - it's a pure function
Detect trend               | csv data     | Return date and time         | None - it's a pure function
Write to PDF               | csv data     | Minimum, Maximum, count of breaches, Date, Time & record trend               | Fake
