# Guide de depouillement des contenus de manuscrits

## But du travail

Dans ce projet, vous transformerez des descriptions de manuscrits tirees de catalogues de bibliotheques en une liste structuree des textes contenus dans chaque manuscrit. Vous partirez de la table **« Contents listings for Bischoff Items »**, qui vous indique quel manuscrit examiner, dans quel catalogue il est decrit, et ou trouver la notice. Vous enregistrerez ensuite les resultats dans la table **« Manuscript Contents »**. La regle fondamentale est la suivante : **une ligne dans « Manuscript Contents » correspond a un texte, une oeuvre, ou une unite textuelle dans un manuscrit donne**. Si un manuscrit contient plusieurs items distincts, il faudra donc creer plusieurs lignes.

Il faut toujours privilegier la prudence. Les champs **« as catalogue »** servent a conserver le libelle du catalogue aussi fidelement que possible; les champs **« normalised »** ne doivent etre remplis que si l'identification est raisonnablement sure. En cas d'incertitude, il vaut mieux **laisser le champ vide** ou **poser une question**, plutot que de deviner. Le but n'est pas de reconstruire le manuscrit de maniere speculative, mais de produire des donnees fiables, explicites et reutilisables.
