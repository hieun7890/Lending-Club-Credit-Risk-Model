# Lending-Club-Credit-Risk-Model
Project 1- Lending Club


Business Dossier
You’ve just started your group internship at Lending Club, a real peer-to-peer lending platform where individual lenders fund loans for individual borrowers.  
Most of the loans are short term (36- or 60-month) all $40K or under (median $13K).  The loans are mostly for debt-consolidation, credit card, home improvement, car, etc.  Individuals complete a loan application and Lending Club either approves it - loaning the money to the individual at a particular interest rate, which they pay back in monthly installments for the term - or Lending Club rejects the application and no further action is taken.


The Business
Like any lending business, Lending Club’s success depends on approving good loans—those that get fully repaid—and avoiding bad loans, where borrowers default (these are called charged off loans).
For this exercise, we’ll make several simplifying assumptions about how revenue, costs, and profit/loss are calculated:
Assume Lending Club acts as a single bank making loans to individuals (ignoring peer-to-peer lending complexity).


We’ll use the average loan amount of $15,268 across all loans - this is the actual average loan amount within the dataset.


If a loan is fully repaid, after monthly payments with interest, assume the borrower returns 1.3x (130%) of the original loan amount (or $19,848 in our simplified model).  1.3x is a reasonable total repayment for a 60-month debt consolidation loan.


The cost to the business is the loan amount plus a flat $1,000 in operating expenses (for processing, servicing, etc.).


We will ignore individual interest rates or loan amounts and apply this flat model to all approved loans.
The Current State
This dataset shows that historically 50% of the approved loans were “charged off” (i.e. never repaid), and only 50% were Fully Paid. In total, these data represent $3.17 billion in losses for Lending Club.  Here is the balance sheet for the loans that are in the dataset.
Inputs / Metrics
Value
How it’s calculated / what it means
Operating Cost per loan
$1,000
Every loan funded costs this much extra
Average Loan Amount
$15,268
Average loan amount within the dataset 
Expected Revenue % on fully paid
1.30
(130%)
For every $1 of the loan this much gets paid back once it’s been fully repaid.
(TLF) Total # of loans funded:
500,000


Total # of Fully Paid:
250,000
 50% of loans funded were paid back in full
Balance Sheet
(OC) Operating Costs
-$500,000,000
(-) (500,000 loans) x ($1,000 op. cost) = $500M
(TAL) Total Amount Loaned
-$7,634,000,000
(-) (500,000 loans) x ($15,268 avg. loan amt) = $7.63B






(TC) Total costs
-$8,134,000,000
(OC) + (TLF)
(R) Revenue on Repaid Loans
$4,962,100,000
(+) (250,000 repaid loans) x ($15,268) x (1.3 exp. profit %)
(P) Profit
-$3,171,900,000
( R - TC ) - Revenue minus costs. Money in v. money out
profit per loan
-$6,344
(P / TLF ) - For every loan we fund, how much do we make?
profit margin
-63.9%
( P / R ) - For every $1 made coming in the door, how much of it was profit?
Return on Investment (ROI)
-39.0%
( R / TC ) - For every $1 we spent running the business and funding all approved loans, how much was profit?

Strategy
Lending Club is losing money right now…a lot.  It’s due to a two-pronged strategy to (1) scale up the business and generate as many customers as quickly as possible, and (2) learn how to better predict who will repay their loans. 
They ran a promotion encouraging people to apply, saying they accepted almost all applicants. They figure that the long term benefits of having repeat customers is worth the cost of funding loans basically willy-nilly.
By giving loans to almost anyone, it allows them to collect a lot of data about loan applicants that they can then use to develop machine learning models to better predict which loans are likely to be repaid based on data in the application. Lending club is betting that they can predict which loans will be repaid or charged off better than their competitors in the long run.
They ran this strategy for 500,000 loans, which is what is in the dataset provided.
Today, Lending Club believes that they have scaled up the business enough and collected enough data to pivot toward being smarter about who they lend to. In other words, they would like to fund loans that, based on the loan application for a borrower, they predict are likely to be repaid, and to stop approving loans that are likely be charged off.

