class CoffeeMachine:
    water = 400
    milk = 540
    beans = 120
    cups = 9
    money = 550

    def __init__(self, user):
        self.user = user

    def coffeemachine(self):
            while True:
                self.user = (input("Write action (buy, fill, take, remaining, exit): "))
                if self.user == "buy":
                            self.user = input("What do you want to buy? 1 - espresso, 2 - latte, 3 - cappuccino, back - to main menu: ")
                            if self.user == "1":
                                if CoffeeMachine.water >= 250 and CoffeeMachine.beans >= 16:
                                    print("I have enough resources, making you a coffee!")
                                    CoffeeMachine.water -= 250
                                    CoffeeMachine.beans -= 16
                                    CoffeeMachine.money += 4
                                    CoffeeMachine.cups -= 1
                                elif CoffeeMachine.water < 250:
                                    print("Sorry, not enough water")
                                elif CoffeeMachine.beans < 16:
                                    print("Sorry, not enough beans")
                            elif self.user == "2":
                                if CoffeeMachine.water >= 350 and CoffeeMachine.milk >= 75 and CoffeeMachine.beans >= 20:
                                    print("I have enough resources, making you a coffee!")
                                    CoffeeMachine.water -= 350
                                    CoffeeMachine.milk -= 75
                                    CoffeeMachine.beans -= 20
                                    CoffeeMachine.money += 7
                                    CoffeeMachine.cups -= 1
                                elif CoffeeMachine.water < 350:
                                    print("Sorry, not enough water")
                                elif CoffeeMachine.milk < 75:
                                    print("Sorry, not enough milk")
                                elif CoffeeMachine.beans < 20:
                                    print("Sorry, not enough beans")
                            elif self.user == "3":
                                if CoffeeMachine.water >= 200 and CoffeeMachine.beans >= 12 and CoffeeMachine.milk >= 100:
                                        print("I have enough resources, making you a coffee!")
                                        CoffeeMachine.water -= 200
                                        CoffeeMachine.milk -= 100
                                        CoffeeMachine.beans -= 12
                                        CoffeeMachine.money += 6
                                        CoffeeMachine.cups -= 1
                                elif CoffeeMachine.water < 200:
                                        print("Sorry, not enough water")
                                elif CoffeeMachine.milk < 100:
                                        print("Sorry, not enough milk")
                                elif CoffeeMachine.beans < 12:
                                        print("Sorry, not enough beans")
                            elif self.user == "back":
                                    continue
                elif self.user == "fill":
                    fill_water = int(input("Write how many ml of water do you want to add: "))
                    fill_milk = int(input("Write how many ml of milk do you want to add: "))
                    fill_beans = int(input("Write how many grams of coffee beans do you want to add: "))
                    fill_cups = int(input("Write how many disposable cups of coffee do you want to add: "))
                    CoffeeMachine.water += fill_water
                    CoffeeMachine.milk += fill_milk
                    CoffeeMachine.beans += fill_beans
                    CoffeeMachine.cups += fill_cups
                elif self.user == "take":
                    print("I gave you $", CoffeeMachine.money)
                    CoffeeMachine.money = 0
                elif self.user == "remaining":
                    print(f"""The coffee machine has:
                    {CoffeeMachine.water} of water
                    {CoffeeMachine.milk} of milk
                    {CoffeeMachine.beans} of coffee beans
                    {CoffeeMachine.cups} of disposable cups
                    {CoffeeMachine.money} of money""")
                elif self.user == "exit":
                    break


user = CoffeeMachine("")
print(user.coffeemachine())
