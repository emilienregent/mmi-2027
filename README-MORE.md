# MMI 2027 - Pour aller plus loin

# Animations

## Quelques définitions

### Modèle 3D
Un modèle maillé 3D est un modèle numérique de surface qui représente numériquement un objet en 3D. Le modèle se compose de sommets(vertices), d'arêtes et d'éléments individuels(polygons).

Les sommets sont utilisés comme coordonnées et les arêtes du modèle relient respectivement deux sommets voisins. Les faces (polygones) englobent les arêtes et forment ainsi la surface de l'objet.

Les polygones les plus souvent utilisés sont les triangles et les quadrilatères. La composition de ces coordonnées, arêtes et polygones constitue le modèle de maillage 3D.

### Rig
Un rig est constitué d'une série d'articulations qui imitent la structure osseuse réelle et fournissent des points de pivot naturels entre les os. Le maillage du personnage est relié aux articulations par un processus appelé peinture pondérée, de sorte que les articulations et le maillage se déplacent ensemble.

> [!NOTE]
> Pour aller plus loin suivez ce [tutorial](https://learn.unity.com/tutorial/intro-to-unity-rigs#)

### Animation
Une série de transformations appliquées à chaque frame ou interpoler entre deux frames.

## Animer un objet
1. Sélectionner l'objet à animer
2. Ouvrir l'onglet "Animation"
3. Créer un nouvel animation clip (crée automatiquement un Animator et ajoute le composant sur l'objet)

## Animator
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/class-AnimatorController.html)

Un graph définissant les états possible d'un objet.
Chaque état défini une animation à jouer.
On définit des transitions pour passer d'un état à un autre.

![Image d'illustration](https://docs.unity3d.com/uploads/Main/MecanimAnimatorControllerWindow.png)

# Camera

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/6000.2/Documentation/Manual/CamerasOverview.html)

Une scène Unity représente des GameObjects dans un espace tridimensionnel. 
L'écran de l'utilisateur étant bidimensionnel, Unity doit capturer une vue et l'« aplatir » pour l'affichage. Il utilise pour cela des caméras.
La caméra Unity est un GameObject qui inclut un composant Camera.

> [!TIP]
> Chaque nouvelle scène Unity vient avec une camera pour en faire le rendu. Elle est défini comme la caméra principale (MainCamera).
> Attention si vous venez à la dupliquer ou en créer une vous-même. Il est important de n'avoir qu'une seule caméra principale.

## Projection
Active ou désactive la capacité de la caméra à simuler la perspective.

### Perspective
La caméra rendra les objets avec une perspective intacte.
Utilisez les paramètres de Field of View pour contrôler l'angle de vue de la caméra.
Mesuré en degrés selon l'axe spécifié dans FOV Axis.

![Image d'illustration](https://docs.unity3d.com/2022.3/Documentation/uploads/Main/Camera-Non-Ortho-FPS.jpg)

### Orthographic
La caméra rendra les objets de manière uniforme, sans aucun sens de la perspective.
Contrôlez la zone visible par l’utilisateur sur son écran (viewport) grâce au paramètre Size. 

![Image d'illustration](https://docs.unity3d.com/2022.3/Documentation/uploads/Main/Camera-Ortho-FPS.jpg)

> [!NOTE]
> Pour aller plus loin sur les différents modes de [projection](https://docs.unity3d.com/6000.2/Documentation/Manual/2Dor3D.html).
> Chaque mode est compatible avec des graphismes 2D ou des géométries 3D. Il est cependant important d'avoir une bonne compréhension des contraintes de chaque mode.

![Image d'illustration](https://docs.unity3d.com/uploads/Main/MecanimAnimatorControllerWindow.png)

# Cinemachine

## Installation

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/upm-ui.html)

Cinemachine est un package qui n'est pas inclus par défaut dans un nouveau projet.
Il est donc nécessaire de l'importer comme tout autre package Unity.

1. Ouvrez la fenêtre Window / Package Manager
2. Sélectionnez la catégorie Unity Registry
3. Installez le package Cinemachine

## Éléments essentiels

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.cinemachine@3.1/manual/concept-essential-elements.html)

Une configuration Cinemachine fonctionnelle implique trois principaux types d'éléments :

- Une seule caméra Unity qui capture les images de la scène
- Un Cinemachine Brain qui active la fonctionnalité Cinemachine dans la caméra Unity
- Une ou plusieurs Cinemachine Cameras qui contrôlent à tour de rôle la caméra Unity en fonction de leur statut

## La Caméra Unity

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/2022.3/Documentation/Manual/class-Camera.html)

La caméra Unity est un GameObject qui inclut un composant Camera, par opposition aux caméras Cinemachine.

### Projection
Active ou désactive la capacité de la caméra à simuler la perspective.

#### Perspective
La caméra rendra les objets avec une perspective intacte.
Utilisez les paramètres de Field of View pour contrôler l'angle de vue de la caméra.
Mesuré en degrés selon l'axe spécifié dans FOV Axis.

![Image d'illustration](https://docs.unity3d.com/2022.3/Documentation/uploads/Main/Camera-Non-Ortho-FPS.jpg)

#### Orthographic
La caméra rendra les objets de manière uniforme, sans aucun sens de la perspective.
Contrôlez la zone visible par l’utilisateur sur son écran (viewport) grâce au paramètre Size. 

![Image d'illustration](https://docs.unity3d.com/2022.3/Documentation/uploads/Main/Camera-Ortho-FPS.jpg)

## Cinemachine Brain

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/CinemachineBrainProperties.html)

Pour fonctionner avec Cinemachine, le GameObject qui porte la Camera doit inclure un composant Cinemachine Brain.

Les GameObject dotés d'un Cinemachine Brain sont affichés dans la hiérarchie avec une petite icône CinemachineCamera à côté d'eux. Vous pouvez désactiver cette option à partir du panneau Préférences Cinemachine.

Ce composant est responsable de :
- Surveiller toutes les caméras Cinemachine actives dans la scène.
- Déterminer quelle caméra Cinemachine contrôle la caméra Unity.
- Gérer la transition lorsqu'une autre caméra Cinemachine prend le contrôle de la caméra Unity.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/images/CinemachineBrain.png)

Pour ajouter un composant Cinemachine Brain à une caméra Unity, effectuez l'une des opérations suivantes :

- Utilisez le menu GameObject > Cinemachine pour ajouter une CinemachineCamera à votre scène. Unity ajoute un composant Cinemachine Brain à la caméra Unity pour vous s'il n'y en a pas déjà un.
- Ajoutez vous-même un composant Cinemachine Brain à la caméra Unity.

## Cinemachine Camera (Virtual Camera)

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/CinemachineVirtualCamera.html)

La CinemachineCamera est un composant que vous ajoutez à un GameObject vide. Il représente une Cinemachine Camera dans la scène Unity.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/images/CinemachineVCamProperties.png)

Utilisez les propriétés Aim, Body et Noise pour spécifier la manière dont la caméra virtuelle anime la position, la rotation et d'autres propriétés. La caméra virtuelle applique ces paramètres à la caméra Unity lorsque Cinemachine Brain transfère le contrôle de la caméra Unity à la caméra virtuelle prioritaire.

### Priority
Ce paramètre contrôle la manière dont la sortie de cette CinemachineCamera est utilisée par CinemachineBrain. 

À tout moment, chaque caméra virtuelle peut être dans l’un de ces états en fonction des valeurs de priorité :

- Live: La caméra virtuelle contrôle activement une caméra Unity dotée d'un cerveau Cinemachine.
- Standby: La caméra virtuelle ne contrôle pas la caméra Unity. Cependant, elle suit et vise toujours ses cibles et se met à jour à chaque image.
- Disabled: La caméra virtuelle ne contrôle pas la caméra Unity et ne suit ni ne vise activement ses cibles.

### Follow
L'objet GameObject cible avec lequel la caméra virtuelle se déplace. Les propriétés Body utilisent cette cible pour mettre à jour la position de la caméra Unity.

### Body

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/CinemachineVirtualCameraBody.html)

