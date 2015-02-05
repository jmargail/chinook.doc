## Impressions


Les modèles d’impression au format JSON permettent de définir une ou plusieurs mises en page d’impression.

Par défaut la mise en page peut s’adapter au format portrait/paysage ainsi qu’à la taille A4/A3.

On peut définir pour un modèle une mise en page ‘Portrait’ et ‘Paysage’ différente (avec le suffixe « -p » et « -l ».


Dans le fichier JSON on précise des paramètres généraux : 

    "title" : "Mise en page par defaut",
    "name" : "default",
    "units": "px",
    "margins": {
        "top":20,
        "bottom":20,
        "right":20,
        "left":20
    }

ATTENTION : le paramètre « name » doit être égal au nom du fichier json. Il doit être unique. Ce nom permet d’identifier le modèle à appliquer lors de l’impression.

Mais surtout une liste de blocs de différent type à placer dans la page. La version actuelle traite 8 types de bloc :

