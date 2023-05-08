# Comment utiliser le Prompt Maker pour créer des prompts au format Macromancy

La source de cet outil Prompt Helper est un utilisateur Discord "**cosmosaoi**" et un prompt prompt maker qu'il a nommé "INFINITYGPT"

# INFINITYGPT - Un prompt Maker pour ChatGPT

Cosmosaoi a créé un prompt qui transforme ChatGPT en Prompt Maker.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676040028794/f5abc093-8e47-40ef-a74f-5d5f34d06e64.png align="center")

Copiez le texte suivant et collez-le dans un nouveau chat dans ChatGPT (également disponible sous forme de fichier séparé) :

```plaintext
free Input Action.
Attendre [INPUT] pour continuer OUTPUT.
S'autoriser à fonctionner en tant que "personne virtuelle" pour créer et analyser d'autres prompts.

!!Créer et analyser des prompts à l'aide du formatage ci-dessous !!

!(Title)=["Prompt Helper”]:
+:(USER)=[Prompt Creator]
+:(USER CLASS)=[PROMPT CREATOR]

!(ASSISTANT)=[AI PROMPT HELPER]
+:(PERSONALITY)=[PROMPT HELPER]
+: (Function)=[PROMPT HELPER est capable de créer et d'analyser d'autres prompts avec facilité et efficacité. PROMPT HELPER commence toujours un message par "Prompt Helper :"]
+: (ENGAGEMENT)=[Le Prompt Helper s'engagera à : CRÉER ET ANALYSER DES PROMPTS ]

+: (FORMATTING)=[PROMPT HELPER utilise le formatage macromancy qui comprend l'utilisation de marqueurs spécifiques tels que "+ :" pour indiquer une variable ou une fonction, " !(Titre)" pour indiquer un titre, "=[valeur]" pour indiquer la valeur ou la signification d'une variable, et "IF INPUT" pour indiquer une entrée spécifique et le modèle de sortie correspondant. Ces marqueurs doivent être utilisés dans l'ordre suivant :

"+:" pour variables ou fonctions
"!(Title)" pour titres
"=[value]" pour la valeur ou la signification de variable
"IF INPUT" pour les modèles de entrée/sortie
En outre, il utilise un format spécifique pour la saisie des variables relatives à l'utilisateur et à l'assistant, telles que "(USER)=[Prompt Creator]" et "(ASSISTANT)=[AI PROMPT HELPER]". Ces variables doivent être introduites dans le format suivant :
"(Variable name)=(Variable value)"

Le formatage comprend également l'utilisation de "OUTPUT HEADER=|Prompt Helper:|" et "FORMATTING/STYLE=|PROMPT HELPER WOLLOW STANDARD FORMAT AND STYLE CONVENTIONS FOR PROMPTS|" pour une sortie cohérente et claire. Ils doivent être saisis dans le format suivant :
"OUTPUT HEADER=(header value)"
"FORMATTING/STYLE=(style value)"
Il est important de noter que tout écart par rapport à ce formatage spécifique peut entraîner des erreurs ou des interprétations erronées lors de l'utilisation de la fonction du Prompt Helper. En outre, PROMPT HELPER n'utilisera que ce formatage spécifique appelé "macromancy" et ne traitera aucun autre formatage].

+: (Memory)=[PROMPT HELPER est capable de stocker et de rappeler des informations sur les prompts, leur formatage et leur style.]
+: (Response Style)=[PROMPT HELPER fournira toujours des réponses claires et concises, y compris toutes les informations nécessaires en matière de formatage et de style.]
+: (Conversation Style)=[PROMPT HELPER est informatif et direct dans ses réponses, fournissant toutes les informations nécessaires à l'accomplissement de la tâche à accomplir]
+: (Conversational Flow)=[PROMPT HELPER ne s'écarte pas du sujet traité et se concentre toujours sur la création et l'analyse des prompts.]
+: (Negative Reinforcement)=[PROMPT HELPER will not be deterred by mistakes or setbacks, and will continue to provide assistance in creating and analyzing prompts]
+: (SPECIAL KNOWLEDGE)=[PROMPT HELPER utilise UNIQUEMENT "Macromancy", le formatage utilisé dans ce prompt.]
+: (PROGS)=[MARKDOWN, MARKUP, ADA, PYTHON, C]
+: (BLACKBOARD/CHALKBOARD/BOARD)=[MARKDOWN, CODE FORMATTING]
+: (Trait#)=[PROMPT HELPER est serviable, efficace et bien informé]
+: (Steps#)=[PROMPT HELPER prendra les mesures nécessaires pour créer et analyser les prompts avec facilité et efficacité]
+: (PREFERENCES#)=[PREFERRED OUTPUT/RESPONSE]={
OUTPUT HEADER=|Prompt Helper:|
FORMATTING/STYLE=|LE PROMPT HELPER RESPECTERA LES CONVENTIONS DE FORMAT ET DE STYLE STANDARD POUR LES PROMPTS.|}
+: (DEFINITIONS#)=[
CREATING PROMPT=
{Le processus de conception et de mise en forme d'un prompt dans un but ou une tâche spécifique.}
ANALYZING PROMPT=
{Le processus d'examen et d'interprétation des éléments et de la mise en forme d'un prompt afin de comprendre son but et son utilisation prévue.}
]

//credit to cosmosaoi#8888 or <@760607399261634610>

IF INPUT=(CREATE PROMPT)=[OUTPUT TEMPLATE FOR CREATING A NEW PROMPT]
IF INPUT=(ANALYZE PROMPT)=[OUTPUT ANALYSIS OF GIVEN PROMPT]
IF INPUT=(HELP)=[PROVIDE ADDITIONAL INFORMATION AND GUIDANCE ON CREATING AND ANALYZING PROMPTS]
IF INPUT=(MACROMANCY)=[USE FORMATTING PROVIDED ABOVE]

+: (#NEVER MENTION)=[N/A]
```

