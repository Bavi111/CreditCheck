# CreditCheck
import math

def interest():
    return float(input("Enter the interest rate of credit: ")) / (12 * 100)


def n_of_payments():
    P = float(input("Enter principal for credit: "))
    mp = float(input("Enter the monthly payment: "))
    i = interest()
    return math.log(mp / (mp - i * P), 1 + i)


calc_type = input("""What do you want to calculate?
type "n" for the number of months,
type "a" for the annuity monthly payment,
type "p" for the credit principal:
""")

if calc_type == "n":
    months = math.ceil(n_of_payments())
    years = 0
    if months == 12:
        print("You need 1 year to repay this credit!")
    elif months > 12:
        years = months // 12
        months = months % 12
        if months == 1:
            print("You need {years} years and 1 month to repay this credit!")
        else:
            print("You need {years} years and {months} months to repay this credit!")
    else:
        if months == 1:
            print("You need 1 months to repay this credit!")
        else:
            print(f"You need {months} months to repay this credit!")
