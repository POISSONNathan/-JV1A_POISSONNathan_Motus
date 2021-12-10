# -JV1A_POISSONNathan_Motusfrom colorama import init
from colorama import Fore, Back, Style
init()
import random

banqueDeMot = ["courir","joyeux","manger","cadeau","arbres","hockey","verger","saisir","marins","arbres"]
choixMot = random.randint(0,9)
motMystere = banqueDeMot[choixMot]  

tentatives = 1



    
while tentatives < 8:
    motTentative = input ("Trouve le mot caché de 6 lettre : \n")
    motModif = ""
    for i in range (len(motTentative)):
        if motTentative[i] == motMystere[i]:
            lettreRouge = Back.RED + motMystere[i] # lettre rouge au bonne endroit
            motModif += lettreRouge
        else:
            lettreBleu = Back.BLUE + motTentative[i] # lettre nleu pour les lettres pas présentes
            motModif += lettreBleu
    motTentative = motModif
        
        

    print(Back.BLACK + "Ton mot est maintenant : ",motTentative)

    if motTentative == motMystere: # cette ligne fonctionne quand la ouleur rouge n'est pas présente
        break
    tentatives += 1
    print(Back.BLACK + "Tu est rendu à ", tentatives ,"tentatives")




if motTentative == motMystere:
    print("Bien joué, tu as trouvé le mot mystère qui est :", motMystere )

if motTentative != motMystere:
    print("Dommage, tu n'as pas trouvé le mot mystère qui était :",motMystere)