Utilisez les propriétés Body pour spécifier l’algorithme qui déplace la caméra virtuelle dans la scène.

Différents algorithmes sont détaillés dans la documentation pour répondre aux besoins variés de suivi du GameObject cible. Mais un des principaux reste le mode 3rd Person follow qui permet de pivoter la caméra horizontalement et verticalement autour du joueur en suivant la cible Follow.

### Aim

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/CinemachineVirtualCameraAim.html)

Utilisez les propriétés Aim pour spécifier comment faire pivoter la caméra virtuelle.

Les principaux algorithmes utilisés sont Composer et Group Composer, qui permettent respectivement de garder une ou plusieurs cibles dans le cadre de la caméra.

## Transitions

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/CinemachineBlending.html)

Utilisez les propriétés de Blend pour spécifier comment le composant Cinemachine Brain effectue un blend entre les caméras virtuelles.

Un Blend Cinemachine n'est pas un fade. Au contraire, Cinemachine Brain effectue une animation fluide de la position, de la rotation et d'autres paramètres de la caméra Unity d'une caméra virtuelle à l'autre.

Pour les fusions entre des caméras virtuelles spécifiques, utilisez la liste Custom Blends dans le composant Cinemachine Brain. Utilisez la propriété Default Blend dans Cinemachine Brain pour spécifier des fusions entre des caméras virtuelles qui n'ont pas de blending personnalisé.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.cinemachine@2.10/manual/images/CinemachineCustomBlends.png)

