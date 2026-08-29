# MMI 2027 - Bases

# Setup

## Créer un nouveau projet depuis un Template

> [!NOTE]
> Vous retrouverez le tutoriel en ligne [ici](https://learn.unity.com/tutorial/get-started-with-unity-in-editor-tutorial)

1. Ouvrez Unity Hub et sélectionnez l'onglet Projects dans la barre de menu à gauche
2. Appuyez sur le bouton bleu "New project" en haut à droite
3. Sélectionnez la version Unity 6.5
4. Sélectionnez le template "Get Started With Unity"
5. Saisissez un nom pour le projet
6. Cliquez sur le bouton "Create project" et attendez l'ouverture du projet

## Ouvrir un projet Unity existant

1. Ouvrez Unity Hub et sélectionnez l'onglet Projects dans la barre de menu à gauche
2. Appuyez sur le bouton "Add" en haut à droite
3. Sélectionnez le répertoire du projet
4. Cliquez sur le bouton "Open" et attendez l'ouverture du projet

# Premiers pas dans Unity

> [!NOTE]
> Pour plus de détails vous pouvez suivre le tutorial [ici](https://learn.unity.com/tutorial/explore-the-unity-editor-1)

## L'interface de l'éditeur
![Image d'illustration des zones de l'éditeur](https://unity-connect-prd.storage.googleapis.com/20220606/learn/images/7fabb375-5282-4852-9ecf-d8acc254052b_EditorExplore.png)

### Scene view et Game view 
Zones de visualisation des objets 3D (**Scene**) et la vue joueur (**Game**)
> [!TIP]
> Avec le layout par défaut la Game View apparaît au même endroit. Utilisez les onglets pour naviguer.

### Hierarchy window 
Collection d’objets dans la scène.

### Project window 
Équivalent d’un explorateur de fichiers pour le projet.

### Toolbar 
Outils de navigation et de manipulation dans la scène

### Inspector window 
Panneau de configuration d’un objet sélectionné.

## Manipuler les objets 3D
![Image d'illustration des outils de transformation](https://unity-connect-prd.storage.googleapis.com/20220601/learn/images/057c859e-04d5-429a-b980-b852a80b2015_gizmos.png)

- W: Outil de déplacement, pour sélectionner et bouger un objet
- E: Outil de rotation, pour sélectionner et tourner un objet
- R: Outil de dimensionnement, pour sélection et changer la taille d'un objet

> [!TIP]
> Utilisez les raccourcis par défaut W (Move), E (Rotate), R (Scale) pour sélectionner l'outil rapidement.

Pour chacun des outils de transformation, un Gizmo apparaît qui vous permet de manipuler le GameObject le long de chaque axe spécifique. 
Lorsque vous manipulez ces contrôles, les valeurs du composant Transform changent en conséquence.

## Créer une nouvelle scène
### Scène vide
1. Ouvrez le dossier **Assets/Scenes** dans la fenêtre Project
2. Cliquez droit pour ouvrir le menu contextuel
3. Sélectionnez **Create/Scene** 
4. Nommez la scène

### Template
1. Ouvrez le menu **File / New Scene…**
2. Sélectionnez le template souhaité
3. Sauvegardez la scène ouverte

### Ajouter la nouvelle scène au build
1. Ouvrez le sous-menu **Build Profiles** depuis le menu **File**
2. Sélectionner l'onglet "Scene List"
2. Glissez/déposez la nouvelle scène dans l'encadré

> [!TIP]
> Utilisez le raccourcis Ctrl+Shift+B pour ouvrir rapidement les Build Settings

# Prefabs

Un Prefab agit comme un modèle à partir duquel vous pouvez créer de nouvelles instances préfabriquées d'un GameObject dans la scène. 
Cela vous permet de créer, configurer et stocker un GameObject complet avec tous ses composants, valeurs de propriété et enfants en tant qu'asset réutilisable.

## Créer un Prefab
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/CreatingPrefabs.html)

Faites glisser un GameObject de la fenêtre Hierarchy vers la fenêtre Project.
Le GameObject, ainsi que tous ses composants et enfants, deviennent un nouvel Asset dans votre fenêtre Project. 

> [!TIP]
> Ce processus de création du Prefab transforme également le GameObject d'origine en une instance du nouveau Prefab.

Les Prefabs dans la fenêtre Project sont affichés avec une vue miniature du GameObject ou l'icône Prefab en forme de cube bleu en fonction de la manière dont vous avez paramétré l'affichage.

![Image d'illustration](https://docs.unity3d.com/6000.2/Documentation/uploads/Main/prefab-workflow.png)

Toutes les modifications sont automatiquement répercutées dans les instances du Prefab modifié. 
Cela permet des changements à l'échelle du projet sans avoir à effectuer à plusieurs reprises la même modification sur chaque copie de l'élément.

Vous pouvez remplacer les paramètres des instances de Prefab individuelles si vous souhaitez que certaines instances d'un Prefab diffèrent des autres. 
Vous pouvez également créer des variantes de Prefab qui vous permettent de regrouper un ensemble de remplacements dans une variation significative d'un Prefab appelée Prefab Variant.

## Modifier un Prefab
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/EditingInPrefabMode.html)

Ouvrez-le dans le Prefab Mode en cliquant sur la flèche à droite de son nom dans la scène.
Ou en double-cliquant sur le Prefab dans la fenêtre Project.

![Image d'illustration](https://learn.unity.com/_next/image?url=https%3A%2F%2Fconnect-mediagw.unity.com%2Fh1%2F20200829%2Flearn%2Fimages%2Fb9bb8293-36d2-4611-be04-9d241c979ba1_image2.png&w=640&q=75)

Ce mode vous permet d'afficher et de modifier le contenu du Prefab séparément de tout autre GameObject dans votre scène. 
Les modifications que vous effectuez dans le Prefab Mode affectent toutes les instances de ce Prefab.

![Image d'illustration](https://docs.unity3d.com/6000.2/Documentation/uploads/Main/prefabs-isolation-mode.png)

En Prefab Mode, la vue Scene affiche une barre de navigation en haut. 
L'entrée la plus à droite correspond au Prefab actuellement ouvert. 
Utilisez la barre de navigation pour revenir aux scènes principales ou aux autresPrefabs que vous avez peut-être ouvertes en naviguant la hiérarchie.

## Prefab Variants
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/PrefabVariants.html)

Une variante de Prefab hérite des propriétés d'un autre Prefab, appelée la base. 
Les modifications apportés à la variante de Prefab ont priorité sur les valeurs de la base. 
Une variante de Prefab peut avoir n'importe quelle autre Prefab comme base, y compris les Prefab de modèle ou d'autres variantes de Prefab.

Les Prefab Variant sont affichées avec l'icône préfabriquée bleue décorée de flèches.

![Image d'illustration](https://docs.unity3d.com/6000.2/Documentation/uploads/Main/prefab-variant-icon.png)

Cliquez avec le bouton droit sur un Prefab dans la vue Project et sélectionner Create > Prefab Variant. 
Cela crée une variante du Prefab sélectionné, qui ne comporte initialement aucune substitution. 
Vous pouvez ouvrir la variante de Prefab dans le Prefab Mode pour commencer à y ajouter des substitutions.

Vous pouvez également faire glisser une instance de Prefab de la **Hierarchy** vers la fenêtre **Project**. 
Une boîte de dialogue vous demande si vous souhaitez créer un nouveau Prefab ou un Prefab Variant. 
Si vous choisissez Prefab Variant, vous obtenez une nouvelle variante basée sur l'instance de Prefab que vous avez fait glisser. 
Toutes les substitutions que vous aviez sur cette instance se trouvent désormais à l'intérieur de la nouvelle variante. 
Vous pouvez l'ouvrir dans le Prefab Mode pour ajouter des substitutions supplémentaires ou pour modifier ou supprimer des substitutions.

# Créer un nouveau script

> [!CAUTION]
> Avant d'aller plus loin, assurez-vous d'avoir exploré l'éditeur en suivant le tutorial [Get Started With Unity](https://learn.unity.com/tutorial/get-started-with-unity-in-editor-tutorial)

> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/CreatingAndUsingScripts.html)

- À partir du menu Créer en haut à gauche du panneau Projet
- À partir du menu contextuel (clic droit) Create / C# Script
- En sélectionnant Assets > Create > C# Script dans le menu principal

> [!TIP]
> Lorsque vous créez un script C# à partir de la fenêtre de projet d’Unity, il hérite automatiquement de [MonoBehaviour](https://docs.unity3d.com/Manual/class-MonoBehaviour.html) et vous fournit un template.

## Ajouter un nouveau component
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/UsingComponents.html)

Une fois sélectionné le GameObject
- À partir du menu Component s'il s'agit d'un composant natif
- Par le Component Browser dans l'inspecteur

# L'interface utilisateur (UI)

## Le Canvas
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/UICanvas.html)

Le Canvas est la zone dans laquelle tous les éléments de l'interface utilisateur doivent se trouver. 
Le Canvas est un gameobject avec un composant Canvas dessus, et tous les éléments de l'interface utilisateur doivent être des enfants de ce Canvas. 
Les éléments UI peuvent être configurés pour s'adapter ou s'étirer jusqu'à une position établie dans le Canvas.

![Image d'illustration](https://unity-connect-prd.storage.googleapis.com/20201103/learn/images/3b893a7f-c707-4dde-95e8-d5dbd58cbe36_93.png)

> [!TIP]
> Un cadre rectangulaire blanc dans la scène représente les limites visibles du Canvas.

### Modes de rendu
Le Canvas dispose d'un paramètre de mode de rendu qui peut être utilisé pour le rendre dans l'espace écran (Screen Space) ou dans l'espace 3D (World Space).

#### Screen Space - Overlay
Ce mode de rendu place les éléments de l'interface utilisateur sur l'écran rendu au-dessus de la scène. 
Si l'écran est redimensionné ou change de résolution, le Canvas changera automatiquement de taille pour correspondre à cela.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/GUI_Canvas_Screenspace_Overlay.png)

#### Screen Space - Camera
Ce mode de rendu est similaire à Screen Space - Overlay, mais dans ce mode de rendu, le Canvas est placé à une distance donnée devant une caméra spécifiée. 
Les éléments de l'interface utilisateur sont rendus par cette caméra, ce qui signifie que les paramètres de la caméra affectent l'apparence de l'interface utilisateur.

#### World Space
Dans ce mode de rendu, le Canvas se comportera comme n'importe quel autre objet de la scène. 
La taille du Canvas peut être définie manuellement à l'aide de son composant Rect Transform, et les éléments de l'interface utilisateur s'afficheront devant ou derrière d'autres objets de la scène en fonction du placement 3D. 
Ceci est utile pour les interfaces utilisateur qui sont censées faire partie du monde. 

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/GUI_Canvas_Worldspace.png)

> [!NOTE]
> C'est ce qu'on appelle également une « interface diégétique ».

## Modifier les éléments UI
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/UIBasicLayout.html)

Chaque élément de l'interface utilisateur est représenté sous forme de rectangle à des fins de mise en page. Ce rectangle peut être manipulé dans la vue de la scène à l'aide de l'outil Rect dans la barre d'outils.

L'outil Rect peut être utilisé pour déplacer, redimensionner et faire pivoter des éléments d'interface utilisateur. Une fois que vous avez sélectionné un élément d'interface utilisateur, vous pouvez le déplacer en cliquant n'importe où à l'intérieur du rectangle et en le faisant glisser.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/GUI_Rect_Tool_Button.png)

Tout comme les autres outils, l'outil Rect utilise le mode de pivot et l'espace d'édition, définis dans la barre d'outils. Lorsque vous travaillez avec l'interface utilisateur, il est généralement judicieux de conserver ces paramètres sur Pivot et Local. Ainsi que de basculer la vue caméra en mode 2D.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/GUI_Pivot_Local_Buttons.png)

### Pivot
Les rotations, les modifications de taille et d'échelle se produisent autour du pivot, de sorte que la position du pivot affecte le résultat d'une rotation, d'un redimensionnement ou d'une mise à l'échelle.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/UI_PivotRotate.png)

### Ancres
Le composant Rect Transform inclus un concept de mise en page appelé ancres. 
Les ancres sont représentées par quatre petites poignées triangulaires dans la vue de la scène et les informations sur les ancres sont également affichées dans l'inspecteur.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/UI_Anchored1.gif)

Si le parent d'un Rect Transform est également un Rect Transform, l'enfant peut être ancré au parent de différentes manières.

L'ancrage permet également à l'enfant de s'étirer en fonction de la largeur ou de la hauteur du parent. De cette façon, les différents coins du rectangle peuvent être ancrés à différents points du rectangle parent.

Les positions des ancres sont définies en fractions (ou pourcentages) de la largeur et de la hauteur du rectangle parent. 

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/UI_Anchored4.gif)

