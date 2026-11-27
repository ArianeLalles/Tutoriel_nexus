# Création d'un VST

[Voir la vidéo YouTube](https://www.youtube.com/watch?v=Z91QfRdT5EI)

## 1. Création du sujet

Ouvrir l’acquisition Static

Dans le panneau **Resources**, onglet **Subjects**, sélectionner **Create a blank subject**. Entrer le nom du futur Template (*Pour les projets validés CPP, entrer le nom de l'étude*).

<img src="images/Etape_1_creation_VST.png" width="800">

<span style="color:red">**Attention, toujours travailler sur la même frame !!!**</span>

## 2. Création des segments

Dans le panneau **Tools**, onglet **Subject Preparation** 
<img src="images/subject_preparation.png" width="300">

Dans **Labeling Template Builder** créer les segments (pelvis, femurD, tibiaD, piedD, femurG, tibiaG, piedG).

Commencer par le pelvis

*Il est plus simple de se placer face au sujet*

1. Indiquer le nom et cliquer sur create
    <figure>
    <img src="images/labeling_template_builder.png" width="450">
    </figure>

2. Sélectionner le marqueur origine du segment

3. Sélectionner les autres marqueurs pour former :
    - L’axe principal (*plus longue distance depuis l’origine*)
    - L’axe secondaire (*direction différente que marqueur précédent*)
    - Le marqueur additionnel (*autre direction*)

4. Recliquer sur create et le segment est terminé (*Le cube correspond à l'origine du segment*)
    <figure>
    <img src="images/segment_termine.png" width="250">
    </figure>

5. Dans l’onglet <strong>Subjects</strong>, étendre le menu déroulant, les marqueurs et le segment créé apparaissent. 
    <figure>
    <img src="images/pelvis_termine.png" width="250">
    </figure>

Faire de même pour les autres segments. Il est préférable d’avoir un marqueur commun à chaque segment. 

## 3. Renommer les marqueurs

Une fois le modèle terminé, nommer les marqueurs selon le marqueur set défini. *Noms à adapter si le markerset est différent.*

<figure>
<img src="images/marker_set.png" width="800">
</figure>

Pour différencier le côté droit et gauche, changer la couleur des marqueurs (CTRL + clic gauche pour sélectionner les marqueurs). Cliquer sur **Color** et modifier la couleur. Changer le radius des marqueurs médiaux (RMFE, LMFE, RMM, LMM, RFMH1, LFMH1).

<figure>
<img src="images/change_color_marker.png" width="800">
</figure>

Si certains marqueurs ne sont présents que pendant la statique les indiquer comme « optional » ou « calibration only »
<figure>
<img src="images/optional_markers.png" width="250">
</figure>

## 4. Relier les segments

Dans **Link segments**, définir le type d’articulation (*e.g.,* ball joint) et cliquer sur **Link** pour relier les segments (**du proximal vers le distal**). 

1. Choisir le segment parent (pelvis)
    <figure>
    <img src="images/segment_parent.png" width="250">
    </figure>

2. Choisir le segment enfant. Pelvis → femurD → tibiaD → piedD. *Faire la même chose pour le côté gauche*
    <figure>
    <img src="images/segment_enfant.png" width="250">
    </figure>

3. Une fois l’opération terminée, les articulations apparaissent
    <figure>
    <img src="images/linked_segments.png" width="250">
    </figure>

Le modèle est fini, à cette étape le nom du modèle doit apparaitre en **noir**. S’il est <span style="color:red">**rouge**</span>, une étape est manquante ou erreur est apparue. Il est préférable de recommencer de zéro.

## 5. Finalisation du VST

Onglet **Tools** > **pipeline** > **Current pipeline**, sélectionner **Calibrate Labeling skeleton static** 
<figure>
<img src="images/calibrate_pipeline.png" width="400">
</figure>

Dans le menu déroulant **available operation** > **subject calibration**, double cliquer sur **Set autolabel pose** et update **skeleton parameters**. Tout apparait dans le Current pipeline, et cliquer sur play.
<figure>
<img src="images/updated_calibrate_pipeline.png" width="400">
</figure>

*Si une calibration fonctionnelle est réalisée, faire la même chose en sélectionnant **create labelling skeleton ROM** à la place, et ajouter set autolabel pose et update skeleton parameters.*

Sauvegarder le sujet comme template : clic droit sur le sujet et **Save labelling skeleton as template**.