HW1 ER-Diagram Explanation:

1. Since the owners are taking a loan of $300000 from a local bank and repaying many installments in a period of 10 years, I have given 1:M relation between 'DENTAL_PRACTICE' and 'INSTALLMENT'. The LOAN_APPLICATION_ID will be the PK in the bank and FK in 'INSTALLMENT' entity meaning that the owners would be paying their installments to their respective LOAN ID.

2. The 'STAFF' entity is connected to 'DENTAL_PRACTICE' entity via 1:M as the practice employs different staff members. Each of the medical professionals will have their STAFF_ID and LICENSE_ID which the business will track. The STAFF_DESIGNATION will give info whether he/she is regular dentists, periodontist, endodontist etc.,

3. The 'EXPENDITURE' entity has 3 entites (MONTHLY_LEASE, STARTUP_COST, MONTHLY_OPERATING_COSTS) connected to it via 1:1 relationship as the total represents a single item and all of which are added to get the TOTAL_COST attribute. The COST_TYPE will give info about which type of cost we are referring to (startup, monthly lease, operational costs).

4. The PATIENT entity will have details like PATIENT_ID, PATIENT_NAME etc.,. An attribute 'PATIENT_STATE' will give info about the patient at anytime(contacted, scheduled, recently visited, up for next visit, dormant). Each patient will have a billing record (BILLING_RECORD entity) and a medical record (MEDICAL_RECORD entity). The PATIENT_ID is the FK in boh of these entities and they are connected via 1:1 relationship since each patient will have their unique billing and medical record.

5. The 'DENTAL_PRACTICE' entity is connected to 'PATIENT' entity via 1:M relationaship with a cardinality of (1:100) as the business hopes to service around 100 patients.

6. 'BILLING_RECORD' has two other entities (INSURANCE_INFORMATION and PAYMENT_DETAILS) giving the required details in a patient's billing record. These are connected via 1:1 relationship since they would be unique to a patient.

7. The DENTAL_PRACTICE entity is connected to PAYMENT_DETAILS entity via 1:M relationship because there will be multiple patients. The TOTAL_INCOME attribute of PAYMENT_DETAILS entity gives the total income of the day's services enabling owners to see it at the end of day.

8. The TOTAL_INCOME attribute from 'PAYMENT_DETAILS' entity and TOTAL_COST attribute from 'EXPENDITURE' will be used to calculate Profit or Loss so that oweners can view it at the end of every month.

9. There is a 'ROOM_SCHEDULE' entity having PATIENT_ID and STAFF_ID(Doctor) and ROOM_NO as attributes. 'PATIENT' entity is connected to this entity via 1:M relationship with cardinality of 1:8 since there are a maximum of 8 rooms.

10. There is a 'DOCTOR' entity connected to the 'ROOM_SCHEDULE'entity via 1:M relationship with a cardinality of 1:8 since 1 room can have a doctor and patient at any time. STAAF_ID is a foriegn key attribute taken from 'DENTAL_PRACTICE' since doctors are a part of the staff. 'DENTAL_PRACTICE' entity is connected to 'DOCTOR' entity via 1:M relationhip since it has many doctors employed.

11. There is an entity 'INSURANCE_PROVIDER' which is used by the business to bill the insurance provider.A patient's billing record will have insurance information giving details like provider name, subscriber ID and eligible amount coverage. 
Note : The 'INSURANCE_INFORMATION' of a patient is connected to 'INSURANCE_PROVIDER' entity via 1(zero or 1):M(1 or many) since a patient can have an insurance or has no insurance. And an insuarnce provider can insure 1 or many patients

12. The patient subscriber ID is taken from 'INSUARNCE_INFORMATION' entity and other details of the treatment done (in the form of TREATMENT_CODE as specified in the document in HW description), treatment date and amount billed.