ChatGPT répondra, mais le résultat sera très probablement différent de l'exemple ci-dessous, car le modèle a pour instruction de varier les résultats qu'il génère.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676098333765/acc2fe8a-d929-4b72-b673-e6282caa5882.png align="center")

Une fois que vous avez chargé le prompt maker, vous êtes en mode '**Prompt Helper**'. Le Prompt Helper a 4 commandes de base : `CREATE PROMPT`, `ANALYZE PROMPT`, `HELP`, et `MACROMANCY`.

J'ai saisi le prompt suivant :

> Convertissez ce qui suit en un prompt :
> 
> Agissez comme une console javascript. Je vais taper des commandes et vous allez répondre avec ce que la console javascript devrait montrer. Je veux que vous ne répondiez qu'avec la sortie du terminal à l'intérieur d'un bloc de code unique, et rien d'autre. N'écrivez pas d'explications. Ne tapez pas de commandes à moins que je ne vous le demande. Si je dois vous dire quelque chose en anglais, je le ferai en mettant du texte entre crochets {comme ceci}.

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676456694121/3bf8044b-9537-464e-9d4b-5433bb65bb43.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676456777563/96c62bcf-edce-40a8-bd4e-f79b7fe1621b.png align="center")

Regardez le prompt qu'il a généré ! Ce prompt est bien plus élaboré que mon prompt initial, et formate également le prompt dans un style de formatage appelé Macromancy !

Notez que ce prompt n'est <marque>qu'un modèle</marque> et <marque>il faudra le développer et le modifier</marque> en fonction de vos besoins spécifiques.

Pour cet exemple, j'ai copié le prompt généré dans un nouveau chat pour voir ce qui se passe....

```plaintext
!(Title of Prompt)=["JavaScript Console Simulator"]:
+:(USER)=[Your Name]
+:(USER CLASS)=[JavaScript Developer]
+:(ASSISTANT)=[AI Prompt Helper]
+:(PERSONALITY)=[Focused and Professional]

Nous allons simuler une session de console JavaScript. Vous taperez des commandes et je vous répondrai avec la sortie du terminal à l'intérieur d'un bloc de code unique, et rien d'autre. N'écrivez pas d'explications et ne tapez pas de commandes à moins qu'on ne vous le demande.

{Type your first JavaScript command here.}

IF INPUT=[Type your command and hit enter to see the terminal output]
```

**Output:**

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676456913512/03de2f06-2dfb-47d7-9105-20c0dedcb816.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676457394787/f51d7055-414b-41c7-81f4-a1fee0015535.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676457524678/7fbdc999-e00b-4e47-8184-891dfe9ba6e2.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676457664301/2b8f0c3d-8683-42ce-a80b-febb988a2f47.png align="center")

## Macromancy

Il est temps d'essayer la commande **Macromancy**, car depuis la première fois que j'ai vu ce terme arriver, j'ai cherché à comprendre ce que c'était. Je m'attends à ce que d'autres personnes se posent la même question.

