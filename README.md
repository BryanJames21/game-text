# game-text
github://com.github.androidimport random
import time
chr_attack = random.randint(25, 30)
g_slime_attack = random.randint(6, 20)
shadow_assassin_attack = random.randint(15, 25)
character_health = 100
item = ""
inventory = []

name = input("Username: ")
print("You're awake adventurer Assasin [" + name +"]")

while character_health > 0:
    if character_health != 100 and item == "Fish":
        n = input("You have taken some damage to heal select |1| to Heal, |0| to Ignore\nInput: ")
        if n == "1":
            character_health += 10
            print("Your character [" + name +"] health is back to " + str(character_health))
        else:
            print("Your character [" + name +"] health is back to " + str(character_health))

    v = int(input("Enter |1| to Cross the River\nEnter |2| to Jump into the Ravine\nEnter |3| to fight the Monster in the Dungeon\nEnter [4] to Know the story of the monster\nInput: "))

    # Start of Journey
    if v == 1:
        choice = input("Do you want to go Fishing? Enter |1| if YES & |0| if NO\nInput: ")
        if choice == "1":
            # Fishing minigame
            print("You have chosen Fishing! ")
            chance = random.randint(0, 9)
            if chance > 6:
                item = "Fish"
                print("You caught a Fish!")
            else:
                print("There is no fish to catch")

        elif choice == "0":
            print("You [" + name +"] have crossed the river")


    elif v == 2:
        # damages the player
        print("You [" + name +"] have jumped into the Ravine")
        print("Your Character [" + name +"] has taken 10 Damage")
        character_health = character_health - 10

    elif v == 3:
        # damages the player
        print("You [" + name +"] have entered the Dungeon")
        print("You [" + name +"] have arrived at a Konoha's' Cave")
        dungeon = input("What path will you take |L|eft, |M|iddle, |R|ight \n"
              "Input: ")
        if dungeon == "L":
            slime_hp = 50
            shadow_assassin_hp = 92
            print("You [" + name +"] have encountered a Green Slime" + " HP:" + str(slime_hp))
            time.sleep(2)
            left = input("Enter |A| to Attack, |E| to Escape \nInput: ")
            if left == "A":
                print("You [" + name +"] have chosen to attack the Green Slime")
                slime_hp = slime_hp - chr_attack
                if chr_attack >= 28:
                    print("Green Slime received " + str(chr_attack) + " [Critical] damage" + " HP:" + str(slime_hp))
                else:
                   print("Green Slime received " + str(chr_attack) + " damage" + " HP:" + str(slime_hp))

                #EnemyMobFightBack
                print("The Green Slime attacked")
                time.sleep(2)
                character_health = character_health - g_slime_attack
                print("You [" + name +"] have taken " + str(g_slime_attack) + " Damage from the Green Slime")
                print("Your character's Health: " + str(character_health))

            if left == "E":
                print("You've chosen to escape\nThe Green Slime chase you down")

            left = input("Enter |A| to Attack, |E| to Escape\nInput: ")
            if left == "A":
                    print("You [" + name +"] have chosen to attack the Green Slime")
                    slime_hp = slime_hp - chr_attack
                    if chr_attack >= 28:
                        print("Green Slime received " + str(chr_attack) + " [Critical] damage" + " HP:" + str(slime_hp))
                    else:
                        print("Green Slime received " + str(chr_attack) + " damage" + " HP:" + str(slime_hp))
                    time.sleep(2)
                    print("You [" + name +"] have defeated the Green Slime")
                    print("The Green Slime dropped Green Goo - used to make a lesser potion")
                    inventory.append("goo")
                    time.sleep(2)
                    print("You [" + name +"] have leveled up! \nYour Health has been restored")
                    character_health = 100

            if left == "E":
                print("You Escape Successfully")

            second_level = input("Do you want to continue to the 2nd Level [" + name +"] ? |Y|es or |N|o \nInput: ")
            if second_level == "Y":
                        print("You have arrived at the Second Level")
                        time.sleep(2)
                        print("A Shadow Assassin used sneak attack on you")
                        character_health = character_health - shadow_assassin_attack
                        print("You [" + name +"] received " + str(shadow_assassin_attack) + " Damage")
                        print("Your character's Health: " + str(character_health))
                        left_2 = input("Enter |A| to Attack, |E| to Escape \nInput: ")
                        if left_2 == "E":
                            print("You've chosen to escape\nYou Escape Successfully")
                        if left_2 == "A":
                            print("You [" + name +"] have chosen to attack the Shadow Assassin")
                            shadow_assassin_hp = shadow_assassin_hp - chr_attack
                            time.sleep(2)
                            if chr_attack >= 28:
                                print("Shadow Assassin received " + str(chr_attack) + " [Critical] damage" + " HP:" + str(shadow_assassin_hp))
                            else:
                                print("Shadow Assassin received " + str(chr_attack) + " damage" + " HP:" + str(shadow_assassin_hp))
                            time.sleep(2)
                            print("Shadow Assassin fought back")
                            character_health = character_health - shadow_assassin_attack
                            print("You [" + name +"] received " + str(shadow_assassin_attack) + " Damage")
                            print("Your character's Health: " + str(character_health))
                            left_3 = input("Enter |A| to Attack, |E| to Escape \nInput: ")
                            if left_3 == "E":
                                print("You've chosen to escape\nYou Escape Successfully")

                            if left_3 == "A":
                                print("You [" + name +"] have chosen to attack the Shadow Assassin")
                                shadow_assassin_hp = shadow_assassin_hp - chr_attack
                                time.sleep(2)
                                if chr_attack >= 28:
                                    print("Shadow Assassin received " + str(
                                        chr_attack) + " [Critical] damage" + " HP:" + str(shadow_assassin_hp))
                                else:
                                    print("Shadow Assassin received " + str(chr_attack) + " damage" + " HP:" + str(shadow_assassin_hp))
                                time.sleep(2)
                                print("Shadow Assassin fought back")
                                character_health = character_health - shadow_assassin_attack
                                print("You [" + name +"] received " + str(shadow_assassin_attack) + " Damage")
                                print("Your character's Health: " + str(character_health))
                                if left_3 == "E":
                                    print("You've chosen to escape\nYou Escape Successfully")
                                if left_3 == "A":
                                    print("You [" + name +"] have chosen to attack the Shadow Assassin")
                                    shadow_assassin_hp = shadow_assassin_hp - chr_attack
                                    time.sleep(2)
                                    if chr_attack >= 28:
                                        print("Shadow Assassin received " + str(
                                            chr_attack) + " [Critical] damage" + " HP:" + str(shadow_assassin_hp))
                                    else:
                                        print("Shadow Assassin received " + str(chr_attack) + " damage" + " HP:" + str(
                                            shadow_assassin_hp))
                                    time.sleep(2)
                                    print("Shadow Assassin fought back")
                                    character_health = character_health - shadow_assassin_attack
                                    print("You  [" + name +"] received " + str(shadow_assassin_attack) + " Damage")
                                    print("Your character's Health: " + str(character_health))
                                    if shadow_assassin_hp <= 0:
                                        inventory.append("key")
                                        print("You [" + name + "] have defeated the Shadow Assassin\nThe Shadow Assassin dropped Key - use to unlock the hidden Treasure Chest")
                                        time.sleep(2)
                                        print("You [" + name +"] have leveled up! \nYour Health has been restored")
                                        character_health = 100
                                    left_3 = input("Enter |A| to Attack, |E| to Escape \nInput: ")
                                    if left_3 == "E":
                                        print("You've chosen to escape\nYou Escape Successfully")
                                    if left_3 == "A":
                                        print("You [" + name +"] have chosen to attack the Shadow Assassin")
                                        shadow_assassin_hp = shadow_assassin_hp - chr_attack
                                        time.sleep(2)
                                        if chr_attack >= 28:
                                            print("Shadow Assassin received " + str(
                                                chr_attack) + " [Critical] damage" + " HP:" + str(shadow_assassin_hp))
                                        else:
                                            print("Shadow Assassin received " + str(
                                                chr_attack) + " damage" + " HP:" + str(shadow_assassin_hp))
                                        time.sleep(2)
                                        print("Shadow Assassin fought back")
                                        character_health = character_health - shadow_assassin_attack
                                        print("You [" + name +"] received " + str(shadow_assassin_attack) + " Damage")
                                        print("Your character's Health: " + str(character_health))
                                        if shadow_assassin_hp <= 0:
                                            print("You have defeated the Shadow Assassin\nThe Shadow Assassin dropped a Key - use to unlock the hidden Treasure Chest")
                                            inventory.append("key")
                                            time.sleep(2)
                                            print("You [" + name +"] have leveled up! \nYour Health has been restored")
                                            character_health = 100


        elif dungeon == "M":
            print("You [" + name +"] found a Treasure chest")
            in_lock = True
            middle = input("|O| to Open the chest, |D| to Destroy the chest \n"
                           "Input: ")
            if middle == "O" and ("key") not in inventory:
                print("You need to find the Key")

            elif middle == "O" and ("key") in inventory:
                print("The Treasure chest has been opened\nYou [" + name +"] have acquired the Greater Potion")
                inventory.remove("key")
                print("Greater Potion - A potion that restore your health back to full")
                m1 = input("Do you want to Drink or Donate it? Enter |GLUP| to Drink |DONO| to Donate\nInput: ")
                if m1 == "GLUP":
                    character_health = 100
                elif m1 == "DONO":
                    print("The Greater Potion has been donated to the Orphanage lmao")
                else:
                    print("Invalid Input")
            elif middle == "D":
                print("The chest have been destroyed")

        elif dungeon == "R":
            print("You [" + name +"] have fallen through the Dungeon hole")
            print("You [" + name +"] have taken 50 damage")
            character_health = character_health - 50
            time.sleep(2)
            gsauce_attack = 1000
            print("A wild Gsauce appeared\nGsauce used Holy Spank")
            character_health = character_health - gsauce_attack
            print("Your character's Health: " + str(character_health))
            if character_health <= 0:
                print("you ded lmao\nGAME OVER")

    elif v == 4:
        choice = input("Do you want to know the story?\nChoose[ 1 ]for YES and Choose[ 0 ] for NO\nInput:")
        print("Story of the monster:\n Zagred the Monster is a tall humanoid with a pair of black, bat-like wings, black horns, clawed hands, and a long, arrow-tipped tail. His pale skin is mostly covered by a black coating and black lines and wrinkles. His teeth are pointed and black, and his irises are red, Zagred can open additional mouths all over his body, including on his heart, Without a body, Zagred appears as a dark-colored cloud of gas with eyes and a mouth.Zagred is a wicked and cruel individual. He looks down on both humans and elves, seeing them as his play things and means to an end. He is shown to be extremely sadistic as he finds joy in the despair of others, such as laughing at Patolli's despaired face when Zagred reveals himself as the one who orchestrated the elves' destruction and has been manipulating Patolli the entire time.This sadistic side also exposes somewhat arrogance, such as how he mockingly reveals everything to Patolli and another time when he reveals his plans to the first Magic Emperor. In both cases, he believes they could do nothing to defeat or stop him even if he revealed his intentions and involvement (Albeit revealing everything to Patolli did accomplish Zagred's goal of making him fall into deep despair) Zagred's actions come from a deep desire for a body just so he can properly manifest himself and unleash chaos wherever he goes. This displays an extremely sadistically ambitious side as Zagred does not care what methods he has to use in order to achieve that goal.All these aspects accumulate to him lacking any morality on how little he thinks of his actions toward humans and elves alike. This is further proven true by Yami, who after sensing his Ki, can only sense nothing but malicious intent from Zagred.This proved to be his own undoing as he constantly underestimates his opponents which ultimately leads to his demise. In his final moments, Zagred expresses shock at the comprehension that he was defeated.")
    else:
        print("Invalid input")
        