Test Data: 50,000 loan applications.




Predicted
Charge Offs
Predicted
Fully Paid
Actual
Charge Offs
14,574
10,461
Actual
Fully Paid
10,841
14,124

Previous Interns – Machine Learning Attempt 1

Lending club hired a group of data science interns to take a first pass at developing a machine learning model to predict (classify) whether loan applications will be Fully Paid or Charged Off. This attempt was productive but didn’t get Lending Club out of the red.  The model had 57% accuracy on its predictions, which means it’s only slightly better than the baseline 50/50 split in the historical data.  Assuming that they’d use the model to only fund those loans they predict would be paid off, this would still result in about a $1.19B loss. That’s an improvement over the baseline $3.17B in losses, but still not profitable.
The confusion matrix for the first ML model is shown above. While it improved the accuracy of predicting which loans would be paid off, it means there are also a lot of loan applications (10,841, bottom-left in the matrix) that the model says to reject that would have been repaid. There are also a lot of loans that were funded (10,461 upper-right) that never got repaid (charged off), the model just failed to predict it.  
Your first day
On your first day, you’re handed some materials left behind by the previous interns. These materials are in Google Drive: CTC / CS218 / Projects / Project 1 - Lending Club
Dataset project1_lending_club_data.csv.gz
A dataset with 500,000 loan applications all of which were approved by Lending Club
There are about 150 columns (features) per loan applicant
For each loan application it shows the final outcome of that loan - the loan_status - which was either “fully paid” or “charged off”

Jupyter Notebook in a Google Colab project - Project 1 - Lending Club - ML Model for Loan Approval.ipynb
This is a notebook left by the previous interns who worked on this dataset to try to build a model that could better predict which loans would be charged off or fully repaid. They are handing this work off to you to continue it.
Spreadsheet with sample data, data dictionary, and business impact calculator
The previous interns created a handy Google sheet with three tabs:
Sample of the dataset: a small, 1000-row, sample of the larger dataset to more easily explore the data
Data dictionary - a listing of all the columns and descriptions of what they hold.

Your Task
Your team’s task is to pick up where the last group of interns left off:
Understand the model they built
Find ways to improve the predictions it makes
Present a business case using data and an ML model for how Lending Club should approve/reject loan applications, and how much money it would potentially save and/or make for the bank over the original baseline.
You’ll evaluate model performance, explore the impact of your changes (see below), and present your findings to the Lending Club data science team.
Resources:
Starting Google Colab Notebook
Dataset
Data dictionary
ChatGPT


Collaboration & Teamwork
This is a group project. That means:
Everyone needs to make a meaningful contribution to the project.
You divide up tasks based on strengths, interests, and capacity.
You reflect on your process, share your knowledge, and check each other’s work.
In real-world teams, this work often includes roles like analysts, project managers, technical leads, and communications leads.  You don’t need to adopt those specific roles or titles, but the work they entail does need to be covered somehow.
Think about how you can divide the project so that everyone contributes meaningfully in parallel.  In addition, don’t neglect the role and work of the “project manager” (PM) who facilitates group discussion, makes sure goals and timelines are clear, motivates the team and helps it stay focused and on track.  The PM isn’t necessarily a single person. Groups can collaboratively “PM” their work, but don’t neglect the need for this type of contribution.
Why this matters: If you’re aiming for an internship or job, this project is a chance to build a story of meaningful collaboration. A strong STAR story shows that a team achieved more together than any one person could alone—and that your contribution mattered. Employers aren’t only interested in “Can you do the work?” They also ask “Do you help others do their best work, too?“  and “Do you make the team better?”

Tips: Don’t be afraid to try lots of ideas—even if they fail. Try to get gemini to write code for you, then understand that code. That’s part of real data science. Use AI tools to help with code, ask questions, or debug.
What You’ll Submit
You will create a project webpage on your Google Site at the path: 

	[link-to-your-google-site]/projects/proj-1-machine-learning  
