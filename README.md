# python-logic-puzzle-solver
Resource Survival Simulator — Turn-based Python survival/resource-management game.
food = 50
water = 50
energy = 6
day_number= 3


while True:
    storing_what_happened = []
    


    print(f"This is your day number {day_number} ")
    print(f"You currently have {food} food")
    print(f"You have {water} water")
    print(f"You have {energy} energy")

    food_reducing = 5
    energy_reducing = 5
    water_reducing = 5

    food_little_reducing = 1
    water_little_reducing = 1
    energy_little_reducing = 1

    food_for_nothing_reducing = 2
    water_for_nothing_reducing = 2
    energy_for_nothing_reducing = 2

    

    

    asking_player = input("What do you want to do now?")
    food=food
    water=water
    energy=energy
    day_number=day_number
    asking_player=asking_player

    options = ["rest","hunt","search","nothing"]
    if asking_player == options[0].lower():
        food=food
        water=water
        energy=energy
        day_number = day_number

        storing_what_happened = [food,water,energy,day_number,asking_player]


        energy+=energy_reducing
        food-=food_reducing
        water-=water_reducing

        
        food-=food_little_reducing 
        water-=water_little_reducing
        energy-=energy_little_reducing

        storing_what_happened = ["This is the day number",day_number,
        "This is the food" ,food,"This is the water",water,"This is the energy"
        ,energy, "This is your input history",asking_player]
        


    elif asking_player== options[1].lower():
        
        energy-=energy_reducing
        food+=food_reducing

        food-=food_little_reducing
        energy-=energy_little_reducing
        water-=water_little_reducing

        storing_what_happened = ["This is the day number",day_number,
        "This is the food" ,food,"This is the water",water,"This is the energy"
        ,energy, "This is your input history",asking_player]

    elif asking_player == options[2].lower():
        

        water+=water_reducing
        energy-=energy_reducing
        
        water-=water_little_reducing
        energy-=energy_little_reducing
        food-=food_little_reducing

        storing_what_happened = ["This is the day number",day_number,
        "This is the food" ,food,"This is the water",water,"This is the energy"
        ,energy, "This is your input history",asking_player]

    elif asking_player==options[3].lower():
        

        water-=water_for_nothing_reducing
        energy-=energy_for_nothing_reducing
        food-=food_for_nothing_reducing

        water-=water_little_reducing
        energy-=energy_little_reducing
        food-=food_little_reducing

        storing_what_happened = ["This is the day number",day_number,
        "This is the food" ,food,"This is the water",water,"This is the energy"
        ,energy, "This is your input history",asking_player]
         

        

    else:
        print("Sorry I didnt understand")
    
    if water<=0:

        print("You have died. Game over")
        print(f"You have survived {day_number} days\n")
        break
    elif food<=0:
        print("You have died. Game over")
        print(f"You have survived {day_number} days\n")
        break
    elif energy <=0:
        print("You have died. Game over")
        print(f"You have survived {day_number} days\n")
        break
    
    
    
    day_number+=1
    
   




for i in storing_what_happened:
    print(i)
        

total_food_used = food_reducing+food_little_reducing


if energy == 0 and day_number==0:
    print("We cant divide 0 by 0")

else:
    calculation_for_average_energy  = energy + energy / day_number
    print("This is calculation for average energy",calculation_for_average_energy)



print("This is total food used",total_food_used)
