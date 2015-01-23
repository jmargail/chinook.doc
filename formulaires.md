#ChinooK – Forms

Fiches de consultation

Configuration

Les fiches de consultation se configurent via un fichier au format JSON.
Le même fichier de configuration permet de définir une fiche de consultation et de saisie. Un processus permet de générer également une version imprimable de la fiche.

1.	Généralités
---------------

La fiche est associée à une couche.
Le fichier de configuration doit être placé dans le dossier « forms » de la couche avec l’extension « .frm »

Syntaxe :

    {
        "name": "departement.default",
        "description": "Moteur de recherche des départements...",
        "window": {
            "title": "Fiche Région",
            "width": 500,
            "height": 400
        },
        "form": {
            "items": [{...}]
        }
    }

Paramètre :

*	name : nom de la fiche. Utilisé comme identifiant par la suite pour charger la fiche (identifiant unique)
	*	nomCouche.nom_formulaire
	*	nom_formulaire : '_' représente le séparateur de dossier, permet de retrouver le fichier '.frm' à partir du form principal de la couche.

*	description : description (non utilisé pour le moment)
*	window : paramètres de configuration de la popup qui va afficher la fiche. Titre, taille.
*	form : définition de la fiche
	*	items : liste des champs de la fiche

Si on utilise une table non associé à la couche (table attributaire)
•	datasource
•	data
•	fid

On retrouve plusieurs types de champs identifié par un « xtype » :
•	ck_textfield
•	ck_combobox
•	ck_gridpanel

Par défaut le champ de type « ck_textfield » est utilisé.


readOnly


2.	Champ texte
---------------

Plusieurs balises sont disponibles :
•	name : nom du champ de la table à afficher.

•	fieldLabel : optionnel libellé du champ. Par défaut utilise le nom ou le libelle du champ définit pour la couche.
•	autres… : cf. doc Ext.js
suffix
prefix
tpl {value}

lien auto + target

vtype
maxlength


Note : le paramètre ‘name’ peut être de la forme
-	nomChamp
-	nomTable.nomChamp
-	nomSchema.nomTable.nomChamp

3.	Champ texte area
---------------

htmleditor :
height

4.	Champ liste déroulante (combobox)
---------------

La fiche en mode édition peut utiliser des listes déroulantes. En mode consultation le champ est affiché comme un texte.

Plusieurs balises sont disponibles :
•	name : nom du champ (notation schema.table)

•	fieldLabel : libellé du champ

•	layer : nom d’une autre couche utilisée pour renseigner la liste des valeurs
•	Datasource
•	Data

•	valueField : nom du champ utilisé comme valeur (sera envoyer par le formulaire)
•	displayField : nom du champ qui s’affiche dans la liste déroulante

•	id : un identifiant (doit être unique pour toutes les fiches) convention nomcouche_nomchamp
•	children : liste des champs enfant. Le champ enfant s’initialise en fonction de la valeur du ou des champs parents.
[« « , » »]

•	anyMatch : (true | false) filtre les valeurs avec « contient » au lieu de « commence par »

•	autocomplete : (true | false) affiche une zone d’autocompletion à la place d’une liste déroulante standard.
•	minChars
•	hideTrigger

•	store inline

D’autres paramètres sont disponible cf. doc Ext.js
•	typeAhead : (true | false) complète automatiquement la saisie.
•	width
•	listWitdh…
•	resizable
•	hideLabel
•	listAlign
•	emptyText

•	editable : liste fermée (store / et autres)


5.	Champ table (gridpanel)
---------------

Affiche des données de tables liées de type relation 1-N

Plusieurs balises sont disponibles :
•	name : nom du champ
•	subform : lien vers une sous-fiche lors du clic sur une ligne du tableau
•	join : définition de la jointure qui permet d’obtenir les enregistrements
•	columns : définition des champs de la table jointe à afficher.

•	fid : normalement auto…


6.	Mise en page
---------------

Colonnes
	layout : column

Onglets
	xtype : tabpanel


7.	Inclusions
---------------

@include
