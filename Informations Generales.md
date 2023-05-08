# limitations de la taille des prompts
Il n'y a pas de limite claire. La longueur courante d'un prompt est inférieure à 256 tokens, mais elle peut être plus élevée, même jusqu'à 1024 tokens. (J'ai également vu un post d'OpenAI indiquant 2000 mots maximum dans un prompt.) Les longs prompts peuvent être difficiles à comprendre pour le modèle et peuvent même générer une réponse inexacte. MAIS, lorsque vous présentez les données dans le prompt de manière très structurée, vous réduisez également le risque que le modèle ne comprenne pas ou génère des réponses indésirables. Règle de base : "Moins, c'est mieux !"

## Tokens
Les modèles de la technologie GPT traitent les textes en utilisant des tokens, qui sont des séquences de caractères courantes dans les textes. Les modèles comprennent les relations statistiques entre ces tokens et excellent dans la production du token suivant dans une séquence de tokens. En étudiant la documentation de l'API GPT, je suis tombé sur un outil intéressant fourni par OpenAI appelé Tokenizer (https://platform.openai.com/tokenizer). Vous pouvez utiliser cet outil pour comprendre comment un morceau de texte serait tokenisé par l'API, et voir le nombre total de tokens dans ce morceau de texte. Il vous indique également les identifiants des jetons.

**Ce qu'il faut noter:**
* De nombreux mots correspondent à un seul jeton, mais d'autres non : indivisible.
* Les caractères Unicode tels que les emojis peuvent être divisés en plusieurs jetons contenant les octets sous-jacents : 🤚🏾
* Une règle empirique utile est qu'un jeton correspond généralement à environ 4 caractères de texte pour un texte anglais courant. Cela correspond à environ ¾ d'un mot (donc 100 tokens ~= 75 mots). Si nous prenons 1024 jetons comme maximum (sur la base des commentaires que j'ai trouvés dans certaines notes de l'API), cela se traduirait approximativement par 768 mots.

Nous avons déjà vu des exemples où l'on utilise un prompt pour donner des instructions au modèle et où l'on soumet les données au prompt suivant pour traitement. Nous savons également que le modèle "se souvient" de l'ensemble du fil de discussion. Cela m'amène à penser que nous pouvons diviser de grandes quantités de données en blocs inférieurs à 1024 tokens / environ 768 mots. (L'une de mes prochaines expériences consistera à voir si / comment je peux faire en sorte que le modèle traite une transcription de plus de 5 000 mots et en extraie toutes les actions à entreprendre).

