# Hello-World

## Project Title: Tax Code Example


### Description
This project is for coding your taxes in Iowa for 2023. When running this code you can input your income, if you are filing jointly and then your partner's income if so. It will then output your state tax, federal tax, and total tax for the year. It is a very useful program for someone who knows their salary for the year. 

### Program Code
'
income = float(input("What is your annual income?"))
mfj = bool(input("If you are married and filling jointly type True, if not press ENTER:"))
if mfj == True:
    spouse_income = float(input("Please enter the income of your spouse:"))
    income = income + spouse_income
else:
    spouse_income = 0
    income = income + spouse_income 
max_tax_1_mfj = 528.00
max_tax_2_mfj = 2841.60
max_tax_3_mfj = 7971.60
max_tax_1_single = 264.00
max_tax_2_single = 1420.80
max_tax_3_single = 3985.80
if mfj == True:
    
    if income <= 12000:
        state_tax = income * .044
        
    elif (income > 12000) and (income <=60000):
        state_tax = max_tax_1_mfj + (income - 12000)*0.0482
    
    elif (income > 60000) and (income <= 150000):
        state_tax = max_tax_2_mfj + (income - 60000)*0.0570
    
    else: #i.e., income > 150000
        state_tax = max_tax_3_mfj + (income - 150000)*0.0600

else:

    if income <= 6000:
        state_tax = income * .044
        
    elif (income > 6000) and (income <=30000):
        state_tax = max_tax_1_single + (income - 6000)*0.0482
    
    elif (income > 30000) and (income <= 75000):
        state_tax = max_tax_2_single + (income - 75000)*0.0570
        
    else: # i.e. , income > 75000
        state_tax = max_tax_3_single + (income - 75000)*0.0600
        
single_file_deduct = 13850
married_file_deduct = 27700
if mfj == True:
    
    income = income - married_file_deduct
    
    if income <= 0:
        federal_tax = 0 
    
    elif income <= 22000:
        federal_tax = income * .10
        
    elif (income > 22000) and (income <= 89450):
        federal_tax = 2200 + ((income -22000) *.12)
    
    elif (income > 89450) and (income <= 190750):
        federal_tax = 10294 + ((income - 89450)*.22)
    
    elif (income > 190750) and (income <= 364200):
        federal_tax = 32580 + ((income - 190750) *.24)
    
    elif (income > 364200) and (income <= 462500):
        federal_tax = 74208 + ((income - 364200)*.32)
    
    elif (income > 462500) and (income <= 693750):
        federal_tax = 105664 + ((income - 462500) * .35)
    
    elif (income > 693750):
        federal_tax = 186601.50 + ((income - 693750) * .37)
else: 
    
    income = income - single_file_deduct
    
    if income < 0:
        federal_tax = 0 
        
    elif income <= 11000:
        federal_tax = income * .10
        
    elif (income > 11000) and (income <= 44725):
        federal_tax = 1100 + ((income -11000) *.12)
    
    elif (income > 44725) and (income <= 95375):
        federal_tax = 5147 + ((income - 44725)*.22)
    
    elif (income > 95375) and (income <= 182100):
        federal_tax = 16290 + ((income - 95375) *.24)
    
    elif (income > 182100) and (income <= 231250):
        federal_tax = 37104 + ((income - 182100)*.32)
    
    elif (income > 231250) and (income <= 578125):
        federal_tax = 52832 + ((income - 231250) * .35)
    
    elif (income > 578125):
        federal_tax = 174238.25 + ((income - 578125) * .37)
if mfj == True:
    
    print("Your tax owed for Iowa in 2023 was $",round(state_tax))
    print("Your federal tax owed for 2023 was $",round(federal_tax))
    print("Your total tax owed for 2023 was $", round(state_tax + federal_tax))
else:
    print("Your tax owed for Iowa in 2023 was $",round(state_tax))
    print("Your federal tax owed for 2023 was $",round(federal_tax))
    print("Your total tax owed for 2023 was $", round(state_tax + federal_tax))

##### Files Used
