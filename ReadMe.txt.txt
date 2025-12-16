GLSimpleSQL – Mini Projet LST GL S5
------------------------------------

Ce projet implémente un interpréteur simplifié du langage SQL en utilisant :
- Flex pour l’analyse lexicale,
- Bison pour l’analyse syntaxique,
- C pour les actions sémantiques et l’exécution.

------------------------------------
Structure du projet
------------------------------------
/ReadMe.txt 
│
├── main.c          → Point d’entrée du programme
├── lexer.l         → Analyseur lexical Flex
├── parser.y        → Analyseur syntaxique Bison
│
├── Rapport.pdf     → Rapport complet du projet
├── Grammaire.pdf   → Grammaire formelle du langage proposée
└── readMe.txt      → Ce fichier


Les fichiers suivants sont générés automatiquement à la compilation :
    lex.yy.c
    parser.tab.c
    parser.tab.h
    a.exe / src.exe

------------------------------------
Compilation
------------------------------------

1. Générer l’analyseur lexical :
    flex lexer.l

2. Générer l’analyseur syntaxique :
    bison -d parser.y

3. Compiler l’ensemble :
    gcc lex.yy.c parser.tab.c main.c -o interpreter.exe

------------------------------------
Exécution
------------------------------------

Lancer :
    ./interpreter.exe

Saisir des commandes SQL telles que :
    Exemples de commandes supportées :

CREATE TABLE Etudiant (
    id INT,
    nom VARCHAR(50),
    age INT
);

INSERT INTO Etudiant VALUES (1, 'Diallo', 20);
INSERT INTO Etudiant (id, nom) VALUES (2, 'Sow');

SELECT * FROM Etudiant;
SELECT nom, age FROM Etudiant WHERE age > 18;

UPDATE Etudiant SET age = 21 WHERE id = 1;
UPDATE Etudiant SET nom = 'Ba', age = 22 WHERE id = 2;

DELETE FROM Etudiant WHERE age < 18;
DROP TABLE Etudiant;



------------------------------------
Fonctionnalités
------------------------------------

✔ Détection des tokens (Flex)
✔ Analyse syntaxique complète (Bison)
✔ Construction des structures de requêtes
✔ Statistiques sur les requêtes SELECT, INSERT, UPDATE
✔ Table des symboles
✔ Vérifications sémantiques :
   - table inexistante
   - champ inexistant
   - incohérence champs/valeurs
   - double création de table
✔ Messages d’erreurs clairs

------------------------------------
Auteur
------------------------------------

Nom : FATIMA ZAHRA LEGDOU , WISSAL BEGGAR .
Filière : LST GL S5
Année : 2025–2026
