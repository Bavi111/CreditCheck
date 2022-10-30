# CreditCheck
import math

def interest():

    return float(input("Enter the interest rate of credit: ")) / (12 * 100)


def n_of_payments():
    P = float(input("Enter principal for credit: "))
    
    mp = float(input("Enter the monthly payment: "))
    
    i = interest()
    
    return math.log(mp / (mp - i * P), 1 + i)


calc_type = input("""Que quieres calcular?

type "n" for numero de months,

type "p" for credit principal:

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
            print("{years} years required to repay credit")
        else:
            print("You need {years} years and {months} months required to repay credit")
    else:
        if months == 1:
            print("At least 1 month required to repay credit")
        else:
            print("{months} months required to repay credit")
