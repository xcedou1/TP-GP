# MATH 60210 : Devoir #1

**Professeur :** Anthony Sanford  
**Date limite :** 6 novembre 2024 à 23 h 55 sur ZoneCours  

## Instructions
Pour ce travail, vous devez travailler en groupes de trois. Je ne m’occuperai pas de la création des groupes. Il est de votre responsabilité de trouver des membres d’équipe pour votre devoir. Si vous avez des difficultés à trouver une équipe, vous pouvez me contacter par courriel et j’essaierai de vous mettre en contact avec d’autres personnes de la classe. Ce devoir comprend deux éléments à soumettre : 1) votre rédaction et 2) votre code. Le fait de ne pas soumettre l’un de ces deux éléments sera considéré comme une soumission incomplète. Votre code doit être écrit en Python. Votre code doit fonctionner de manière fluide et être clairement annoté. Si vous avez utilisé des ressources en dehors de ce qui est assigné pour ce cours, vous devez donner le crédit de la source. Par exemple, si vous avez recherché du code sur Google et utilisé ce que vous avez trouvé, indiquez la source. Sinon, vous trichez. Votre rédaction a comme objectif d’analyser, de discuter et d’interpréter vos résultats. Soumettre simplement un tableau sans en discuter clairement ne constitue pas une réponse à la question. Considérez ce que je fais en classe - je présente un thème et j’en discute. Pensez à votre rédaction de la même manière. Vous interprétez vos résultats pour quelqu’un qui lit votre rapport. Veuillez noter que les règles de HEC Montréal concernant le plagiat s’appliquent à la fois à vos réponses écrites et à votre code informatique.

Il y a 4 questions en plusieurs parties, les points pour chaque question/partie sont indiqués ci-dessous. Pour chaque partie, il y a quatre notes possibles :

- **E :** C’est la note si vous n’écrivez littéralement rien. Ça vaut 0 %.
- **C :** C’est la note si vous ne comprenez vraiment pas ce que vous faites... mais que vous avez écrit quelque chose. Ça vaut 50%.
- **B :** C’est la note si vous avez obtenu la réponse en grande partie correcte. Ça vaut 80%. Ce sera probablement la note la plus courante.
- **A :** C’est la note si votre réponse est aussi bonne (ou meilleure !) que la mienne. Ça vaut 100%.

**Remarque :** les commentaires dans votre code qui me permettent de comprendre facilement ce que vous avez essayé de faire peuvent améliorer votre note. Un code python particulièrement laid ou inélégant peut réduire votre note de 10% (par exemple, si vous faites beaucoup de copier-coller parce que vous ne savez pas comment utiliser efficacement les boucles, les fonctions ou les opérations de tableau). Vous pouvez également perdre des points si votre code ne s’exécute pas correctement ou ne fournit pas la même solution que votre réponse écrite.

---

## Problème 1 [10 Pts]

Cette question examine votre capacité de suivre des instructions. Si vous suivez les instructions pour ce travail, vous recevrez un crédit complet pour cette question.

1. Listez les noms de votre groupe **[2 pts]**
2. Tapez vos réponses (ce qui signifie que vous n’avez pas remis votre devoir écrit à la main) **[2 pts]**
3. Formatez votre devoir sous la forme d’un rapport écrit, et non d’un simple code que vous soumettez (y compris le formatage et l’étiquetage appropriés des tableaux et des graphiques). **[2 pts]**
4. Fournissez le code Python pour vos réponses **[2 pt]**
5. Votre code Python fonctionne tout seul et fournit les réponses que vous avez soumises dans votre texte. **[2 pts]**

---

## Problème 2 [35 Pts] : Value-at-Risk

Pour cette question, nous allons examiner certaines données du monde réel et calculer certaines mesures de risque. Pour commencer, obtenez des données de rendement pour le rendement du marché pondéré en fonction de la valeur, avec des distributions de dividendes, ainsi que des actions de votre choix commençant toutes par la première lettre du nom des membres de votre équipe. Par exemple, si vous avez une équipe dont les membres sont Émilie, John et Jack, vous devez obtenir des données pour trois actions dont les tickers commencent par E, J et J. Vos données doivent être quotidiennes et s’étendre du 2 décembre 2013 au 2 décembre 2022. Votre meilleure source pour ces données sera WRDS, mais vous devrez y avoir accès, ce qui peut prendre quelques jours. Répondez aux questions suivantes :

1. Fournissez des statistiques descriptives et des graphiques de séries temporelles pour vos données. Veillez à étiqueter correctement vos graphiques et discutez des résultats (tant les statistiques descriptives que les graphiques). **[5 pts]**

2. Écrivez une fonction qui se compose de deux entrées : 
   - Un objet de type tableau (array) 1-D de données de retour.
   - Une valeur réelle $\alpha$ qui est délimitée par zéro et un et qui sera utilisée pour estimer la $VaR_\alpha$ et la $ES_\alpha$ du tableau (array) 1-D.  
   Obtenez quelques résultats de votre fonction et fournissez leurs interprétations. **[5 pts]**

