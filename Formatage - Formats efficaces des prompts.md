# Des formats de prompt efficaces
Le Prompt Helper est un outil formidable, mais il peut y avoir plusieurs raisons pour lesquelles vous préférez concevoir votre prompt d'une autre manière. Ce chapitre présente les meilleures pratiques que j'ai trouvées en parcourant de nombreux groupes, vidéos, etc. En raison de la manière dont les modèles de suivi des instructions sont entraînés ou des données sur lesquelles ils sont entraînés, il existe des formats de prompt spécifiques qui fonctionnent particulièrement bien et qui s'alignent mieux sur les tâches à accomplir.

Voici un certain nombre de formats de prompt qui fonctionnent de manière fiable, mais n'hésitez pas à explorer d'autres formats, qui peuvent s'adapter au mieux à votre tâche.

Règles empiriques et exemples Remarque : l'expression `"{entrée de texte ici}"` est un espace réservé pour le texte/contexte réel.

# Placez les instructions au début du prompt et utilisez ### ou """ pour séparer l'instruction et le contexte.

```
Résumez le texte ci-dessous sous la forme d'une liste à puces des points les plus importants.
Text: """ {text input here} """  
```
La documentation de l'OpenAI fait référence à `###` et `"""` comme une séquence d'arrêt.

Chaque prompt contient une séquence d'arrêt. Si vous ne fournissez pas de séquence d'arrêt, alors `/n` agit comme une séquence d'arrêt.

La règle consistant à placer d'abord les instructions dans le prompt, puis dans le contexte, n'est pas une règle absolue, comme l'illustre l'exemple suivant.

# Exemple de séquence d'arrêt utilisant """
Ceci est un exemple fourni par OpenAI qui montre comment GPT peut être utilisé pour **expliquer un morceau de code compliqué.**

**The prompt:**
```
class Log:
    def __init__(self, path):
        dirname = os.path.dirname(path)
        os.makedirs(dirname, exist_ok=True)
        f = open(path, "a+")

        # Check that the file is newline-terminated
        size = os.path.getsize(path)
        if size > 0:
            f.seek(size - 1)
            end = f.read(1)
            if end != "\n":
                f.write("\n")
        self.f = f
        self.path = path

    def log(self, event):
        event["_event_id"] = str(uuid.uuid4())
        json.dump(event, self.f)
        self.f.write("\n")

    def state(self):
        state = {"complete": set(), "last": None}
        for line in open(self.path):
            event = json.loads(line)
            if event["type"] == "submit" and event["success"]:
                state["complete"].add(event["id"])
                state["last"] = event
        return state

"""
Voici ce que fait la classe ci-dessus :
1.
```

` """ ` est la séquence d'arrêt dans cet exemple. Cette séquence d'arrêt sert de séparateur entre deux sections, une section contenant le contexte et une section contenant les instructions. J'ai déjà vu des exemples de prompts contenant plusieurs séparateurs (séquences d'arrêt).

Soyez aussi précis, descriptif et détaillé que possible en ce qui concerne le contexte, le résultat, la longueur, le format, le style, etc. souhaités.

```
Rédigez un court poème inspirant sur un lever de soleil, vu sur une plage aux eaux calmes, dans le style de {célèbre poète}.
```

# Montrer et dire
Les modèles réagissent mieux lorsqu'on leur présente des exigences spécifiques en matière de format. Cela facilite également l'analyse programmatique de plusieurs sorties de manière fiable.
```
Extrayez les entités importantes mentionnées dans le texte ci-dessous. Extrayez d'abord tous les noms d'entreprises, puis tous les noms de personnes, puis les sujets spécifiques qui correspondent au contenu et enfin les thèmes généraux.

Desired format:
Company names: <comma_separated_list_of_company_names>
People names: -||-
Specific topics: -||-
General themes: -||-

Text: {text}
```
## Zero-shot, then few-shot
**Zero-shot:**
```
Extraire les mots-clés du texte ci-dessous.

Text: {text}

Keywords:
```
## Quelques clichés - à l'aide de quelques exemples :

```
Extrayez les mots-clés des textes correspondants ci-dessous.

Texte 1 : Stripe fournit des API que les développeurs web peuvent utiliser pour intégrer le traitement des paiements dans leurs sites web et applications mobiles.
Mots clés 1 : Stripe, traitement des paiements, API, développeurs web, sites web, applications mobiles
###
Texte 2 : OpenAI a formé des modèles de langage de pointe qui sont très bons pour comprendre et générer du texte. Notre API donne accès à ces modèles et peut être utilisée pour résoudre pratiquement n'importe quelle tâche impliquant le traitement du langage.
Mots clés 2 : OpenAI, modèles de langage, traitement de texte, API.
###
Texte 3 : {texte}
Mots clés 3 :
```

Ce prompt fournit deux exemples. Le texte 3 est l'endroit où vous indiquez votre texte, et vous laissez les mots-clés 3 vides. Le modèle génère les mots-clés.

Notez l'utilisation d'une séquence d'arrêt entre chaque exemple.

# Réduire les descriptions floues et imprécises
La description suivante est moins efficace :
```
La description de ce produit doit être assez courte, quelques phrases seulement, sans plus.
```

Cette description est meilleure :
```
Décrivez ce produit dans un paragraphe de 3 à 5 phrases.
```

# Dire au modèle ce qu'il doit faire au lieu de lui dire ce qu'il ne doit PAS faire
Moins efficace :
```
Ce qui suit est une conversation entre un agent et un client. NE PAS DEMANDER LE NOM D'UTILISATEUR OU LE MOT DE PASSE. NE PAS RÉPÉTER.

Le client : Je n'arrive pas à me connecter à mon compte.

Agent:
```

