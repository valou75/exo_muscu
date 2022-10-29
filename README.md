# exo_muscu
une application de muscu
#Programme vocale muscu
from gtts import gTTS
import os   
import pyautogui
import time

'''def quitter():
    fin = lecteur_multimédia.quit()
    return fin'''
def menu():
    choix = int(input("1 Choix exercice\n"))
    return choix
def supp():
    pyautogui.hotkey('alt', 'F4')
#metttre un systeme de joueur en fonction du nombre de personne qui font les exos avec toi 
while True:
    men = menu()
    if men == 1:    
        choix_vocal = gTTS(text="Quel exercice voulez vous chosir ? ", lang='fr')
        choix_vocal.save("choix_vocal.mp3")
        os.system("start choix_vocal.mp3")
        time.sleep(4.5)
        pyautogui.hotkey('alt', 'F4')#permet de fermer le lecteur mp3
        choix_exercice = int(input("Quel exercice voulez vous chosir ?\n 1 = Pompe; 2 = abdo"))
        if choix_exercice == 1:
            pompe_vocal = gTTS(text="Vous allez donc maintenant faire des pompes", lang='fr')
            pompe_vocal.save("pompe_vocal.mp3")
            os.system("start pompe_vocal.mp3")
            time.sleep(4.5)
            supp()
            #mettre chrono
            #for série in range(0;10):
                
        if choix_exercice == 2:
            abdo_vocal= gTTS(text="Vous allez donc maintenant travaillez vos abdo", lang='fr')
            abdo_vocal.save("abdo_vocal.mp3")
            os.system("start abdo_vocal.mp3")
            time.sleep(4.5)
            supp()