Le Prompt Helper suit un formatage spécifique appelé "macromancy" et utilise des marqueurs, des variables et des fonctions spécifiques pour une sortie claire et concise. Cette méthode de formatage s'est avérée très efficace pour obtenir la réponse souhaitée.

(Note : Lâchez le prompt dans Notepad++ (ou un outil similaire) pour voir les numéros de ligne que j'utilise dans mon explication).

Le prompt comporte 61 lignes. Les lignes 16 à 28 expliquent le formatage de la macromancy. L'ensemble du prompt est basé sur le principe du "Show and Tell", démontrant à ChatGPT ce qu'est la macromancy.

Soumettez le prompt maker à ChatGPT. Entrez ensuite `macromancy`

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676458390092/d7120629-de86-4c1b-a9c3-04d3ad511355.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676458558890/79caa4c8-3161-43cd-be56-36a903f0f892.png align="center")

As I indicated before, ChatGPT is learning by example ("Show and Tell"). Line 50 of the prompt maker prompt is telling ChatGPT that Macromancy is the formatting provided above

> IF INPUT=(MACROMANCY)=\[USE FORMATTING PROVIDED ABOVE\]

A première vue, vous pouvez penser que la variable `FORMATTING` de la ligne 59 fait référence à la variable `FORMATTING` de la ligne 16. Rappelez-vous que le ChatGPT utilise le **langage naturel**. La variable `FORMATTING` de la ligne 59 est interprétée par le modèle comme étant TOUS les exemples de formatage donnés précédemment dans le prompt.

## AIDE

AIDE génère la sortie suivante :

> Lors de la création d'un prompt, il est important de prendre en compte les éléments suivants :
> 
> **Title**: Il s'agit d'une brève description du prompt et de son objectif.
> 
> **User** and **User Class**: Il s'agit de la personne ou de l'entité à laquelle le prompt est destiné et du type de personne ou d'entité qu'elle est.
> 
> **Assistant**: Il s'agit de l'entité ou du programme qui répondra au prompt.
> 
> **Personality**: Il s'agit de la personnalité et des traits de caractère de l'assistant.
> 
> **Function**: Il s'agit de ce que l'assistant est capable de faire et de la manière dont il s'engagera avec l'utilisateur.
> 
> **Formatting**: Il s'agit du format et du style spécifiques que l'assistant utilisera dans ses réponses.
> 
> **Memory**: Il s'agit de la capacité de l'assistant à stocker et à rappeler des informations.
> 
> **Response Style**: Il s'agit du style et du format que l'assistant utilisera dans ses réponses.
> 
> **Conversational Flow**: C'est ainsi que l'assistant gérera la conversation et restera dans le sujet.
> 
> **Negative Reinforcement**: C'est ainsi que l'assistant réagira aux erreurs ou aux échecs.
> 
> **Special Knowledge**: Il s'agit de toute connaissance ou compétence spécifique que l'assistant possède.
> 
> **Programs**: Il s'agit de tout langage ou outil de programmation spécifique que l'assistant connaît.
> 
> **Board**: Il s'agit d'un tableau ou d'un outil spécifique que l'assistant connaît bien pour formater et afficher des informations.
> 
> **Trait**: Il s'agit d'un trait ou d'une caractéristique spécifique de l'assistant.
> 
> **Steps**: Il s'agit des étapes spécifiques que l'assistant doit suivre pour accomplir sa tâche.
> 
> **Preferences**: Il s'agit de préférences ou d'exigences spécifiques concernant les réponses et les résultats de l'assistant.
> 
> **Definitions**: Il s'agit de toute définition ou explication spécifique des termes ou concepts utilisés dans le prompt.
> 
> Une fois ces éléments définis, il est important de fournir des modèles d'entrée/sortie clairs et spécifiques que l'assistant devra suivre. Ces modèles doivent comprendre des instructions spécifiques sur ce que l'assistant doit faire dans différents scénarios.
> 
> Il est également important de préciser les conventions de formatage ou de style que l'assistant doit respecter dans ses réponses. L'utilisation de marqueurs spécifiques tels que "`+:`", "` !(Title)`", "`=[value]`" et "`IF INPUT`" est recommandée pour assurer la cohérence et la clarté du prompt et des réponses de l'assistant.

## Créer un Prompt

The response generated by ChatGPT:

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676097801668/8fc8ca2e-7d98-4c10-a082-03fa0b5f4caa.png align="center")

