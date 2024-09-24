def check_loan_eligibility():
    try:
        # Input customer details
        salary = float(input("Enter your monthly salary: "))
        loan_amount = float(input("Enter the loan amount you are requesting: "))

        # Conditions for loan eligibility
        if salary >= 30000:
            max_loan_amount = 10 * salary
            if loan_amount <= max_loan_amount:
                print("You are eligible for the loan!")
                
                # Asking the customer how many months they plan to repay
                months = int(input("In how many months do you plan to repay the loan? "))
                
                # Adding 10% interest
                total_loan_with_interest = loan_amount * 1.10
                monthly_payment = total_loan_with_interest / months
                
                # Displaying loan details
                print(f"Loan approved! Total loan with interest: {total_loan_with_interest:.2f}")
                print(f"Your monthly payment over {months} months will be: {monthly_payment:.2f}")
            
            else:
                print(f"Loan denied! The amount you requested exceeds your limit of {max_loan_amount:.2f}.")
        
        else:
            print("Loan denied! Your salary is too low to qualify for the loan.")
    
    except ValueError:
        print("Invalid input. Please enter numerical values for salary and loan amount.")

# Call the function to run the program
check_loan_eligibility()
