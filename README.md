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

Write tests in the form of `<expected output or action>` from `<input>` / when `<event>`

Add to these tests:

1. Write minimum and maximum to the PDF from a csv containing positive and negative readings
1. Write "Invalid input" to the PDF when the csv doesn't contain expected data
1. _enter a test
1. _enter a test

(add more)

### Recognize Fakes and Reality

Consider the tests for each functionality below.
In those tests, identify inputs and outputs.
Enter one part that's real and another part that's faked/mocked.

| Functionality            | Input        | Output                      | Faked/mocked part
|--------------------------|--------------|-----------------------------|---
Read input from server     | csv file     | internal data-structure     | Fake the server store
Validate input             | csv data     | valid / invalid             | None - it's a pure function
Notify report availability | _enter input | _enter output               | _enter fake or mock
Report inaccessible server | _enter input | _enter output               | _enter fake or mock
Find minimum and maximum   | _enter input | _enter output               | _enter fake or mock
Detect trend               | _enter input | _enter output               | _enter fake or mock
Write to PDF               | _enter input | _enter output               | _enter fake or mock
