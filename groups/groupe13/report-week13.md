## Gautam Demeulemeester

Cette semaine j'ai terminé ma feature Sokoban, j'ai ajouté des couleurs aux boites et cibles pour ajouter une regle qu'une boite ne peux etre valide que si il est sur la cible de sa couleur. 
J'ai d'abord voulu que les couleurs soient saisies dans les maps de partie mais je n'ai pas reussi a parser les maps. Je suis donc partie sur une logique d'attribution des couleurs aléatoire.
J'ai pu travailler le TDD, double dispatch, l'affichage visuel mais aussi la génération de forme géometrique avec la classe BlElement et BlCircleGeometry.

## HEDDI Abdelkader 

Pour cette semaine et cette dernière séance de C3P, je me suis concentré sur la finalisation du projet **Sokoban** et la **préparation de la soutenance**.

* **Préparation de la soutenance** : J'ai réalisé le diaporama de présentation en structurant mon discours autour de l'évolution de l'architecture du jeu. J'ai notamment préparé les slides comparant le "Design Avant" (couplage fort UI/Modèle) et le "Design Après" (introduction du Pattern Command), ainsi que les diagrammes UML explicatifs. J'ai également préparé mon passage à l'oral pour expliquer clairement mes choix techniques (TDD et l'utilisation du pattern Command).

* **Fonctionnalité implémentée** : Le "Undo" (Annuler) J'ai développé la fonctionnalité permettant au joueur d'annuler ses derniers coups.

* **Objectif** : Offrir un droit à l'erreur au joueur sans recharger le niveau.

* **Architecture** : Mise en place du Design Pattern Command. Chaque déplacement est désormais encapsulé dans un objet SkMoveCommand stocké dans un historique.

* **Méthodologie** : J'ai appliqué le TDD (Test Driven Development) pour garantir que l'annulation fonctionne parfaitement, même dans les cas complexes comme lorsqu'une caisse a été poussée (gestion via un flag boxPushed pour ramener la caisse en arrière).

Le code est disponible sur github : https://github.com/K-Boo/Myg

## Khalil BOUCHAMA
 
Cette semaine, j'ai réalisé terminé l'implémentation complète du compteur de mouvements et son intégration avec le système d'annulation (Undo) :

 j'ai :
- Implémenté la méthode de mise à jour updateMoveCountDisplay.
- Modifié la gestion des événements (manageEvent:) pour rafraîchir le compteur après chaque déplacement validé par le double dispatch.

Pour l'Intégration de l'Undo, j'ai :
- Créé le test testUndoDecrementsMoveCount pour reproduire le problème de non-décrémentation.
- Ajouté la méthode decrementMoveCount dans le MygSkGameManager.
- Modifié la méthode MygSkBoard >> undo pour déclencher la décrémentation du compteur à chaque annulation d'action, garantissant ainsi la cohérence du score affiché.