> [!TIP]
> Utilisez le nom réservé **ANY CAMERA** pour effectuer un blend depuis ou vers n'importe quelle caméra virtuelle.

# La lumière

Les rayons de lumière rebondissent sur les objets qui nous entourent.
Chaque rayon réagit en fonction des propriétés des matériaux rencontrés lors de chaque rebond (fréquence, direction, etc).
Une fois que ces rayons atteignent l'œil, le cerveau interprète ce qui "reste" de la lumière pour déterminer notre environnement.

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/2022.3/Documentation/Manual/LightingInUnity.html)

## Éclairage direct et indirect
On parle d'éclairage direct lorsque le rayon de lumière atteint l'œil après avoir rebondi une seule fois sur un objet.
A l'inverse un éclairage indirect correspond aux multiples rebonds d'un rayon de lumière avant qu'il n'atteigne l'œil.
C'est cette partie de l'éclairage qui est compliqué à calculer de manière réaliste.
En informatique on va donc contraindre le nombre de rebonds (généralement 3 maximum) pour réduire les calculs à réaliser.

## Temps réel et précalculé
L'éclairage en temps réel (**realtime**) est utilisé lorsque Unity calcule l'éclairage au moment de l'exécution. 
L'éclairage précalculé (**baked**) est utilisé lorsque Unity effectue des calculs d'éclairage à l'avance et enregistre les résultats sous forme de données d'éclairage, qui sont ensuite appliquées au moment de l'exécution. 
 
Dans Unity, votre projet peut utiliser un éclairage en temps réel, un éclairage précalculé ou un mélange des deux (appelé éclairage mixte).

## Éclairage global
Unity dispose de deux systèmes d'éclairage global, qui combinent l'éclairage direct et indirect.
Le système d'illumination globale en temps réel est [Enlighten Realtime Global Illumination](https://docs.unity3d.com/2022.3/Documentation/Manual/realtime-gi-using-enlighten.html).
Cela va par exemple permettre d'éclairer des objets avec une lumière vacillante.

> [!NOTE]
> Son usage est conseillé pour les plateformes suffisamment robustes pour gérer le calcul de ces changements à chaque frame.
> En général les plateformes mobiles vont éviter ce type d'éclairage et se rabattre sur un éclairage précalculé.

Le système Baked Global Illumination se compose de lightmaps, de light probs et de reflection probes qu'il est possible de précalculé avec le [Progressive Lightmapper](https://docs.unity3d.com/2022.3/Documentation/Manual/progressive-lightmapper.html).
Ce système permet de générer les données d'éclairage dans une scène et sur les objets quelle contient pendant l'édition plutôt que l'éxécution. 

> [!IMPORTANT]
> Il est important de noter que l'éclairage précalculé ne fonctionne que pour les objets statiques dans la scène.
> Par ailleurs cela nécessite des UV non superposés avec de petites erreurs de surface et d'angle.

