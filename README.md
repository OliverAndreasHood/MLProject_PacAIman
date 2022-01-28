# MLProject_PacAIman
## Uczestnicy projektu
- Piotr Szulc (https://github.com/OliverAndreasHood)  
- Rafał Miłodrowski (https://github.com/milodrowski)  
- Krystian Komenda (https://github.com/komendien)  

## Opis
Celem projektu jest przygotowanie własnego środowiska do uczenia maszynowego opartego o grę PacMan. Chcemy wykorzystać uczenie maszynowe ze wzmocnieniem (RL) do uzyskania modelu agenta adaptującego się do zmieniających się warunków w grze.  
Trenowanie zaplanowano na 4 etapy:  
- Uczenie bez obecności przeciwników ani wzmocnień  
- Uczenie w obecności przeciwników ale bez wzmocnień  
- Uczenie w obecności przeciwników ze wzmocnieniami  
- Optymalizacja punktów uzyskiwanych przez model pod kątem jakości i szybkości.  

Sposób poruszania się przeciwników ma być podobny do tych z oryginalnej gry MsPacman na konsole Atari.  

## Końcowy efekt i podział pracy  
Podjęto inny sposób osiągnięcia podobnego efektu. Przygotowanie własnego środowiska okazało zbyt pracochłonne, a samym uczestnikom projektu najnaturalniej w świecie brakowało na to czasu. Na pewno próba przygotowania takiego środowiska będzie kontynuowana w przyszłości.  

Wykorzystano więc gotowy ROM gry MsPacman udostępniony przez pakiet 'gym'.  
Z użyciem biblioteki tensorflow i keras przygotowano agenta opartego o sieć DQN oraz model sieci w postaci:  
- Convolution2D(32, (8, 8), strides = (4,4), activation='relu', input_shape = (3,height,width,channels)),  
- Convolution2D(64, (4, 4), strides = (2,2), activation='relu'),  
- Convolution2D(64, (3, 3), activation='relu'),  
- Flatten(),  
- Dense(512, activation='relu'),  
- Dense(256, activation='relu'),  
- Dense(actions, activation='linear')  

Optymalizacja hiperparametrów uczenia pozwoliła na wytrenowanie ponad 100'000 kroków w łącznej ilości 137 pełnych epizodów gry.  
Wyniki trenowanego agenta w porówaniu do przypadkowych ruchów uzyskała wynik ponad dwukrotnie lepszy.( 250 : 590 )  

### Parametry środowiska programistycznego  
 -----  
gym                 0.21.0  
keras               2.6.0  
numpy               1.21.2  
rl                  NA  
session_info        1.0.0  
tensorflow          2.6.0  
 -----  
Click to view modules imported as dependencies  
 -----  
IPython             7.29.0  
jupyter_client      7.1.0  
jupyter_core        4.9.1  
jupyterlab          3.2.1  
notebook            6.4.6  
 -----  
Python 3.9.7 (default, Sep 16 2021, 16:59:28) [MSC v.1916 64 bit (AMD64)]  
Windows-10-10.0.19044-SP0  
 -----  
Session information updated at 2022-01-26 22:11  

### Finalny udział w projekcie
0. Wstępny Research, know - how: Krystian  
1. Przygotowanie własnego środowiska gry PacMan - nieudane: Piotr  
2. Modele sieci, polityki uczenia: Piotr  
3. Przygotowanie środowiska: Rafał  
3. Model sposobu nauczania: Piotr  
4. Budowa sieci neuronowej: Piotr  
6. Dobór parametrów uczenia: Rafał  
7. Optymalizacja kodu i środowiska do działania na GPU: Rafał  
8. Symulacja modeli: Rafał  
9. Przygotowanie wizualizacj: Krystian  
10. Przygotwanie raportu z pracy: Krystian  