Plus efficace :
```
Ce qui suit est une conversation entre un agent et un client. L'agent tente de diagnostiquer le problème et de proposer une solution, tout en s'abstenant de poser des questions relatives aux informations nominatives. Au lieu de demander des informations nominatives, telles que le nom d'utilisateur ou le mot de passe, il renvoie l'utilisateur à l'article d'aide www.samplewebsite.com/help/faq.

Customer: Je ne peux pas me connecter à mon compte.

Agent:
```
# Spécifique à la génération de code - Utiliser des "mots-clés" pour orienter le modèle vers un modèle particulier.
Moins efficace
```
# Écrire une fonction python simple qui
# 1. Me demander un nombre en mille
# 2. Elle convertit les miles en kilomètres
Dans l'exemple de code ci-dessous, l'ajout de "import" indique au modèle qu'il doit commencer à écrire en Python. (De même, "SELECT" est une bonne indication pour le début d'une instruction SQL).
```
Plus efficace
```
# Écrire une fonction python simple qui
# 1. Me demande un nombre en mille
# 2. convertit les miles en kilomètres

import
```

# Formatage Markdown
L'interface web de ChatGPT peut générer des résultats en utilisant CommonMark. Toutes les options de formatage Markdown ne sont pas disponibles, mais certains formats peuvent être implémentés pour différents types de prompts.

Un des exemples les plus simples est de demander à ChatGPT de produire une sortie dans un tableau Markdown :
```
Créez un tableau markdown répertoriant 3 types de fruits, leur couleur et un fait intéressant sur chacun d'entre eux.

```

D'autres options de formatage utiles sont disponibles :
```
# Heading 1
## Heading 2
### Heading 3

*italic text*, **bold text**, __underlined text__

[Hyperlinks](www.google.com)
![Images](https://image.pollinations.ai/prompt/lake)
```

Un guide de formatage plus complet (avec des exemples de chaque type de sortie) est disponible à l'adresse suivante `ChatGPT Formatting Guide` [prompt]

## Un guide de formatage complet pour les prompts ChatGPT utilisant CommonMark
* **Line breaks**: Pour créer un saut de ligne, il suffit d'appuyer deux fois sur la touche Entrée/Retour. Exemple : Ceci est la première ligne. Voici la deuxième ligne.
* **Numbered lists**: Pour créer une liste numérotée, commencez chaque élément par un chiffre et un point, suivis d'un espace.
* **Bulleted lists**: Pour créer une liste à puces, commencez chaque élément par un tiret (-) ou un astérisque (*), suivi d'un espace.
* **Bold text**: Pour mettre en forme un texte en gras, entourez-le de doubles astérisques (**).
* **Italic text**: Pour formater le texte en italique, entourez-le d'astérisques (*).
* **Bold and italic text**: Pour mettre en forme un texte en gras et en italique, entourez-le de trois astérisques. (***).
* **Inline code**: Pour formater un texte en tant que code en ligne, entourez le texte de barres d'espacement simples. (`).
* **Code blocks**: Pour formater plusieurs lignes de code sous la forme d'un bloc de code, entourez le code de triples crochets (```), éventuellement suivis du nom du langage de programmation.
* **Blockquotes**: Pour formater un texte en guillemets, commencez le texte par un signe plus grand que (>), suivi d'un espace. Exemple : > Il s'agit d'une citation en bloc.
* **URLs**: Pour inclure une URL dans votre prompt, il suffit de la coller dans le texte.

# prompt en plusieurs étapes
ChatGPT a la capacité de garder en mémoire les réponses précédentes, de répondre à des questions complémentaires ou de recevoir des instructions de l'utilisateur. Voici quelques conseils pour rendre plus cohérents les prompts impliquant plusieurs étapes : - La spécification d'un "rôle" pour ChatGPT est très efficace. - Il est souvent utile de spécifier la première sortie. - Il peut être nécessaire d'inclure des instructions explicites contre la génération d'une entrée pour l'utilisateur. - Inclure des indices permettant au modèle de suivre sa progression au cours d'un prompt à plusieurs étapes, tels que des numéros de questions, des comptes à rebours ou des indicateurs de progression.

Moins efficace
```
Posez-moi d'abord huit questions sur mes dépenses dans différentes catégories, puis produisez un budget dans un tableau de démarcation.
```
Plus efficace
```
Vous devez jouer le rôle de calculateur de budget en vous abstenant de répondre à la place de l'utilisateur. Commencez par écrire "Question 1/8 : Combien gagnez-vous par quinzaine ? Attendez une réponse. Une fois que vous avez reçu une réponse, posez une question complémentaire sur les dépenses de l'utilisateur. Une fois que les huit questions ont été posées, créez un tableau markdown avec un exemple de budget pour l'utilisateur.
```

# Mettre l'accent sur les contraintes importantes
Tout au long de mes recherches, j'ai entendu dire que la meilleure notation à utiliser pour les prompts d'ingénierie pour ChatGPT est une liste à puces, car elle souligne clairement les exigences spécifiques du prompt et facilite la compréhension et le suivi du modèle.

Le prompt de l'exemple précédent comporte des puces et décrit clairement les exigences spécifiques du prompt.

J'ai récemment découvert que l'utilisation de mots-clés tels que "NE JAMAIS RÉPÉTER" ou "ÉVITER DE RÉPÉTER" en **majuscules** permet de mettre l'accent sur les contraintes importantes qui doivent être respectées.

En d'autres termes, présentez le prompt de manière claire et efficace en utilisant une combinaison de puces, de structures de phrases et de mots-clés en majuscules pour transmettre les exigences.
