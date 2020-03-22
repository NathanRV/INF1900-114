# Polytechnique Montréal

Département de génie informatique et génie logiciel

INF1900: Projet initial de système embarqué

# Grille de correction des programmes:

Identification:
+ Travail    : Capteurs et conversion analogique/numérique
+ Section #  : 3
+ Équipe #   : 114
+ Correcteur : Yoan Gauthier

# LISIBILITÉ
## En-têtes en début de programme   

| Pénalité par erreur                       | -1.5          |
| ----------------------------------------- | ------------- |
| Noms des auteurs                          |               |
| Description du programme                  |               |
| Identifications matérielles (Broches I/O) |               |
| Table des états ou autres s'il y a lieu   |               |
| __Résultat partiel__                      | __(1.5/1.5)__ |

## Identificateurs significatifs (Autodocumentation)

| Points importants                               | Poids         |
| ----------------------------------------------- | ------------- |
| Absence de *chiffres magiques*                  | (0.0/0.5)     |
| Noms de variables décrivent l'intention         | (0.5/0.5)     |
| Noms de fonctions décrivent l'intention (en/fr) | (0.0/0.5)     |
| __Résultat partiel__                            | __(0.5/1.5)__ |

## Commentaires pertinents

Bonnes raisons d'un commentaire
 + Explication d'un algorithme ou procédure 
 + peu évidente (ou *hack*)
 + Référence d'extraits de code copiés d'internet
 + Détail du POURQUOI d'un extrait de code

| Pénalité par erreur  | -0.5          |
| -------------------- | ------------- |
| __Résultat partiel__ | __(1.0/1.0)__ |


## Indentation   

| Pénalité par erreur                    | -0.5          |
| -------------------------------------- | ------------- |
| Indentation structurée                 |               |
| Indentation uniforme dans le programme | -0.5          |
| __Résultat partiel__                   | __(0.5/1.0)__ |


# MODULARITÉ ET COMPRÉHENSION
## Fonctions bien définies

| Pénalité par erreur                  | -0.5          |
| ------------------------------------ | ------------- |
| Responsabilité unique d'une fonction |               |
| Maximum de 4 paramètres              |               |
| Absence de code dupliqué             |               |
| __Résultat partiel__                 | __(1.0/1.0)__ |


## Bonne application des concepts de systèmes embarqués

| Pénalité par erreur                          | -1.0          |
| -------------------------------------------- | ------------- |
| Utilisation des registres appropriée         | -1.0          |
| Machine à états codée clairement             |               |
| Délais et minuteries utilisés judicieusement |               |
| PWM bien établi                              |               |
| Scrutation et interruptions bien utilisés    | -1.0          |
| etc                                          |               |
| __Résultat partiel__                         | __(2.0/4.0)__ |

# FONCTIONNALITÉS
## Git

| Points importants            | Poids         |
| ---------------------------- | ------------- |
| Fichiers aux bons endroits   | (1.5/1.5)     |
| Absence de fichiers inutiles | (1.5/1.5)     |
| __Résultat partiel__         | __(3.0/3.0)__ |


## Compilation    

| Pénalité par erreur                          | -2.0          |
| -------------------------------------------- | ------------- |
| Absence de messages d'erreurs de compilation |               |
| Absence de messages d'attention (*warning*)  |               |
| __Résultat partiel__                         | __(2.0/2.0)__ |
   

## Évaluation boîte noire  

| Points importants            | Poids         |
| ---------------------------- | ------------- |
| Cas normal de fonctionnement | (2.0/2.5)     |
| Cas limites observables      | (2.5/2.5)     |
| __Résultat partiel__         | __(4.5/5.0)__ |

# Résultat

__Total des points: 16/20__

# Commentaires du correcteur:

+ Chiffres magiques
+ Mélange entre l'anglais et le français, choisir une langue et y rester
+ Ce n'est pas la meilleure pratique que de faire une lecture des pin à l'intérieur du ISR.
+ `tmp = reader.lecture(PINA);` PINA c'est un registre complet. Ici on veut la position (PA1, PA2, ...)
+ `delayMs(uint16_t(50)); //delay 50 ms=0,05s` Le cast est inutile. Le type sera déduit lors de la compilation. Mais faites-vous une variable ou une constante.
+ Indentation entre les symboles

# Basé sur le commit suivant
```
commit 4312410869aa6cc19f04e353e1d9df12546ab98a
Author: Nathan Ramsay-Vejlens <nathan.ramsay-vejlens@polymtl.ca>
Date:   Thu Feb 27 13:16:50 2020 -0500

    finalisation fonction delayMs p1.cpp et ajout de commentaires
```

# Fichiers indésirables
```

```

# Sortie de make dans les sous-répertoires
```
======================= Sortie de make dans tp/tp6/pb1 =============================
make: Entering directory '/home/yoangau/Documents/h20/inf1900-grader/correction_tp6/114/tp/tp6/pb1'
avr-gcc -I. -MMD  -g -mmcu=atmega324pa -Os -fpack-struct -fshort-enums -funsigned-bitfields -funsigned-char -Wall                                         -fno-exceptions      -c p1.cpp
avr-gcc -Wl,-Map,pb1.out.map -mmcu=atmega324pa -o pb1.out  p1.o \
-lm 
make: Leaving directory '/home/yoangau/Documents/h20/inf1900-grader/correction_tp6/114/tp/tp6/pb1'

======================= Sortie de make dans tp/tp6/pb2 =============================
make: Entering directory '/home/yoangau/Documents/h20/inf1900-grader/correction_tp6/114/tp/tp6/pb2'
avr-gcc -I. -MMD  -g -mmcu=atmega324pa -Os -fpack-struct -fshort-enums -funsigned-bitfields -funsigned-char -Wall                                         -fno-exceptions      -c p2.cpp
avr-gcc -I. -MMD  -g -mmcu=atmega324pa -Os -fpack-struct -fshort-enums -funsigned-bitfields -funsigned-char -Wall                                         -fno-exceptions      -c can.cpp
avr-gcc -Wl,-Map,pb2.out.map -mmcu=atmega324pa -o pb2.out  p2.o can.o \
-lm 
make: Leaving directory '/home/yoangau/Documents/h20/inf1900-grader/correction_tp6/114/tp/tp6/pb2'


```