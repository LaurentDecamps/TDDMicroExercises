_Voici une traduction française du readme inspiré de celui d'Emily Bache_

Racing Car Katas
=================

Imaginez qu'il s'agisse d'un code que vous avez hérité d'une ancienne base de code. Vous voulez écrire des tests unitaires pour eux, et c'est plus difficile que cela ne devrait l'être.

En résolvant ces problèmes, vous pouvez en apprendre davantage sur les principes de conception SOLID et sur la manière de remanier le code pour le rendre plus testable. 

Emily Bache a réalisé une vidéo qui explique plus en détail : https://youtu.be/ldthYMeXSoI 

Trois exercices code
----------------

Il y a 5 exercices distincts dans ce dépôt. 

Trois d'entre eux ont été séparé pour qu'il soit plus facile de se concentrer sur un à la fois : 

1. [TirePressureMonitoringSystem](https://github.com/emilybache/TirePressure-Kata) 
2. [HtmlTextConverter](https://github.com/emilybache/HtmlConverter-Kata) 
3. [TicketDispenser](https://github.com/emilybache/TurnTicket-Kata) 
4. TelemetrySystem - pas encore migré 
5. Leaderboard - pas encore migré

Instructions de l'exercice
---------------------
Pour chaque exercice, vous devez identifier quels principes SOLID ne sont pas respectés par le code. Il n'y a qu'une seule classe pour laquelle vous souhaitez écrire des tests pour le moment. Dans un premier temps, essayez de mettre en place une sorte de test avant de modifier la classe. Si les tests sont difficiles à écrire, est-ce à cause des problèmes liés aux principes SOLID ? 

Lorsque vous disposez d'une sorte de test sur lequel vous pouvez vous appuyer, remaniez le code et rendez-le testable. Veillez, lors de la refonte, à ne pas altérer la fonctionnalité ou à ne pas modifier les interfaces sur lesquelles d'autres codes clients peuvent s'appuyer. (Imaginez qu'il y ait du code client dans un autre dépôt que vous ne pouvez pas voir pour l'instant). 
Ajoutez des tests supplémentaires pour couvrir la fonctionnalité de la classe particulière que l'on vous a demandé de tester. 

Appliquez le style et le cadre de test unitaire avec lesquels vous êtes le plus à l'aise. Vous pouvez choisir d'utiliser des stubs, des mocks ou rien du tout. Dans ce cas, vous êtes libre d'utiliser l'outil de simulation que vous préférez. 

1. Exercice **TirePressureMonitoringSystem** : écrivez les tests unitaires pour la classe Alarm. La classe Alarm est conçue pour surveiller la pression des pneus et déclencher une alarme si la pression sort de la plage prévue. La classe Capteur fournie pour l'exercice imite le comportement d'un vrai capteur de pneu, fournissant des valeurs aléatoires mais réalistes.

2. **Exercice HtmlTextConverter** : écrivez les tests unitaires pour la classe HtmlTextConverter. La classe ToHtmlTextConverter est conçue pour reformater un fichier texte brut afin de l'afficher dans un navigateur.

3. **Exercice TicketDispenser** : écrivez les tests unitaires pour le TicketDispenser. La classe TicketDispenser est conçue pour être utilisée pour gérer un système de file d'attente dans un magasin. Il peut y avoir plus d'un distributeur de tickets, mais le même ticket ne doit pas être délivré à deux clients différents. 

4. **Exercice TelemetrySystem** : écrivez les tests unitaires pour la classe TelemetryDiagnosticControls. La responsabilité de la classe TelemetryDiagnosticControls est d'établir une connexion avec le serveur de télémétrie (à travers le TelemetryClient), d'envoyer une requête de diagnostic et de recevoir avec succès la réponse qui contient les informations de diagnostic. La classe TelemetryClient fournie pour l'exercice imite le comportement de la classe TelemetryClient réelle et peut répondre soit avec les informations de diagnostic, soit avec une séquence aléatoire. La classe TelemetryClient réelle se connecte et communique avec le serveur de télémétrie via tcp/ip. 

5. **Exercice du tableau de bord** : (note : cet exercice est encore en cours de développement) Ecrire les tests unitaires pour la classe Leaderboard, y compris les courses avec des voitures auto-conduites. Le Leaderboard calcule les points et les classements des conducteurs sur la base des résultats d'un certain nombre de courses. TDD avec Mock Objects : 

Principes de conception et propriétés émergentes 
------------------------------------------------

 Il s'agissait à l'origine d'un fork de [Luca Minudel's repo] (https://github.com/lucaminudel/TDDwithMockObjectsAndDesignPrinciples). Il l'utilisait pour une étude des principes de TDD et de conception. Emily Bache l'utilise comme un dépôt pour stocker des exercices utiles pour les personnes souhaitant améliorer leurs compétences avec les principes TDD et SOLID. Vous pouvez consulter son article de blog ["SOLID principles and TDD"] (http://coding-is-like-cooking.info/2012/09/solid-principles-and-tdd/) pour une lecture de fond, ou le livre d'Emily Bache ["The Coding Dojo Handbook"] (http://leanpub.com/codingdojohandbook).
 
- Lorsque vous aurez fait ces exercices vous-même, vous pourrez consulter les [solutions proposées] (https://github.com/lucaminudel/TDDwithMockObjectsAndDesignPrinciples/tree/master/TDDMicroExercises.ProposedSolution) en C#, Java, Javascript. Si vous avez fait les exercices en Python, vous pourriez être intéressé par l'article sur le blog d'Emily ["SOLID exercises in Python"](http://coding-is-like-cooking.info/2012/09/solid-exercises-in-python/). 
- Pour en savoir plus sur l'étude de Luca, consultez le [document](https://github.com/lucaminudel/TDDwithMockObjectsAndDesignPrinciples/blob/master/Paper/mockobjects_emergingproperties.pdf?raw=true) et la [présentation](https://github.com/lucaminudel/TDDwithMockObjectsAndDesignPrinciples/blob/master/Slides/TDD-SOLID.pdf?raw=true) sur le site de Luca.

## RAPPEL : Les principes SOLID

### S = Single Responsability =  Une seule responsabilité

Une classe / une fonction doit avoir une et une seule responsabilité, c'est-à-dire une seule raison de changer/d'être modifiée.

### O = Open Close = Ouvert Fermé

Une classe doit être ouvert à l'extension mais fermée à la modification. 

### L = Liskov substitution = Substitution de Liskov

Les méthodes qui utilisent une classe de base doivent pouvoir utiliser des instances de classes dérivées sans le savoir : toutes les classes dérivées doivent respecter le contrat défini par la classe de base

### I = Interface Segregation = Ségrégation d'Interface

Les clients ne doivent pas être contraints de dépendre de membres d'interface qu'ils n'utilisent pas : les interfaces qui ne servent qu'une seule portée devraient doivent être préférées aux interfaces lourdes.

### D = Dependency Inversion = Inversion de dépendance

Les classes de bas niveau et les classes de haut niveau doivent toutes deux dépendre d'abstractions : les classes de haut niveau ne doivent pas dépendre des classes de bas niveau.
