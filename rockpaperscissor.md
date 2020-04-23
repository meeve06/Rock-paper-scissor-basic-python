# Rock-paper-scissor-basic-python
This is a simple code in python using if else structure that has been used to make the very famous Rock ,Paper Scissor game.
import random

# variables to define user score and computer's score

user_score=0
comp_score=0

#function that takes the users choice as input

def user_choice():
    user_input= input("Choose ROCK, PAPER OR SCISSOR :")
    if(user_input in ["Rock","ROCK","rock","r","R"]):
        user_input="r"
    elif(user_input in ["Paper","PAPER","paper","p","P"]):
        user_input="p"
    elif(user_input in ["Scissor","SCISSOR","scissor","s","S"]):
        user_input="s"
    else:
        print(":::::::::::INVALID INPUT, PLEASE RE-ENTER YOUR CHOICE:::::::::::: " )
        user_choice()
    return user_input

#function that takes the copmuter choice as input
#this function makes use of randint function to generate random choice in a given range on integers

def comp_choice():
    comp_input=random.randint(1,3)
    if(comp_input==1):
        comp_input="r"
    if(comp_input ==2):
        comp_input="p"
    if(comp_input==3):
        comp_input="s"
    return comp_input


#code from here on contains logic to decide the winner and track the score
cont_play=""
while cont_play not in ["no", "n", "N", "NO"]:
    user_input= user_choice()
    comp_input=comp_choice()
    if(comp_input=="r"):
        if(user_input=="r"):
            print(" _____________ ITS A TIE, TRY AGAIN_____________")
        if(user_input=="p"):
            user_score +=1
            print("______________ PLAYER WON__________________")
        if(user_input=="s"):
            print("______________COMPUTER WON,BETTER LUCK NEXT TIME______________")
            comp_score +=1
    if(comp_input=="p"):
        if(user_input=="r"):
            print("______________COMPUTER WON,BETTER LUCK NEXT TIME______________")
            comp_score += 1
        if(user_input=="p"):
            print(" _____________ ITS A TIE, TRY AGAIN_____________")
        if(user_input=="s"):
            user_score += 1
            print("______________ PLAYER WON__________________")

    if(comp_input=="s"):
        if(user_input=="r"):
            user_score += 1
            print("______________ PLAYER WON__________________")
        if(user_input=="p"):
            print("______________COMPUTER WON,BETTER LUCK NEXT TIME______________")
            comp_score += 1
        if(user_input=="s"):
            print(" _____________ ITS A TIE, TRY AGAIN_____________")

    print("Do you want to play further ?   [y/n]")
    cont_play=input("Enter your choice :")
    if(cont_play in ["yes","y","Y","YES"]):
        pass
    elif(cont_play in ["no","n","N","NO"]):
        break
    else:
        print("player's score is: " + str(user_score))
        print("computers score is :" + str(comp_score))
        break
