---
title:  TD2 &ndash; Compléments
subtitle: Attributs et méthodes statiques
layout: tutorial
lang: fr
---

<!-- ## Créer un projet avec NetBeans

### Si vous commencez un projet de zéro

#### Configuration courte

1. Allez dans le menu Fichier > Nouveau Projet > PHP > PHP Application

2. Changez le dossier (.../public_html/PHP/TD2 par exemple) et le nom du projet
   (TD2 par exemple).

3. Appuyez sur Finish

#### Configuration complète

1. Allez dans le menu Fichier > Nouveau Projet > PHP > PHP Application

2. Changez le dossier et le nom du projet puis choisissez la version de PHP la plus
   élevée.

3. Appuyez sur Next

4. * Exécuter comme "Site Web local",

   * URL du projet : l'adresse de votre page Web sur `webinfo`, par exemple
   [http://webinfo/~votre_login/PHP/TD2/](http://webinfo/~votre_login/PHP/TD2/)

5. Appuyez sur Finish

### Si vous reprenez un projet en cours

Allez dans le menu Fichier > Nouveau Projet > PHP > PHP Application **with
existing sources**


### Fonctionnalités utiles

* Indentation automatique : Source > Format ou `Alt+Maj+F`
* Ouvrir la page Web : Éxécuter projet ou (`F6`).  
  Cela ouvre dans le navigateur l'URL donnée lors de la configuration complète.
* Activer/désactiver les commentaires : sélectionner une région de texte et
  taper `Ctrl+Shift+C` -->

## Les attributs et méthodes `static`

<!-- Compléter avec autre source de definition -->

### Attributs statiques

Un attribut d'une classe est *statique* si il ne dépend pas des instances d'une
classe mais juste de la classe. Si on pense en terme de mémoire, on peut avoir
plusieurs instances différentes d'un même objet en mémoire, mais un attribut
statique ne sera présent qu'une seule fois en mémoire.

Comme un attribut `static` ne dépend que de la classe, on l'appelle avec la
syntaxe `NomClasse::$nom_attribut` en PHP. Par contraste, les attributs classiques
s'accèdent par la syntaxe `$instance->attribut`.

De la même manière que `$this` renvoie sur l'instance courante lors de la
déclaration d'une classe (c-à-d `$instance` dans l'exemple précédent), 
`static` renvoie la classe appelée (c-à-d `NomClasse` dans l'exemple précédent). 
Il existe aussi le mot clé `self` qui renvoie au nom de la classe dans laquelle est déclarée le code.

Voyons la différence sur un exemple :

```php?start_inline=1
class Mere {
    public static function printSelfStatic(){
        // NomDeClasse::class a pour valeur
        // la chaine de caractères "NomDeClasse"
        echo "self : " . self::class . PHP_EOL;
        echo "static : " . static::class . PHP_EOL;
    }
}

class Fille extends Mere {
}

Fille::printSelfStatic();
// Affiche :
// self : Mere
// static : Fille
```

### Méthodes statiques

Une méthode non statique (appelé aussi dynamique) peut se comprendre comme une méthode qui reçoit un
argument `$this` en supplément des arguments déclarés. Du coup, une méthode
statique est juste une fonction dans laquelle on n'a pas accès à `$this`.

### Utilisation

Les attributs statiques sont utiles pour créer des attributs communs à une
classe. Par exemple, la constante `Math::Pi` en Java agit un peu comme une
variable globale à la classe `Math`.

<!-- vérifier la syntaxe de Math::Pi -->

Les attributs statiques servent aussi à coder des comportements de classe. Par
exemple, on peut attribuer un identifiant unique à chaque instance d'une classe
en stockant dans une variable statique le nombre d'instances.

<!-- Choses à faire: -->
<!-- --------------- -->
<!-- - préparer squelette class avec fonction/attribut statique/non statique  -->
<!-- -> Comment appelle-t-on la fonction/attribut dedans/dehors la classe -->

