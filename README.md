# Blight-violation-predictor

Blight violations are issued by the city to individuals who allow their properties to remain in a deteriorated condition. Every year, the city of Detroit issues millions of dollars in fines to residents and every year, many of these fines remain unpaid. Enforcing unpaid blight fines is a costly and tedious process, so the city wants to know: how can we increase blight ticket compliance?

The first step in answering this question is understanding when and why a resident might fail to comply with a blight ticket. This is where predictive modeling comes in. The task is to predict whether a given blight ticket will be paid on time. Each row in these two files corresponds to a single blight ticket, and includes information about when, why, and to whom each ticket was issued. The target variable is compliance, which is True if the ticket was paid early, on time, or within one month of the hearing data, False if the ticket was paid after the hearing date or not at all, and Null if the violator was found not responsible. File descriptions (Use only this data for training your model!)

train.csv - the training set (all tickets issued 2004-2011) 

# Data fields
[train.csv](https://drive.google.com/file/d/1u0mnYEoKCAQoYrX9takG_cQ_biOE6DVe/view?usp=sharing) {Find data here}
    
    ticket_id - unique identifier for tickets
    agency_name - Agency that issued the ticket
    inspector_name - Name of inspector that issued the ticket
    violator_name - Name of the person/organization that the ticket was issued to	
	violation_street_number, violation_street_name, violation_zip_code - Address where the violation occurred
	mailing_address_str_number, mailing_address_str_name, city, state, zip_code, non_us_str_code, country - Mailing address of the violator
	ticket_issued_date - Date and time the ticket was issued
	hearing_date - Date and time the violator's hearing was scheduled
	violation_code, violation_description - Type of violation
	disposition - Judgment and judgement type
	fine_amount - Violation fine amount, excluding fees
	admin_fee - $20 fee assigned to responsible judgments
	state_fee - $10 fee assigned to responsible judgments
	late_fee - 10% fee assigned to responsible judgments
	discount_amount - discount applied, if any
	clean_up_cost - DPW clean-up or graffiti removal cost
	judgment_amount - Sum of all fines and fees
	grafitti_status - Flag for graffiti violations
	
	payment_amount - Amount paid, if any
	payment_date - Date payment was made, if it was received
	payment_status - Current payment status as of Feb 1 2017
	balance_due - Fines and fees still owed
	collection_status - Flag for payments in collections
	compliance [target variable for prediction] 
	Null = Not responsible
	0 = Responsible, non-compliant
	1 = Responsible, compliant
	compliance_detail - More information on why each ticket was marked compliant or non-compliant 
# Evaluation
The evaluation metric for this assignment is the Area Under the ROC Curve (AUC).