> [!TIP]
> Il est nécessaire de cocher la propriété Generate Lightmaps UVs sur les objets importés dans Unity si ces UVs n'ont pas été créées préalablement dans l'outil de modelling 3D.
> ![image](https://github.com/user-attachments/assets/390a5d12-bf32-4811-921e-f9819b25163f)

## Éclairage ambiant
Toute nouvelle scène créée dans Unity est déjà éclairée de deux façons : 
	1. Un éclairage ambiant de base (fenêtre lighting-->settings).
	2. Une lumière directionnelle présente dans l'onglet hierarchy 
 
Même en désactivant toutes les sources de lumière dans votre environnement, ce dernier reste légèrement éclairé par la lumière ambiante qui éclaire tous les objets de façon égale. 
Pour contrôler et modifier cet éclairage ambiant, choisir le menu Window/Renderin/LightingSettings, puis l'onglet Scene.

## Éclairage par composant

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/2022.3/Documentation/Manual/Lighting.html)

Vous pouvez ajouter des lumières à votre scène à partir du menu GameObject->Light. 
Vous choisirez le format de lumière que vous souhaitez dans le sous-menu qui apparaît. 
Une fois qu'une lumière a été ajoutée, vous pouvez la manipuler comme n'importe quel autre GameObject. 
De plus, vous pouvez ajouter un composant Light à n'importe quel GameObject sélectionné en utilisant Component->Rendering->Light.

Plusieurs types de lumières son disponibles avec ce composant.
![image](https://github.com/user-attachments/assets/6e414466-8bff-49e8-a023-69bdf59cf868)

### Lumière directionnelle (Directional light)
Ce comportant de nombreuses façons comme le soleil, les lumières directionnelles peuvent être considérées comme des sources lumineuses distantes qui existent à une distance infinie. 
Une lumière directionnelle n'a pas de position source identifiable et l'objet lumineux peut donc être placé n'importe où dans la scène.

> [!TIP]
> La rotation de la lumière directionnelle par défaut entraîne la mise à jour de la **Skybox**.
> Si la Skybox est sélectionnée comme source ambiante, l'éclairage ambiant changera en fonction de ces couleurs. 
> Avec la lumière orientée vers le côté, parallèlement au sol, des effets de coucher de soleil peuvent être obtenus.
> En pointant la lumière vers le haut, le ciel devient noir, comme s'il faisait nuit.
> Avec la lumière orientée vers le bas, le ciel ressemblera à la lumière lorsque le soleil est au zénith.

### Point de lumière (point light)
Un point lumineux est situé à un point de l'espace et envoie de la lumière dans toutes les directions de manière égale. 
La direction de la lumière frappant une surface est la ligne reliant le point de contact au centre de l'objet lumineux. 
L'intensité diminue avec la distance par rapport à la lumière.

### Lumière spot (spotlight)
Tout comme un point de lumière, un spot a un emplacement et une portée spécifiques sur lesquels la lumière tombe. 
Cependant, un spot est limité à un angle, ce qui donne une zone d'éclairage en forme de cône.
Cela est généralement utilisé pour les sources de lumière artificielle telles que les lampes de poche, les phares de voiture et les projecteurs.

### Lumière de zone (area light)
Vous pouvez définir une lumière de zone par l'une des deux formes dans l'espace : un rectangle ou un disque. 
Une lumière de zone émet de la lumière depuis un côté de cette forme. 
La lumière émise se propage uniformément dans toutes les directions sur la surface de cette forme.
 
> [!IMPORTANT]
> Étant donné que ce calcul d’éclairage nécessite beaucoup de ressources processeur, les lumières de zone ne sont pas disponibles en temps-réel et ne peuvent être intégrées que dans des lightmaps précalculées.

## Éclairage provenant d'un objet (Emissive)

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/2022.3/Documentation/Manual/lighting-emissive-materials.html)

Il est possible d'ajuster les propriétés du matériel d'un objet pour qu'il émette de la lumière.
Ces objets contribuent à la lumière réfléchie dans votre scène et les propriétés associées telles que la couleur et l'intensité peuvent être modifiées pendant le jeu.
 
L'émission ne sera reçue que par les objets marqués comme « Static » ou « Lightmap Static » dans l'inspecteur.
De même, les matériaux émissifs appliqués à une géométrie non statique ou dynamique telle que des personnages ne contribueront pas à l’éclairage de la scène.

# L'Audio

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/AudioOverview.html)

Pour simuler les effets de position, Unity nécessite que les sons proviennent d'Audio Source attachées à des objets.
Les sons émis sont ensuite captés par un Audio Listener attaché à un autre objet, le plus souvent la caméra principale.