3. Écrivez une fonction qui calculera la VaR pour les valeurs ajustées par OLS en supposant des erreurs normales iid : $\epsilon_t \sim i.i.d. \ \mathcal{N}(0, \hat{\sigma}_{OLS})$. Assurez-vous que votre fonction accepte un objet de type `RegressionResults` et une valeur réelle $p$ qui est délimitée par zéro et un. Obtenez quelques résultats de votre fonction et fournissez leurs interprétations. **[5 pts]**

4. Calculez la VaR comme vous l’avez fait dans la partie (c), mais cette fois, nous allons faire l’hypothèse que les erreurs de régression sont définies comme :  

$$
\sigma_t^2 = \frac{\hat{\sigma}_{OLS}^2}{2} + \frac{\sigma_{t-1}^2}{2} \quad \text{and} \quad \sigma_0^2 = \hat{\sigma}_{OLS}^2.
$$  

Interprétez ce que vous trouvez. De quel type de modèle s’agit-il ? En quoi les résultats sont-ils différents de ceux que vous avez trouvés dans la partie (c) ? **[10 pts]**


5. Écrivez une fonction qui vous permettra de tester l’hypothèse nulle selon laquelle la valeur à risque a un taux de couverture $p$ (notez que $p$ doit être délimité par zéro et un) pour le tableau (array) de retour. Vous pouvez utiliser la formule pour $s_1$ dans les slides du cours 2 pour la statistique de test et fournir les interprétations. **[5 pts]**

---

## Problème 3 [35 Pts] : Simulations

Pour cette question, afin d’obtenir des crédits, vous devrez 1) écrire les fonctions et 2) interpréter les résultats obtenus à partir des fonctions que vous avez écrites. Assurez-vous de fournir le contexte de votre interprétation du résultat : écrire simplement "J’ai obtenu une réponse de 1.21029" ne vous donnera aucun crédit pour votre interprétation. Vous devez me dire ce que le résultat signifie dans le contexte de ce dont nous discutons dans ce cours.

1. **Écrivez une fonction qui accepte** :
   - un objet de type `BitGenerator`, `BG`
   - un entier positif `degrees`
   
   et retourne un tableau (array) 1-D de 200 tirages i.i.d. d’une distribution student-t avec `degrees` degrees of freedom.  
   **[10 pts]**

2. **Écrivez une fonction qui accepte** :
   - un `BitGenerator` `bg`
   - un tableau 1-D `a`
   - un booléen `r`
   
   et retourne un tableau (array) 1-D de la même taille que `a` qui contient des valeurs tirées aléatoirement de `a`. Ces valeurs sont tirées au hasard avec remplacement si `replace = True` et sinon sont tirées sans remplacement (c’est-à-dire qu’elles sont "shuffled").  
   **[5 pts]**

3. **Écrivez une fonction qui accepte un tableau (array) 1-D `s` et produit un graphique de probabilité** comparant ses valeurs à une distribution $\mathcal{N}(0, 1)$.  
   **[5 pts]**

4. **Écrivez une fonction qui accepte** :
   - un `BitGenerator` `bg`
   - un tableau (array) 1-D de valeurs réelles `a`
   - un entier positif `T`
   
   et ensuite :
   - bootstrap (échantillons avec remplacement) de `a`
   - calcule la statistique du test de Kolmogorov-Smirnov pour l’hypothèse $H_0$ que les valeurs bootstrapped suivent une distribution $\mathcal{N}(0, 1)$.
   - répète les deux étapes précédentes `T` fois.
   
   La fonction renvoie alors une valeur scalaire `p`, avec $0 \leq p \leq 1$, représentant la fraction des `T` simulations où nous rejetons $H_0$ au niveau de signification de 5 %.  
   **[5 pts]**

5. **Expliquez brièvement pour chacun des éléments suivants** :
   - Que vous disent les résultats de la partie (d) sur la taille et la puissance du test KS ?
   - Vos résultats de la partie (d) sont-ils cohérents avec vos résultats de la partie (c) ?  
   **[10 pts]**

---

## Problème 4 [20 Pts] : Combinaison des simulations et de la valeur à risque

Nous allons maintenant combiner ce que nous avons fait dans les questions 2 et 3.

1. **Écrivez une fonction qui calculera une VaR bootstrapée en utilisant 10 000 tirages**. Interprétez la valeur VaR obtenue.  
   **[5 pts]**

2. **Faites un graphique des résultats de la partie (a) et discutez de ce que vous trouvez**.  
   **[5 pts]**

3. **Quel est l’intervalle de confiance à 95 % de votre VaR ?**  
   **[5 pts]**

4. **Comparez les résultats de cette question à ceux de la question 2. Sont-ils les mêmes ? Pourquoi ou pourquoi pas ?**  
   **[5 pts]**