That includes:
A brief, written, personal STAR story (see below)
A link to your group’s final Google Colab notebook
A link to your slide presentation or report
A link to the dataset you used
Make it look good. For each of the above do not just leave a raw link. At least label, or link an image or screenshot to make it clear what you’re linking to (think: this is your portfolio for the outside world, not just the professors and TAs for grading).
STAR Story Instructions:
 Write a brief reflection on your page (not a link) using the STAR format:
Situation: What challenge or problem were you trying to solve?
Task: What task was given to the team (and/or to you)
Action: What did you do? (as a team and as an individual )
Result: What did your team achieve? What was your role in that impact?


Keep it short but specific. This is your chance to highlight your contribution and your understanding of both the project and team dynamics.
Ideally, your story will show how your team achieved something meaningful—and how you helped make that happen. But even if things didn’t go well, you can still reflect meaningfully (and usefully for a future interview). A valuable STAR story can also come from a team that struggled, as long as you identify the factors that limited its effectiveness, acknowledge your own role, and describe what you’d do differently next time.

Suggested Steps
Step 1: Investigate the Existing Work
Open the jupyter notebook from the previous interns.
Explore the dataset and get familiar with:
The features (a.k.a. “indicators” or variables)
The labels (whether loans were “fully paid” or “charged off”)
Use gemini to ask to see values, distributions or other things you’d like to explore


Understand how the previous interns’ model works:
What kind of model is it?
What features were used?
What performance did they achieve?
Step 2: Try to Improve the Model
Brainstorm ways to improve the model:
Could you try different features?
Adjust model parameters?
Use a different train/test split?
Try a different algorithm?


Use your team, ChatGPT, Gemini, and Google Colab to explore the data, understand the result and build and test models.
Try to get a test accuracy value greater than 57% (that’s what the previous interns got)
Your model doesn’t have to be perfect—but it should aim to beat the previous one.


Step 3: Estimate the Business Impact
For this project, we're focusing on improving our ability to predict whether a loan will be repaid or not, based on the application data.  The impact on the business will depend on your model.
Since we’re now approving or rejecting loan applications based on a predictive model, sometimes our predictions will be wrong.  So a certain % of loans we deny might have been repaid, and a certain % we approve will be charged off.  Generally speaking you need to consider 4 factors:
Money lost - by approving a loan that gets charged off (but the model classified as not risky)
Money earned - by approving a loan that ends up being fully paid
Money saved - by not approving a risky loan (one likely to be charged off)
Money missed out - by not approving a loan that would have been repaid (but the model incorrectly classified as risky)
Calculating the business impact involves figuring out the combination of money you save, lose, earn, or miss out on. And improving your model can mean increasing or decreasing any one or all of them appropriately.
Use the Business Impact Calculator in the provided Google Sheet - to use it, simply plug in the 4 values reported by the confusion matrix for your ML model.  The rest of the values are all calculated for you based on that.  No one formula is very complicated, there’s just a lot of them, so using this tool makes it easier.
Step 4: Prepare a Team Presentation
You’ll explain:
What you inherited and how the previous model worked
How you improved the model (or why you couldn’t)
What insights your model provides
A statement about impact to the business over the baseline data.
Ethical considerations (model card): What biases are at play in the model?  Do you introduce bias? What are the limitations or cautions you’d have about using this model?  What are potential unintended consequences?







Timeline (Suggested)
Week
Focus
1
Inherit the notebook + understand the data, Test new ideas, features, and models
2
Finalize analysis, presentation, and deliverables


NOTE: We are no longer doing model cards for this project – Prof. Franke
Model Card (Required)
You’ll include a simple Model Card with:
Intended use
Limitations
Training data
Performance
Ethical risks
Recommendations




Appendix 1 - Estimating Business impact
Below is a heavily annotated version of the Business Impact Calculator in the provided Google Sheet.  
Our simplified profit/loss calculations have 3 variables that we will hold as constants for calculations to make the math reasonable but approximate. 
Operating Cost per loan - we’ve fixed an assumption that when Lending club approves a loan it costs a flat $1000, regardless of the loan amount.