> [!IMPORTANT]
> 0,0 (0 %) correspond au côté gauche ou inférieur, 0,5 (50 %) au milieu et 1,0 (100 %) au côté droit ou supérieur.

Dans l'inspecteur, le bouton Anchor Preset se trouve dans le coin supérieur gauche du composant Transformation rectangulaire. Cliquez sur le bouton pour afficher la liste déroulante de presets. À partir de là, vous pouvez rapidement sélectionner certaines des options d'ancrage les plus courantes.

## Ratio et Résolution
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/HOWTO-UIMultiResolution.html)

Les jeux et applications modernes doivent souvent prendre en charge une grande variété de résolutions d'écran différentes et les dispositions de l'interface utilisateur doivent notamment pouvoir s'adapter à cela.

Les éléments de l'interface utilisateur sont ancrés par défaut au centre du rectangle parent. Cela signifie qu'ils conservent un décalage constant par rapport au centre. Si la résolution est modifiée en format paysage avec cette configuration, les boutons pourraient carrément se retrouver en dehors de l'écran.

Une façon de conserver les boutons à l’intérieur de l’écran est de modifier la disposition de sorte que les emplacements des boutons soient liés à leurs coins respectifs de l’écran plutôt qu'au centre.

![Image d'illustration](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/images/UI_MultiResCorners.png)

Lorsque la taille de l'écran est modifiée pour une résolution plus grande ou plus petite, les boutons restent également ancrés dans leurs coins respectifs. 
Cependant, comme ils conservent leur taille d'origine spécifiée en pixels, ils peuvent occuper une proportion plus ou moins grande de l'écran.

C'est là que le composant Canvas Scaler peut vous aider.
Vous pouvez définir son UI Scale Mode sur Scale With Screen Size. Avec ce mode d'échelle, vous pouvez spécifier une résolution à utiliser comme référence. Si la résolution d'écran actuelle est inférieure ou supérieure à cette résolution de référence, le facteur d'échelle du Canvas est défini en conséquence, de sorte que tous les éléments de l'interface utilisateur sont agrandis ou réduits en même temps que la résolution de l'écran.

> [!IMPORTANT]
> Une chose à savoir : après avoir ajouté un composant Canvas Scaler, il est important de vérifier également à quoi ressemble la mise en page dans d'autres rapports hauteur/largeur.

## Outils éditeur

Il existe différents outils dans l'éditeur pour simuler le rendu dans différents ratios ou configurations.

### Aspect Ratio
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/GameView.html)

