# customer_banking

## Technology Used 

| Technology Used | Resource URL | 
| ------------- |:-------------:| 
| Python | [https://www.w3schools.com/python/python_reference.asp](https://www.w3schools.com/python/python_reference.asp) | 
| Git | [https://git-scm.com/](https://git-scm.com/) | 

## Description 
This customer banking system allows customers to calculate interest earned on savings and CD accounts. This application will enable customers to enter their savings account and cd account information, see the interest earned, and view the updated balances.

## Code Example 

First I imported the various py files to access all dependencies in the Account class all of its functions. This is necessary to pull data and complete the rest of the program. 

"""Import the Account class from the Account.py file."""
from Account import Account

# Define a function for the Savings Account
def create_savings_account(balance, interest_rate, months):
    """Creates a savings account, calculates interest earned, and updates the account balance.

    Args:
        balance (float): The initial savings account balance.
        interest_rate (float): The APR interest rate for the savings account.
        months (int): The length of months to determine the amount of interest.

    Returns:
        float: The updated savings account balance after adding the interest earned.
        And returns the interest earned.
    """
    # Create an instance of the `Account` class and pass in the balance and interest parameters.
    #  Hint: You need to add the interest as a value, i.e, 0.
    account = Account(balance, interest_rate) 

    # Calculate interest earned
    interest_earned = (balance * (interest_rate/100) * (months/12))

    # Update the savings account balance by adding the interest earned
    updated_balance = balance + interest_earned

    # Pass the updated_balance to the set balance method using the instance of the SavingsAccount class.
    account.set_balance(updated_balance)

    # Pass the interest_earned to the set interest method using the instance of the SavingsAccount class.
    account.set_interest(interest_earned)

    # Return the updated balance and interest earned.
    return updated_balance, interest_earned

Then I set the balance and interest for the Account class.


Next I defined functions for creating savings and CD accounts, which calculate interest earned and update the account balances. This allowed me to take user inputs each and calculate the updated balance, interest earned.

from Account import Account

def create_cd_account(balance, interest_rate, months):
    """Creates a CD account, calculates interest earned, and updates the account balance.

    Args:
        balance (float): The initial CD account balance.
        interest_rate (float): The APR interest rate for the CD account.
        months (int): The length of months for the CD.

    Returns:
        float: The updated CD account balance after adding the interest earned.
        And returns the interest earned.
    """
    # Create an instance of the `Account` class and pass in the balance and interest parameters.
    #  Hint: You need to add the interest as a value, i.e, 0.
    cd_account = Account(balance, interest_rate) 
    #interest = balance * (0/100 * months/12)

    # Calculate interest earned
    interest_earned = (balance * (interest_rate/100) * (months/12))
    # Update the CD account balance by adding the interest earned
    updated_balance = balance + interest_earned
    # Pass the updated_balance to the set balance method using the instance of the CDAccount class.
    cd_account.set_balance(updated_balance)
    # Pass the interest_earned to the set interest method using the instance of the CDAccount class.
    cd_account.set_interest(interest_earned)
    # Return the updated balance and interest earned.
    return updated_balance, interest_earned


Then I asked the user for information on their balance, interest and maturity that I could use to calculate the updated savings balance and updated cd balance .

    savings_balance = float(input("Enter your savings account balance:"))
    savings_interest = float(input("Enter your savings interest rate:"))
    savings_maturity = int(input("Enter your savings maturity:"))

    cd_balance = float(input("Enter your cd account balance:"))
    cd_interest = float(input("Enter your cd interest rate:"))
    cd_maturity = int(input("Enter your cd maturity:"))

Then I called the functions for creating the accounts, passing in the user-provided inputs, the interest is computed, and balances are updated.

    # Call the create_savings_account function and pass the variables from the user.
    updated_savings_balance, interest_earned = create_savings_account(savings_balance, savings_interest, savings_maturity)

    # Call the create_cd_account function and pass the variables from the user.
    updated_cd_balance, cd_interest_earned = create_cd_account(cd_balance, cd_interest, cd_maturity)
       
I printed the updated account balances and the interest earned.

    print(f"\nYour updated cd balance is: ${updated_cd_balance: ,.2f}")
    print(f"Your updated cd interest earned is: {cd_interest_earned: ,.2f}")

Lastly, the main method is used to execute the process when the program is run.

     if __name__ == "__main__":
            main()


## Challenges
This project was more challenging for me than I expected.  The class helped a great deal with the methods but visualizing what was happening was a challenge for me. The hints were very helpful with the math portion as math is not one of my strengths.  