![image](https://docs.unity3d.com/uploads/Main/AudioSourceListDiagram.png)

> [!TIP]
> Unity ne peut pas calculer les échos uniquement à partir de la géométrie de la scène, mais vous pouvez les simuler en ajoutant des filtres audio aux objets.

## Les Formats
Unity peut importer des fichiers audio aux formats AIFF, WAV, MP3 et Ogg de la même manière que d'autres ressources.
Importez un fichier audio pour créer un clip audio que vous pouvez ensuite faire glisser vers une source audio ou utiliser à partir d'un script.

## Audio Source

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/class-AudioSource.html)

La source audio lit un clip audio dans la scène.
Le clip peut être lu par un Audio Listener ou via un mixeur audio.
L'audio peut être réparti entre les différents haut-parleurs de la plateforme (stéréo vers 7.1) (Spread).
Il peut être également transformé entre 3D et 2D (SpatialBlend).
L'audio peut être atténué avec la distance par l'intermédiaire de courbes de décroissance.

Il est possible de faire tourner le clip audio en boucle lorsqu'il atteint la fin en activant la propriété Loop.
Vous pouvez définir la quantité de changement de hauteur (Pitch) due au ralentissement/à l'accélération du clip audio. La valeur 1 correspond à la vitesse de lecture normale.

![image](https://docs.unity3d.com/uploads/Main/AudioSourceInspector.png)

Pour créer une nouvelle source audio :
	
- Importez vos fichiers audio dans votre projet Unity. Ce sont désormais des clips audio.
- Créez un GameObject de source audio (menu : GameObject > Audio > Audio Source).
- Avec le nouveau GameObject sélectionné, sélectionnez Composant > Audio > Audio Source.

Dans l'inspecteur, recherchez la propriété Clip audio sur le composant Audio Source et attribuez un clip, soit en le faisant glisser depuis la fenêtre de projet, soit en cliquant sur la petite icône en forme de cercle à droite de la propriété Inspecteur, puis en sélectionnant un clip dans la liste.
	
> [!TIP]
> Si vous souhaitez créer une source audio uniquement pour un clip audio que vous avez dans le dossier Assets, vous pouvez simplement faire glisser ce clip vers la vue de la scène - un GameObject avec un composant Source audio sera créé automatiquement pour celui-ci.

## Audio Listener

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/class-AudioListener.html)

Il reçoit les entrées de n'importe quelle source audio donnée dans la scène et diffuse les sons via la sortie son de la plateforme. 

En fonction de la perspective du joueur, il peut être plus judicieux de connecter l'Audio Listener à la caméra principale (expérience à la première personne par exemple). Cependant, si la caméra est détachée de la représentation du joueur, vous devez alors déterminer où l'Audio Listener s'intègre le mieux (éventuellement près de la tête du personnage principal).

L'Audio Listener n'a pas de propriétés. Il doit simplement être ajouté pour fonctionner. Il est toujours ajouté à la caméra principale par défaut.

Lorsque l'Audio Listener est attaché à un GameObject dans votre scène, toutes les sources suffisamment proches de seront captées et transmises à la sortie son de la plateforme.

> [!IMPORTANT]
> Chaque scène ne peut avoir qu'un seul Audio Listener pour fonctionner correctement.

Si les sources sont en 3D, l'Audio Listener émulera la position, la vitesse et l'orientation du son dans le monde 3D. 2D ignorera tout traitement 3D.

# Collider Interactions

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/collider-interactions.html)

Lorsque deux Colliders entrent en contact, vous pouvez appeler des fonctions pour déclencher d'autres événements dans votre projet via des scripts.

> [!CAUTION]
> Les événements Collider nécessitent une configuration via un script C# ; vous ne pouvez pas les configurer en utilisant uniquement l'interface utilisateur.

### Collision events
Ces événements se produisent lorsque deux Colliders entrent en contact et qu'aucun des collisionneurs n'a la fonction IsTrigger activée.

### Trigger events 
Ces événements se produisent lorsque deux Colliders entrent en contact, qu'au moins un Collider a l'option IsTrigger activée et qu'au moins un Collider a un Rigidbody ou ArticulationBody.

## OnCollision events

Le travail avec les événements de collision implique principalement les fonctions API suivantes :

