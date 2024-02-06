# CS6300 Spring2024 Assignment 5 Jia Li
### 1.	When the app is started, the user is presented with the main menu, which allows the user to (1) enter or edit current job details, (2) enter job offers, (3) adjust the comparison settings, or (4) compare job offers (disabled if no job offers were entered yet ).  
> In my UML design, the MainMenu class serves as the system's entry point. The MainMenu class offers the primary interface for user interaction with the system, allowing users to access and manipulate the system's features, such as entering or editing current job details, adjusting the comparison settings, etc.
> 
> ![image](https://github.com/jiali120/CS6300/assets/60761935/787876e8-7983-4b82-8309-0e9284d39270)

### 2.	When choosing to enter current job details, a user will: a.	Be shown a user interface to enter (if it is the first time) or edit all the details of their current job. b.	Be able to either save the job details or cancel and exit without saving, returning in both cases to the main menu.
> In the CurrentJobDetails class, I have set up the attributes as per the job requirements, such as title (String), company (String), location (String), costOfLocation (Float), etc. Additionally, in the operations section, I have included enterDetails, editDetails, saveDetails, and cancelAndExit to facilitate manipulating functionality.
> 
> ![image](https://github.com/jiali120/CS6300/assets/60761935/80cf2776-9b2e-4a85-97ff-bf8186f61eb4)

### 3.	When choosing to enter job offers, a user will: a. Be shown a user interface to enter all the details of the offer, which are the same ones listed above for the current job. b.	Be able to either save the job offer details or cancel. c.	Be able to (1) enter another offer, (2) return to the main menu, or (3) compare the offer (if they saved it) with the current job details (if present).
> For this requirement, I created a class named JobOffer that extends the CurrentJobDetails class, inheriting attributes such as title (String), company (String), location (String), and costOfLocation (Float). The JobOffer class includes methods to: enterDetails(): Allows users to input all the necessary details for a new job offer. saveDetails(): Provides the functionality to save the entered job offer details to the system. cancel(): Enables users to cancel the entry process. enterAnotherOffer(): users can choose to enter details for another job offer. returnToMainMenu(): back to main menu. compareWithCurrentJob(): If the job offer details are saved, users have the option to compare these details with their current job directly.

### 4.	When adjusting the comparison settings, the user can assign integer weights to: If no weights are assigned, all factors are considered equal.
> In the ComparisonSettings class, I set all the attributes to Integer to make it easier to calculate the weight given by the user. The ComparisonSettings class allows users to assign integer weights to various aspects of a job offer, thus adjusting the comparison process to meet personal preferences and priorities. In the operation part, I have made three Settings: voidadjustSettings(): Enables the user to modify the weights of different job offer aspects. resetWeights(): Allows the user to reset all weights.

### 5.	When choosing to compare job offers, a user will: a.	Be shown a list of job offers, displayed as Title and Company, ranked from best to worst (see below for details), and including the current job (if present), clearly indicated. b.	Select two jobs to compare and trigger the comparison. c.	Be shown a table comparing the two jobs, displaying, for each job. d.	Be offered to perform another comparison or go back to the main menu.
> In the JobComparison class, I implemented functionalities, for example, displayOffers(), showing the user a list of job offers. SelectAndCompare (int job1, int job2): Allow users to select two job offers by their identifiers (or positions in the list) and initiate the comparison between them. displayComparisonTable(): This operation implements requirement 5c by presenting a table that compares the selected job offers side by side, displaying details like title, company, location, yearly salary adjusted for cost of living, yearly bonus, stock options, home buying program fund, personal choice holidays, and monthly internet stipend. performAnotherComparison(): This method allows users to perform additional comparisons between job offers. returnToMainMenu(): back to main menu. In the meantime, I set An array or list of JobOffers to store multiple job offer details. An instance of CurrentJobDetails to store the details of the user's current job.

### 6.	When ranking jobs, a job’s score is computed as the weighted average of: AYS + AYB + (CSO/3) + HBP + (PCH * AYS / 260) + (MIS*12)
> In the JobRanking class, I made it inherit the attributes from the ComparisonSettings class and added a computedScore() method to calculate the weighted average. Let displayJobRanking() to display the ranking of the offers.

### 7.	The user interface must be intuitive and responsive.
> In the UML, the ComparisonSettings has been defined as an interface to encapsulate the customization aspects of how job offers are compared within the application.

### 8.  Additional information
> I also designed the Customer class because I realized that the user needs to operate the save function; by defining the Customer class, it implies that users can save the information under their own account. Adding the Customer class makes the entire UML design more comprehensive.
> 
> ![image](https://github.com/jiali120/CS6300/assets/60761935/373df829-21b7-42f5-bbe6-e693e8059d96)