Average Loan Amount - the average dollar amount of a loan for these data. You can calculate it based on data in hand or it can be given to you by leadership. We calculated the average as $15,268.


Expected Revenue (%) on Repaid Loans - a multiplier that tells you how much profit you make, on average, for a loan. Thus, the total money earned is: Expected Revenue % * Loan amount.  In our simplified model this value is a multiplier of 1.3 (130%) which works out to $19,848
The annotated confusion matrix below is fairly dense with multiple layers of information - it takes a minute to study.


Predicted: 

Charged Off
We will reject loans in this column ⇩
Predicted:

Fully Paid
We will approve loans in this col. ⇩


Actual: Charged off
⇨
This row are loans that end up being charge-offs (risky)
Money (S)aved
A correct prediction.

We rejected a loan that wouldn’t be repaid. We kept money rather than losing it.

(+) S = #loans * avg_loan_amt
Money (L)ost
An incorrect prediction. 
We approved a loan that was never repaid. Full loan amount is lost.



(-) L = #loans * avg_loan_amt
Recall:

S / (S+L) = correctly identified % of all charge offs
Actual:
Fully Paid
⇨
This row are loans that end up being Fully Paid
Money (M)issed
An incorrect prediction.  

We rejected a loan that would have been repaid. We missed out on earnings.

(-) M = #loans * avg_loan_amt * profit_rate
Money (E)arned
A correct prediction. 

We approved a loan that was repaid. We make money on earned interest.


(+) E = #loans * avg_loan_amt * profit_rate
Recall:

E / (E+M) = correctly identified % of all Fully Paid loans


Precision of Charge-Offs:
S / (S + M) = 
% of correctly denied loans
Precision of Fully Paid
E / (E + L) =
% of correctly approved loans




Model accuracy = (S+E) / (S+L+M+E)
The % of correct predictions





In the Business Impact Calculator we’ve provided a spreadsheet where you can plug in the 4 values from the confusion matrix and everything else will be computed for you in a balance sheet that looks like the table below. The initial values supplied in the confusion matrix are the ones from the previous interns’ model. 
Inputs / Metrics
Value
How it’s calculated / what it means
Operating Cost per loan
$1,000
Every loan funded costs this much extra
Average Loan Amount
$15,268
Average loan amount within the dataset 
Expected Revenue % on fully paid
1.30
(130%)
For every $1 of the loan this much gets paid back once it’s been fully repaid.
(TLF) Total # of loans funded:
500,000


Total # of Fully Paid:
250,000
 50% of loans funded were paid back in full
Balance Sheet
(OC) Operating Costs
-$500,000,000
(-) (500,000 loans) x ($1,000 op. cost) = $500M
(TAL) Total Amount Loaned
-$7,634,000,000
(-) (500,000 loans) x ($15,268 avg. loan amt) = $7.63B






(TC) Total costs
-$8,134,000,000
(OC) + (TLF)
(R) Revenue on Repaid Loans
$4,962,100,000
(+) (250,000 repaid loans) x ($15,268) x (1.3 exp. profit %)
(P) Profit
-$3,171,900,000
( R - TC ) - Revenue minus costs. Money in v. money out
profit per loan
-$6,344
(P / TLF ) - For every loan we fund, how much do we make?
profit margin
-63.9%
( P / R ) - For every $1 of revenue, how much of it is profit?
Return on Investment (ROI)
-39.0%
( R / TC ) - For every $1 we spent running the business and funding all approved loans, how much is profit?


PLEASE NOTE: This is a greatly simplified calculation used solely to support this project in CS 218. In a real bank, profit/loss math would be more complex to calculate — but you also wouldn’t be doing that math, they’d give it to you. You’d be tuning the machine learning model. 


What might change in the real world is the definition of what counts as a “good” prediction — because the bank’s formula for profit is different. But the ML work is the same: build, tune, evaluate.