[Collider.OnCollisionEnter](https://docs.unity3d.com/ScriptReference/Collider.OnCollisionEnter.html) : Appelée sur chaque GameObject lorsque deux Colliders entrent en contact pour la première fois.

[Collider.OnCollisionStay](https://docs.unity3d.com/ScriptReference/Collider.OnCollisionStay.html) : Appelée sur chaque GameObject une fois par mise à jour physique lorsque deux Colliders sont en contact.

[Collider.OnCollisionExit](https://docs.unity3d.com/ScriptReference/Collider.OnCollisionExit.html) : Appelée sur chaque GameObject lorsque deux Colliders cessent le contact.

> [!CAUTION]
> Pour les Collision events, au moins un des objets impliqués doit avoir un corps physique dynamique (c'est-à-dire un Rigidbody ou un ArticulationBody dont l'option IsKinematic est désactivée). 

> [!WARNING]
> Si les deux GameObjects d'une collision sont des corps physiques Kinematic, la collision n'appelle pas les fonctions OnCollision.

## OnTrigger events

Les Triggers Colliders ne provoquent pas de collisions. 
Au lieu de cela, ils détectent les autres **Colliders** qui les traversent et appellent des fonctions que vous pouvez utiliser pour déclencher des événements.

L'utilisation de Trigger Collider implique principalement les fonctions API suivantes :

[Collider.OnTriggerEnter](https://docs.unity3d.com/ScriptReference/Collider.OnTriggerEnter.html) : Appelée sur un GameObject qui possède un Collider en mode IsTrigger lorsqu'il entre en contact pour la première fois avec un autre Collider.

[Collider.OnTriggerStay](https://docs.unity3d.com/ScriptReference/Collider.OnTriggerStay.html) : Appelée sur un GameObject qui possède un Collider en mode IsTrigger une fois par image s'il détecte un autre Collider à l'intérieur de ses limites.

[Collider.OnTriggerExit](https://docs.unity3d.com/ScriptReference/Collider.OnTriggerExit.html) : Appelée sur un GameObject qui possède un Collider en mode IsTrigger lorsqu'il cesse le contact avec un autre Collider.

## Créer et configurer un Trigger Collider

1. Créez un GameObject
	- Pour créer un Trigger Collider invisible, créez un GameObject vide. Dans la plupart des cas, ces colliders sont invisibles.
	- Pour créer un Trigger Collider visible, créez un GameObject doté d'un Mesh. Ce type de Collider n'a besoin d'être visible que s'il est possible pour d'autres GameObjects de le traverser de manière visible pendant le jeu.
2. Ajoutez un composant Collider au GameObject
3. Configurez le Collider comme un Trigger:
	- En éditeur, affichez l'inspecteur du Collider en question et cochez la propriété IsTrigger
	- En script, modifiez la propriété IsTrigger avec la valeur true

# Input System

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.15/manual/QuickStartGuide.html)

Obtenir un Input directement à partir d'un périphérique d'entrée est rapide et pratique, mais nécessite un chemin distinct pour chaque type de périphérique.
Cela rend également plus difficile de modifier ultérieurement le contrôle du périphérique qui déclenche un événement spécifique dans le jeu.

À la place il est possible d'utiliser les actions comme intermédiaire entre les Inputs des périphériques et les réponses qu'ils déclenchent.
Le moyen le plus simple est d'utiliser le composant PlayerInput sur le GameObject d'un joueur. 

> [!IMPORTANT]
> Chaque PlayerInput représente un joueur différent dans le jeu.

## Modifier un asset Input Action

Pour afficher l'éditeur d'actions
- double-cliquez sur un élément .inputactions dans le navigateur de projet
- ou sélectionnez le bouton Modifier l'élément dans l'inspecteur de cet élément

L'éditeur d'actions apparaît sous la forme d'une fenêtre distincte, que vous pouvez également ancrer dans l'interface  pour ne pas avoir à accéder à l'asset systématiquement.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.inputsystem@1.15/manual/images/ActionsEditorCallout.png)

> [!CAUTION]
> Par défaut, Unity n'enregistre pas les modifications que vous effectuez dans l'éditeur d'actions lorsque vous enregistrez le projet.
> Pour enregistrer vos modifications, sélectionnez Save Asset dans la barre d'outils de la fenêtre.
> Ou bien activez l'enregistrement automatique en activant la case à cocher Auto Save dans la barre d'outils.