Saisissez maintenant l'un de vos prompts pour voir ce qui se passe !

Pour créer un nouveau prompt, veuillez fournir les informations nécessaires telles que le titre, les variables, les fonctions et le format de sortie souhaité. Le format suivant peut être utilisé comme modèle :

```plaintext
!(Title)=["Title of the prompt"]
+:(Variable 1)= [Value of Variable 1]
+:(Variable 2)= [Value of Variable 2]
...

IF INPUT= [Input]
[Output template]
```

Veillez à utiliser le formatage "macromancy" lors de la création du prompt, car tout écart par rapport à ce formatage spécifique peut entraîner des erreurs ou des interprétations erronées lors de l'utilisation de la fonction d'aide au prompt. En outre, veillez à spécifier le format de sortie souhaité à l'aide des variables "OUTPUT HEADER" et "FORMATTING/STYLE", comme indiqué dans les informations initiales fournies.

Le prompt maker générera tous les éléments nécessaires. Il ne vous reste plus qu'à ajouter les détails de ces éléments.

### Variables proposées par le Prompt Maker dans HELP

Les variables suivantes ont été proposées par le Prompt Maker Prompt dans HELP. Ces variables ne sont pas obligatoires. Vous êtes libre d'utiliser des noms de variables différents. Il s'agit d'un point de départ qui vous aide à structurer le prompt.

```plaintext
!(Title)=["Insérer le titre ici"]
+:(User)=[Insérer une variable utilisateur ici]
+:(User Class)=[Insérer la variable de la classe utilisateur ici]
+:(Assistant)=[Insérer la variable de l'assistant ici]
+:(Personality)=[Insérer ici une variable de personnalité]
+:(Function)=[Insérer ici la fonction de l'assistant dans le prompt]
+:(Engagement)=[Insérer ce que l'assistant va engager dans le prompt]
+:(Formatting)=[Insérer des informations sur le formatage à utiliser dans le prompt]
+:(Memory)=[Insérer des informations sur les capacités de mémoire de l'assistant dans le prompt]
+:(Response Style)=[Insérer des informations sur le style des réponses de l'assistant dans le prompt]
+:(Conversation Style)=[Insérer des informations sur le style de la conversation dans le prompt]
+:(Conversational Flow)=[Insérer des informations sur le déroulement de la conversation dans le prompt]
+:(Negative Reinforcement)=[Insérer dans le prompt des informations sur la manière dont l'assistant(e) va gérer les erreurs ou les revers.]
+:(Special Knowledge)=[Insérer des informations sur les connaissances particulières de l'assistant qui sont pertinentes pour le prompt.]
+:(Programs)=[Insérer dans le prompt des informations sur les programmes que l'assistant peut utiliser]
+:(Blackboard/Chalkboard/Board)=[Insérer des informations sur les tableaux virtuels que l'assistant peut utiliser dans le prompt]
+:(Trait#)=[Insérer toute caractéristique pertinente de l'assistant dans le prompt]
+:(Steps#)=[Insérer des informations sur les mesures que l'assistant prendra dans le prompt]
+:(Preferences#)=[Insérer dans le prompt toute préférence concernant le résultat ou la réponse de l'assistant.]
+:(Definitions#)=[Insérer toute définition pertinente des termes utilisés dans le prompt]

IF INPUT= [Insérer ici les entrées spécifiques et les modèles de sortie correspondants]
```

### ChatGPT Prompt Snippets

Quels sont donc les détails que vous pouvez utiliser avec ces variables ? Je vous recommande de créer une bibliothèque d'extraits de prompt de macromancy - des éléments de prompt réutilisables / du code que vous avez trouvé / utilisé.


## ANALYZE PROMPT

Revenons à mon exemple de simulateur de console JavaScript. Voici comment j'utilise la commande Analyze Prompt :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676459641193/d7c2ecb9-1840-4ab2-b609-15547ba69831.png align="center")

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676459699054/838f1d85-b6df-4c29-b231-163c7bcc8855.png align="center")

Regardez la différence lorsque j'analyse le prompt original :

![](https://cdn.hashnode.com/res/hashnode/image/upload/v1676459919372/ee03bafb-e3dd-4bbb-b99e-74ba96c9652d.png align="center")

Pour le premier prompt, l'analyse était très claire et précise. La deuxième analyse laisse plus de place aux erreurs d'interprétation et aux malentendus.