Dans la fenêtre Game, cette option permet de tester l'apparence de votre jeu sur des écrans avec différents rapports hauteur/largeur. 

![Image d'illustration](https://docs.unity3d.com/uploads/Main/game-view-window.png)

Par défaut, le rapport hauteur/largeur est défini sur Free Aspect. Cela correspond finalement à tester le rendu uniquement dans les dimensions actuelles de la fenêtre. Donc potentiellement très loin de la réalité.

Vous pouvez changer cette configuration vers une configuration ou un ratio prédéfini. Ou bien créer une configuration personnalisée suivant vos besoins.

### Simulator view
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Manual/device-simulator-view.html)

Utilisez la vue Simulateur pour prévisualiser l'apparence de votre application créée sur un appareil mobile.

![Image d'illustration](https://docs.unity3d.com/uploads/Main/device-simulator-view.png)

Pour basculer entre les vues Game et Simulator, dans l'onglet Game/Simulator, sélectionnez une option dans le menu.

Vous pouvez également ouvrir la vue Simulator en allant dans Window > General et en sélectionnant Device Simulator. Si aucune instance de la vue Simulator n'est ouverte, elle s'ouvre sous forme de fenêtre flottante.

## Interagir avec les éléments UI
> [!NOTE]
> Plus de détails dans le [manuel](https://docs.unity3d.com/Packages/com.unity.ugui@1.0/manual/UIInteractionComponents.html)

Canvas utilise l'objet EventSystem pour transmettre des messages entre l'interface et le code.
Cet objet est ajouté automatiquement dans la scène à la création d'un nouvel objet Canvas et est indispensable pour que les éléments interactifs de l'interface fonctionnent.

La plupart des composants d'interaction ont des points communs. Ils sont sélectionnables, ce qui signifie qu'ils partagent une fonctionnalité intégrée pour visualiser les transitions entre les états.

Les composants d'interaction ont au moins un UnityEvent qui est invoqué lorsque l'utilisateur interagit avec le composant d'une manière spécifique. Le système d'interface utilisateur détecte et enregistre toutes les exceptions qui se propagent hors du code attaché à UnityEvent.
