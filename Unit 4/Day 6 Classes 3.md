### Now that you have some experience making basic classes, we will spend some time exploring uses of these new Objects. 
### Since we have a short period today, I want you to just try one thing. Use my code below as a starting point. You should either make a bank account like mine (But more involved), or make a to do list using classes. Try and think about where a class would be most helpful in this endeavor!

### Here is a sample code of a basic bank account. (Notice that all you can do at the moment is deposit money!)
```
class BankAccount:
    def __init__(self, balance):
        self.balance = balance

    def deposit(self, amount):
        self.balance += amount

    def withdraw(self, amount):
        if amount <= self.balance:
            self.balance -= amount
        else:
            print("Insufficient funds.")

    def check_balance(self):
        return self.balance

my_account = BankAccount(1000)


action = input("What would you like to do? Type deposit, withdraw, or check balance")
if action == "deposit":
    amount = int(input("How much would you like to deposit?"))
    my_account.deposit(amount)
    print(f"I have put {amount} into your account. You now have What would you like to do next? \n type deposit, withdraw, check balance, or leave")
my_account.deposit(500)
my_account.withdraw(200)
print(my_account.check_balance())
```
