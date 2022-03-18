# Balanced strings

A string containing grouping symbols `{}[]()` is said to be balanced if every open symbol `{[(` has a matching closed symbol `]}` and the substrings before, after and between each pair of symbols is also balanced. The empty string is considered as balanced.

For example: `{[][]}({})` is balanced, while `][`, `([)]`, `{`, `{(}{}` are not.

Implement the following method:

```java
public static boolean isBalanced(String str) {
    ...
}
```

`isBalanced` returns `true` if `str` is balanced according to the rules explained above. Otherwise, it returns `false`.

Use the coverage criteria studied in classes as follows:

1. Use input space partitioning to design an initial set of inputs. Explain below the characteristics and partition blocks you identified.
2. Evaluate the statement coverage of the test cases designed in the previous step. If needed, add new test cases to increase the coverage. Describe below what you did in this step.
3. If you have in your code any predicate that uses more than two boolean operators check if the test cases written so far satisfy *Base Choice Coverage*. If needed add new test cases. Describe below how you evaluated the logic coverage and the new test cases you added.
4. Use PIT to evaluate the test suite you have so far. Describe below the mutation score and the live mutants. Add new test cases or refactor the existing ones to achieve a high mutation score.

Write below the actions you took on each step and the results you obtained.
Use the project in [tp3-balanced-strings](../code/tp3-balanced-strings) to complete this exercise.

## Answer

1. La partition est en fonction de l'argument donnée à isBalanced(). Il y a donc null et une chaîne vide. Il y a ensuite les cas simple qui fonctionne `(), [], {}` puis un cas plus complexe `({[]})` qui prends tous les charactères. Et enfin une erreur `(, [, {`.
2. J'ai ajouté un test qui prend n'importe quel charactère pour augmenter le coverage.
3. Pour le if qui vérifie la fermeture j'ai rajouté `][` qui m'a permis de trouver un bug et de le corriger. J'ai aussi rajouter `(}` pour passer dans tous les cas.
4. PIT a généré 27 mutations pour un score de 89% qui est quasiment de 100%. Les 10% manquant sont à cause du switch, avec un if pour chaque charactère le coverage aurais été de 100%.
