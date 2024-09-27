# customer_banking

## Technology Used 

| Technology Used | Resource URL | 
| ------------- |:-------------:| 
| Python | [https://www.w3schools.com/python/python_reference.asp](https://www.w3schools.com/python/python_reference.asp) | 
| Git | [https://git-scm.com/](https://git-scm.com/) | 

## Description 
This customer banking system allows customers to calculate interest earned on savings and CD accounts. This application will enable customers to enter their savings account and cd account information, see the interest earned, and view the updated balances.

## Code Example 

<---- First I imported the various py files to access all dependencies in the Account class all of its functions. This is necessary to pull data and complete the rest of the program. ----->

      from Account import Account
      from cd_account import create_cd_account
      from savings_account import create_savings_account

<---- In this part of the code I set the balance and interest for the Account class. ----->

     class Account:
         def __init__(self, balance, interest):
              self.balance = balance
              self.interest = interest

         def set_balance(self, balance):
             self.balance = balance

         def set_interest(self, interest):
             self.interest = interest

<---- Next I defined functions for creating savings and CD accounts, which calculate interest earned and update the account balances. This allowed me to take user inputs each and calculate the updated balance, interest earned. ----->

     def create_savings_account(balance, interest_rate, months):
         account = Account(balance, interest_rate)
         interest_earned = (balance * (interest_rate / 100) * (months / 12))
         updated_balance = balance + interest_earned
         account.set_balance(updated_balance)
         account.set_interest(interest_earned)
         return updated_balance, interest_earned

     def create_cd_account(balance, interest_rate, months):
         cd_account = Account(balance, interest_rate)
         interest_earned = (balance * (interest_rate / 100) * (months / 12))
         updated_balance = balance + interest_earned
         cd_account.set_balance(updated_balance)
         cd_account.set_interest(interest_earned)
         return updated_balance, interest_earned

<------ Here I asked the user for information on their balance, interest and maturity that I could use to calculate the updated savings balance and updated cd balance . ------>

     savings_balance = float(input("Enter the initial balance for your savings account: "))
     savings_interest = float(input("Enter the annual interest rate (APR) for your savings account (as a percentage): "))
     savings_maturity = int(input("Enter the number of months for which the interest is calculated: "))

     cd_balance = float(input("\nEnter the initial balance for your CD account: "))
     cd_interest = float(input("Enter the annual interest rate (APR) for your CD account (as a percentage): "))
     cd_maturity = int(input("Enter the number of months for which the interest is calculated: "))

<----- Then I called the functions for creating the accounts, passing in the user-provided inputs, the interest is computed, and balances are updated. ------->


     updated_savings_balance, savings_interest_earned = create_savings_account(savings_balance, savings_interest, savings_maturity)
     updated_cd_balance, cd_interest_earned = create_cd_account(cd_balance, cd_interest, cd_maturity)
        
<----- Here I printed the updated account balances and the interest earned to verify the success of the process. ------>

     print(f"\nSavings Account Interest Earned: ${savings_interest_earned:.2f}")
     print(f"Updated Savings Account Balance: ${updated_savings_balance:.2f}")

     print(f"\nCD Account Interest Earned: ${cd_interest_earned:.2f}")
     print(f"Updated CD Account Balance: ${updated_cd_balance:.2f}")

<------ Lastly, the main method is used to execute the process when the program is run. -------->

     if __name__ == "__main__":
            main()


## Challenges
This project was more challenging for me than I expected.  The class helped a great deal with the methods but visualizing what was happening was a challenge for me. The hints were very helpful with the math portion as math is not one of my strengths.  
