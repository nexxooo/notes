---
tags: [W1]
title: W CM1
created: '2025-09-09T11:27:16.734Z'
modified: '2025-09-09T12:56:44.663Z'
---

# W CM1

## PRESENTATION 

- **HTML** : langage de description, à base de balise 
- **CSS** : langage de dexcription pour la mise en forme
- **JS** : langage de prog pour l'interaction 

HTML n'estpas une norme mais un standard régi par W3C 

## HTML
pour un paragraphe :
~~~
<p> pargraphe </p>
~~~
les balises marchent pas 2 ou alors elles sont orphelines
elle peut se suivre ou s'imbriquer mais il faut faire attention a l'ordre d'ouverture et de fermeture 

**HTML 5**: a apporté beacoup dont les balise sémantique pour une meilleur structure et donc un meilleur référencelent 

### Balise importante 
~~~HTML 
<header>
<nav>
<main>
<aside>
<p>
<section>
<article>
<blockquote>
<footer>
~~~

## CSS 
### syntaxe
~~~CSS
h3{
  font-style:italic;
}
~~~
### intergration
~~~HTML
<style rel ="stylesheet"
~~~
### selection d'élément 

| CSS  | HTML  |
|---|---|
|  h1{ } |rien   |
| h1.titre{ }  | mettre <h1 class ="titre"  |
| .titre{ }|tous objet avec la class titre |
| titre#01{ }| mettre <h1 id ="01"|
|h1:first-child/last { }| <body **<h1** <h1|
|section > 1 { }| <section **<p** <article <p // enfant direct |
| a:hover{ }| <a href=""... // pseudo classe (ici lorsque le curseur survole)|

 * lorsque qu'un style HTML est applioqué a un élément, il est appliqué par héritage
* les style sont appliqué dans l'ordre de la feuillle css
* si un élément se voit attribue plusieur style par des selecteur different, une priorité sur le type de selecteur s'applique 

### mise en forme du texte 
~~~CSS
font-familly:"...","..."
tet-align:
line-height:
border-radius:
background-image
background-repeat
display
border 
width
~~~
### taille 
* relatif 
  * em 
  * rem 
  * %
* absolue 
  * px 
  * inch 
  * cm 
### Flex box 
permet de distribuer l'espace entre les objet d'un conteneur pour les placer comme on le souhaite 
#### pour mettre en place 
~~~css
.container{
display: flex,
flex-direction: row/colum;
flew-wrap: wrap/ wrpa-reverse // passage a la ligne 

justify-content // distribue l'espace sur l'axe principale
align-item // dist axe secondaire
align-content // si plusieur ligne

// les enfant peuvent influencer leur propre taille et position 
flex-grown 
}
~~~


