**CDCRC** recently conducted a session on the **Microsoft Teams platform**. 
The attendance output file generated from the platform contains multiple instances of the same user. 
For example, a user can join the session at 10 AM, leave the meeting at 10:15 AM, again join at 10:25 AM and leave at 10:30. In this case, the user was present for a total of 20 minutes.

Given the [**raw_attendance.csv**](https://drive.google.com/file/d/1ypJ_zTSQuLDj_oE7LtG6YUD-57uqPot1/view?usp=sharing) file which contains some finite rows, and your task is to find the overall time a person attended the meeting.


### Input

**Input File:** [Link](https://drive.google.com/file/d/1ypJ_zTSQuLDj_oE7LtG6YUD-57uqPot1/view?usp=sharing)
<br/>

1. Each row contains the following three attributes: `[Full Name, User Action, Timestamp]`.
2. Timestamp is of format: `MM/DD/YYYY, HH:MM:SS (AM|PM)`
3. User Action takes three values: `[Joined, Joined before, Left]`


### Output

**Output Spreadsheet:** [Link](https://docs.google.com/spreadsheets/d/1WrIwEadlO_c0dBBTM56aBWZzAzwHFz0pno-njNIDAg8/edit?usp=sharing)

Your output should contain multiple rows where each row must contain the following attributes:
1. Name
2. Extracted Entry Number
3. Timestamp 
    - Format: **(Joining Timestamp, Leaving Timestamp, Diff)**
4. Total Time 
    - Format: **HH:MM:SS**
5. Status 
    - Values: **Present/Absent**
    - if Total Watch Time >= 40 Minutes: **Present** 
    - if Total Watch Time <  40 Minutes: **Absent**


### Here are some of the key points:
1. As mentioned above a user can join the meeting multiple times after leaving. In such cases, you need to merge the timings.
For example, `DeKThdfHPS_3698HFP8237` joined the meeting multiple times after leaving. 
2. Entry Number is of format 4 Digits followed by 3 Chars and then 4 Digits. In case no entry number found then leave the `Extracted Entry Number` field blank in the output file.
3. All timestamp should be of the format specified above, and multiple instances should be separated by `\n`.

### Reference:
* For **Python** users:
    1. Consider using **pandas**, it will be effortless.
    2. Use python datetime module for handling of time.
    3. Use Regex for entry number extraction.
* For **JavaScript** users:
    1. Consider not using any parser, and load the data using simple string `split` method.
    
For any queries, consider mailing us at `softcom@iitrpr.ac.in` or write down your queries in the comments.
