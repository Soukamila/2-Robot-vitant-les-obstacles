# 2-Robot-vitant-les-obstacles
# Devoir n°2 : Robot évitant les obstacles

## Objectif

Programmer le robot virtuel pour qu'il détecte un obstacle grâce au capteur de distance, s'arrête, change de direction, puis continue sa route automatiquement.

## Composants

- **Robot virtuel VEX VR** : le robot simulé dans le navigateur.
- **Capteur FrontDistance** : mesure en millimètres la distance entre le robot et le mur devant lui.
- **Terrain Wall Maze** : un labyrinthe avec des murs, des zones A à D et des cases numérotées de 1 à 4.
- **Programmation par blocs** : catégories Events, Control, Sensing, Operators et Motion.

## Fonctionnement

1. Le programme démarre avec `When started`.
2. Dans une boucle `forever`, le robot avance.
3. Il attend que la distance mesurée par FrontDistance soit inférieure à 100 mm.
4. Il s'arrête, puis tourne de 90 degrés vers la droite.
5. Si le passage devant lui est encore bloqué (distance inférieure à 150 mm), il tourne de 180 degrés vers la gauche.
6. Si c'est encore bloqué, il tourne de 90 degrés supplémentaires vers la gauche, ce qui le ramène en arrière.
7. La boucle recommence.

## Programme (pseudo-code des blocs)

```
When started
forever
    drive forward
    wait until [FrontDistance distance in mm] < [100]
    stop driving
    turn right for [90] degrees
    if [FrontDistance distance in mm] < [150] then
        turn left for [180] degrees
        if [FrontDistance distance in mm] < [150] then
            turn left for [90] degrees
        end if
    end if
end forever
```

## Résultats obtenus

- Le robot détecte bien les murs, s'arrête devant eux et change de direction.
- Il ne réussit pas encore à traverser le labyrinthe en entier : il fait des allers-retours dans certains couloirs sans progresser.
- Réglages utilisés : seuil d'arrêt de 100 mm, seuil de vérification de 150 mm, rotations de 90 et 180 degrés.
- Première version testée : avec seulement une rotation à droite à chaque mur, le robot montait puis redescendait en boucle dans le même couloir.

<img width="654" height="722" alt="image" src="https://github.com/user-attachments/assets/486decf1-d36b-4177-8898-abb2d598f7dd" />


