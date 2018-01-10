# game-of-unknown
import random
from sys import exit
import time

lives = 10

def start():
    print("Welcom to the game of unkown...")
    time.sleep(2)
    print("If one dares type \'enter\' to begin..")

    reply = input("> ")

    if 'enter' in reply:
        dark_door()
    else:
        print("Please enter the correct command..")

def dark_door():
    print("Welcome to the dark room.")
    time.sleep(2)
    print("Good luck trying to find the light.")
    print("But first, you must solve this riddle.")
    time.sleep(1)
    print("""I am a strong as a rock, but a word can destroy me.
    What am I?""")

    reply = input("> ")
    while reply != 'silence':
        print("I knew you would never solve my riddle.")
        time.sleep(1)
        print("But I'll give you another go.")
        reply = input("> ")

    print("Well done.")
    time.sleep(1)
    print("You may go farther in this journey than I originally anticipated.")
    time.sleep(1)
    print("You may proceed.")
    time.sleep(1)
    print("Would you like to enter \'door 1\' or \'door 2\'?")

    reply = input("> ")

    while reply != 'door 1' and reply != 'door 2':
        print("The option you have chosen is invalid.")
        time.sleep(1)
        print("Your studpidity is going to cost you your life.")
        dead("Better luck next time.")
        reply = input("> ")

    if 'door 1' == reply:
        weapon_door()
    if 'door 2' == reply:
        demon_door()

def weapon_door():
    print("I see you've solved my riddle..")
    time.sleep(1)
    print("""Here you must choose your weapon that will help you
    defend yourself for the remainder of the journey..""")
    time.sleep(1)
    print("There is a chest with the number \'6969\' printed on it.")
    time.sleep(1)
    print("Open the chest. Remember the code. You might need it later on.")
    time.sleep(1)
    print("In the case, there are two items for you to choose from.")
    print("The \'hatchet\' or a bottle of \'holy water\'.")
    time.sleep(1)
    print("Whatever you choose will help you along the journey.")
    print("So choose wisely.")

    reply = input("> ")

    while reply != 'hatchet' and reply != 'holy water':
        print("Quickly, choose one of these two weapons.")
        reply = input("> ")

    has_holy_water = ('holy water' == reply)
    has_hatchet = ('hatchet' == reply)

    if reply == 'hatchet' or reply == 'holy water':
        print("""Now that you have your item, lets move on. There are two gates
        do you wish to go through the \'narrow\' gate, or the gate that is
        \'wide\'?""")

        reply = input("> ")

    while reply != 'narrow' and reply != 'wide':
        print("You have not chosen a vaild path.")
        print("Choose and, and choose wisely.")
        reply = input("> ")

    if reply == 'wide':
        demon_room(has_holy_water)
    if reply == 'narrow':
        tree_room(has_hatchet)

def demon_door():
    print("There is a demon in this room.")
    time.sleep(1)
    print("What would you like to do? \'fight demon\' or \'run\'?")

    reply = input("> ")

    while reply != 'fight demon' and reply != 'run':
        print("You need to make a clear decision on what you want to do.")
        print("And quick!")
        reply = input("> ")

    if reply == 'fight demon':
        print("The demon enters your body.")
        time.sleep(1)
        dead("Your soul is lost forever.")

    if reply == 'run':
        dark_door()

def code_room():
    print("There is another door on the other side of the room.")
    time.sleep(1)
    print("You walk over to the door and see a keypad.")
    time.sleep(1)
    print("You need the code to open the door.")
    time.sleep(1)
    print("Do you remeber the code from earlier?")
    time.sleep(1)
    print("Type in the code to enter the room.")
    reply = input("> ")

    while reply != '6969':
        print("Sorry. Wrong code. Try again.")

    if reply == '6969':
        print("Congradulations.")
        print("You have made it to the last part of your journey.")
        time.sleep(1)
        print("""You now have the option to either \'exit\' the game.
         Or you can try you luck in the \'maze\'""")
        time.sleep(1)
        print("Which do you choose?")

        reply = input("> ")

        while reply != 'exit' and reply != 'maze':
            print("That is not an option. Choose again.")
            reply = input("> ")

        if reply == 'maze':
            print("Good luck...")
            exit()
            
        if reply == 'exit':
            exit()

def demon_room(has_holy_water):
    if not has_holy_water:
        print("""There is a demon blocking the path. He spots you and
        starts coming for you.""")
        time.sleep(1)
        print("Your hatchet does nothing against this mighty beast.")
        time.sleep(1)
        print("The demon takes over your body.")
        print("Your soul is lost forever.")
        dead("Better luck next time.")

    print("I see you have chosen to enter the wide gate.")
    time.sleep(1)
    print("This gate will lead to destruction.")
    time.sleep(2)
    print("""There is a demon blocking the door. He spots you and
    starts coming for you. You can try and use your bottle of holy water
    to disable the demon. Type \'use holy water\'""")

    reply = input("> ")

    while reply != 'use holy water':
        print("That didn't work. Try using the holy water.")
        reply = input("> ")

    if reply == 'use holy water':
        print("You have burned the demon!.")
        time.sleep(1)
        print("You see a door that the demon was guarding.")
        time.sleep(1)
        print("""Quickly, before he realized what has happened, run to the
        door and go through it!""")
        time.sleep(1)
        print("There's a door behind the sharks dead body.")
        print("You go through the door...")
        time.sleep(1)
        print("You hear the door shut, and lock, behind you.")
        code_room()

def tree_room(has_hatchet):
    if not has_hatchet:
        print("You have chosen the narrow path.")
        time.sleep(1)
        print("This road leads to life, but few find it.")
        time.sleep(1)
        print("The path behind you has disappeared.")
        time.sleep(1)
        print("The tree of the forbidden fruit is blocking the path ahead.")
        print("Would you like to eat the fruit? \'yes\' or \'no\'?")

        reply = input("> ")

        while reply != 'yes' and reply != 'no':
            print("Its a simple yes or no question.")
            print("Answer it.")
            reply = input("> ")

        if reply == 'yes':
            print("This fruit is forbidden.")
            dead("You will now suffer a painful death.")

        if reply == 'no':
            print("""You're stuck on the path with no food, and no way to
            get past the tree.""")
            time.sleep(1)
            dead("You loose your mind and die of starvation.")

    print("You have chosen the narrow path.")
    time.sleep(1)
    print("This road leads to life, but few find it.")
    time.sleep(2)
    print("""The tree of the forbidden fruit is blocking the path ahead.
    Would you life to replenish your strength and \'eat fruit\' or would you
    like to \'use hatchet\' and chop down the tree?""")

    reply = input("> ")

    while reply != 'use hatchet' and reply != 'eat fruit':
        print("It's a simple question.")
        print("Answer it.")
        reply = input("> ")

    if reply == 'use hatchet':
        print("""Congradulations! You have successfully chopped down the tree
        of the forbidden fruit.""")
        time.sleep(1)
        print("Further down the path, there is a door.")
        print("You walk to it and, go through the door...")
        time.sleep(1)
        print("You hear the door shut and lock behind you.")
        code_room()

    if reply == 'eat fruit':
        print("This fruit is forbidden.")
        dead("You will now suffer a painful death.")

def dead(why):
    global lives

    print(why, "Restarting...")
    time.sleep(1)
    lives -= 1
    print("You have", lives, "Lives left.")
    time.sleep(2)
    start()


def exit():
    print("You've come this far just to quit? Coward.")


start()
