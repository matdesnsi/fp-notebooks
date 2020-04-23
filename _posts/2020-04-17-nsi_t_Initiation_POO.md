---
keywords: fastai
description: Cours NSI Terminale - Thème 1.
title: Initiation à la Programmation Orientée Objet
toc: true 
badges: true
comments: false
categories: [python, NSI, Terminale, Structure_donnees, POO, TP]
nb_path: _notebooks/2020-04-17-nsi_t_Initiation_POO.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2020-04-17-nsi_t_Initiation_POO.ipynb
-->

<div class="container" id="notebook-container">
        
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Introduction">Introduction<a class="anchor-link" href="#Introduction"> </a></h2><p>Objets et POO sont au centre de la manière Python fonctionne. Vous n'êtes pas obligé d'utiliser la POO dans vos programmes - mais comprendre le concept est essentiel pour devenir plus qu'un débutant. Entre autres raisons parce que vous aurez besoin d'utiliser les classes et objets fournis par la librairie standard.</p>
<p>En effet en manipulant les tableaux en python, vous avez certainement remarqué qu'il y a deux syntaxes pour appeler des fonctions :</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">tableau</span> <span class="o">=</span> <span class="p">[</span><span class="mi">1</span><span class="p">,</span> <span class="mi">3</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">8</span><span class="p">]</span>
<span class="n">taille</span> <span class="o">=</span> <span class="nb">len</span><span class="p">(</span><span class="n">tableau</span><span class="p">)</span>
<span class="n">tableau</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="mi">11</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<ul>
<li>le calcul de la longueur du tableau se fait par l'appel à la fonction <code>len()</code> avec une syntaxe identique aux foncitons que vous avez l'habitude d'écrire.</li>
<li>l'ajout d'un élément dans le tableau est un peu différent car la fonction <code>append</code> semble provenir du tableau lui même : dans ce cas, on ne parle pas de fonciton mais de <strong>méthode</strong> associée à l'<strong>objet</strong> tableau.</li>
</ul>
<p>Un objet est une structure de donnée qui intègre des variables (que l'on nomme <strong>propriétés</strong>) et des fonctions (que l'on nomme <strong>méthodes</strong>). Nous allons voir l'intérêt de cette approche, omniprésente dans Python, en particulier lorsqu'on développe des interfaces graphiques, mais avant quelques petits repères historiques et éléments de contexte</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Petit-historique">Petit historique<a class="anchor-link" href="#Petit-historique"> </a></h3><p>La programmation en tant que telle est une matière relativement récente. Etonnament la programmation orientée objet remonte aussi loin que les années 1960. <em>Simula</em> est considéré comme le premier langage de programmation orienté objet.</p>
<p>Les années 1970 voient les principes de la programmation par objet se développent et prennent forme au travers notamment du langage <em>Smalltalk</em></p>
<p>À partir des années 1980, commence l'effervescence des langages à objets : <em>Objective C</em> (début des années 1980, utilisé sur les plateformes Mac et iOS), <em>C++</em> (C with classes) en 1983 sont les plus célèbres.</p>
<p>Les années 1990 voient l'âge d'or de l'extension de la programmation par objet dans les différents secteurs du développement logiciel, notemment grâce à l'émergence des systèmes d'exploitation basés sur une interface graphique (MacOS, Linux, Windows) qui font appel abondamment aux principes de la POO.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Programmation-proc&#233;durale">Programmation proc&#233;durale<a class="anchor-link" href="#Programmation-proc&#233;durale"> </a></h3><p>La programmation procédurale est celle que vous avez utilisé jusqu'à maintenant : cela consiste à diviser votre programme en blocs réutilisables appelés fonctions.</p>
<p>Vous essayez autant que possible de garder votre code en blocs modulaires, en décidant de manière logique quel bloc est appelé. Cela demande moins d’effort pour visualiser ce que votre programme fait. Cela rend plus facile la maintenance de votre code – vous pouvez voir ce que fait une portion de code. Le fait d’améliorer une fonction (qui est réutilisée) peut améliorer la performance à plusieurs endroits dans votre programme.</p>
<p>Vous avez des variables, qui contiennent vos données, et des fonctions. Vous passez vos variables à vos fonctions – qui agissent sur elles et peut-être les modifient. L'interaction entre les variables et les fonctions n'est pas toujours simple à gérer : les variables locales, globales, les effets de bords que provoquent certaines fonctions qui modifient des variables globales sont souvent source de bugs difficiles à déceler.</p>
<p>On touche ici aux limites de la programmation procédurale, lorsque le nombre de fonctions et de variables devient important.</p>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Cr&#233;ation-d'une-classe">Cr&#233;ation d'une classe<a class="anchor-link" href="#Cr&#233;ation-d'une-classe"> </a></h2><p>Nous allons voir un premier exemple simple basé sur la notion de <em>pile</em> vue dans une séquence précédente.</p>
<p>Une pile possède un comportement différent d'un tableau. On a utilisé un tableau pour simuler le comportement d'une pile mais faisant cela, on peut être tenté d'utiliser des fonctionnalités du tableau qui ne sont pas possibles avec une vraie pile comme accéder au dernier élément de la pile en faisant pile[0].</p>
<p>Pour y remédier nous allons créer un objet <em>Pile</em> qui se comportera exactement comme on le souhaite. Un objet se définit dans une <strong>classe</strong> qui va nous permettre de définir les <strong>propriétés</strong> et les <strong>méthodes</strong> que l'on souhaite intégrer à notre objet <em>Pile</em>.</p>
<p><img src="/images/copied_from_nb/classePile.png" alt="classe Pile"></p>
<p>Notre classe <em>Pile</em> va nous permettre de définir le modèle de l'objet que l'on souhaite créer. Ce modèle possèdera</p>
<ul>
<li>2 propriétés (variables intégrées à l'objet)<ul>
<li>longueur : la longueur de la pile</li>
<li>sommet : la valeur du sommet de la pile</li>
</ul>
</li>
<li>2 méthodes (fonctions agissant sur cet objet)<ul>
<li>empile(v) : empile la valeur <code>v</code> sur le sommet de la pile</li>
<li>depile() : sort une valeur de la pile et la renvoie.</li>
</ul>
</li>
</ul>
<p>Avec ces caractéristiques nous avons donc défini le prototype de notre pile.</p>
<p>Voyons en pratique comment cela se passe.</p>
<h3 id="D&#233;finition-de-la-classe">D&#233;finition de la classe<a class="anchor-link" href="#D&#233;finition-de-la-classe"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Définir une classe - pour le moment vide</span>
<span class="k">class</span> <span class="nc">Pile</span><span class="p">():</span>
    <span class="k">pass</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Pour le moment, on a créé une classe <strong>Pile</strong>.</p>
<p>On peut voir la classe comme le modèle de fabrication de l'objet. Ce n'est pas un objet réel, juste une manière de décrire comment il est constitué et comment il se comporte.</p>
<p>Une classe seule ne sert à rien. C'est un peu comme voir le nouveau modèle du smartphone de vos rèves sur un site de commerce en ligne : Vous voyez à quoi il ressemble, ses caractéristiques, son prix, ses fonctionnalités... mais vous ne le possédez pas !</p>
<p>Vous allez donc craquer et passer la commande. Quelques jours plus tard, vous allez posséder l'<strong>objet</strong> réel, le tenir dans vos mains, le manipuler. Vous avez créé ce qu'on appelle une <strong>instance</strong> de la classe.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Créer une instance de l&#39;objet Pile</span>
<span class="n">ma_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="mi">2</span>
<span class="n">autre_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Vous avez convaincu quelques uns de vos camarades qui ont aussi commandé le même modèle de smartphone. Ils vont aussi 
posséder leur propre instance. Ces smartphones fonctionneront de la même manière que le votre car fabriqué à partir des mêmes plans, mais ne possèderont pas les mêmes données : vos photos ou vos apps sont propres à votre instance de votre téléphone et n'apparaîtront pas sur celles de vos amis.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ma_pile</span><span class="o">.</span><span class="n">taille</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">autre_pile</span><span class="o">.</span><span class="n">taille</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Nous avons créé deux instances de la classe <em>Pile</em> : <code>ma_pile</code> et <code>autre_pile</code>.
<code>ma_pile</code> possède à présent deux propriétés : <em>longueur</em> et <em>sommet</em>. Ces propriétés n'existent pas sur <code>aure_pile</code> car l'initialisation de ces propriétés est faite en dehors de la classe, ce qui n'est pas une bonne chose : nous voulons que toutes nos piles soient fabriquées sur le même modèle et donc initialiser les propriétés à l'intérieur de la classe.</p>
<p>Voici comment procéder :</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">class</span> <span class="nc">Pile</span><span class="p">():</span>
    <span class="sd">&quot;&quot;&quot;Implémentation basique d&#39;une pile&quot;&quot;&quot;</span>
    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="sd">&quot;&quot;&quot;Initialisation de l&#39;instance&quot;&quot;&quot;</span>
        
        <span class="c1"># Initialisation des propriétés</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="kc">None</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Pour initialiser les propriétés, nous avons créé une méthode spéciale à l'intérieur de la classe : la méthode <strong><em><strong>init</strong>()</em></strong>. Le nom de cette méthode lancée automatiquement à la création de chaque instance est imposé par Python et ne peut être changé. Attention aux 2 __ à suivre.</p>
<p>Le mot clé <strong>self</strong> désigne une instance de la classe - imaginez le remplacer par <code>ma_pile</code> ou <code>autre_pile</code>. Puisqu'au moment de concevoir ma classe, ces instances n'existent pas encore, le mot <strong>self</strong> a été introduit. Il est important de ne pas oublier le <strong>self</strong> car sinon <em>longueur</em> et <em>sommet</em> seront des variables locales à la fonction <strong><strong>init</strong>()</strong> ce qui n'est pas du tout le but recherché ici !</p>
<p>Recréons à présent des instances de <em>Pile</em> et commençons à saisir des données :</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ma_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>
<span class="n">autre_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>

<span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span> <span class="o">=</span> <span class="mi">1</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="mi">2</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">autre_pile</span><span class="o">.</span><span class="n">longueur</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Tout fonctionne comme prévu : mes deux instances possèdent les mêmes propriétés mais chacune possède ses valeurs qui lui sont propres.</p>
<p>Il est temps de définir nos méthodes. Commençons pas <strong>empile</strong>. 
La définition d'une méthode est similaire à la définition d'une fonction à deux détails près</p>
<ul>
<li>les méthodes sont définies <strong>à l'intérieur d'une classe</strong></li>
<li>le premier paramètre d'une méthode est <strong>toujours</strong> <strong><em>self</em></strong></li>
</ul>
<p>Pour empiler des valeurs dans ma pile je vais avoir besoin d'une structure qui mémorise les données de ma pile. Je vais donc créer une propriété <em>cachée</em> <strong>__reste</strong> qui contiendra toutes les valeurs de ma pile autre que le sommet. Les 2 __ sont une convention de nommage et signifie que la propriété ou la méthode n'a pas vocation à être appelée à l'extérieur de la définition de la classe, d'où la qualification de <em>cachée</em>.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">class</span> <span class="nc">Pile</span><span class="p">():</span>
    <span class="sd">&quot;&quot;&quot;Implémentation basique d&#39;une pile&quot;&quot;&quot;</span>
    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="sd">&quot;&quot;&quot;Initialisation de l&#39;instance&quot;&quot;&quot;</span>
        
        <span class="c1"># Initialisation des propriétés publiques</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="kc">None</span> <span class="c1"># None signifie que la pile est vide</span>
        
        <span class="c1"># Initialisation du reste de la pile</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">__reste</span> <span class="o">=</span> <span class="p">[]</span>
    
    <span class="k">def</span> <span class="nf">empile</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">valeur</span><span class="p">):</span>
        <span class="sd">&quot;&quot;&quot;empile la valeur passée en paramètre&quot;&quot;&quot;</span>
        
        <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
            <span class="c1"># Le sommet de la pile passe dans le reste</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">__reste</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">sommet</span><span class="p">)</span>
        <span class="c1"># le nouveau sommet est la valeur qu&#39;on empile</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="n">valeur</span>
        <span class="c1"># La longueur de la pile augmente de 1</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">+=</span> <span class="mi">1</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ma_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">empile</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">empile</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="nb">print</span><span class="p">(</span><span class="n">ma_pile</span><span class="o">.</span><span class="n">sommet</span><span class="p">)</span>
<span class="nb">print</span><span class="p">(</span><span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>En lisant la définition de la méthode <strong>empile</strong>, vous serez attentif aux points suivants :</p>
<ul>
<li>le premier paramètre est <strong>self</strong>, <em>valeur</em> arrive en second</li>
<li>lorsqu'on invoque la méthode <strong>empile</strong>, on ne passe pas <strong>self</strong>, on passe juste <em>valeur</em>.</li>
<li>à chaque fois qu'on fait appel à une propriété, on utilise le préfixe <strong>self.</strong></li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="A-vous-de-jouer">A vous de jouer<a class="anchor-link" href="#A-vous-de-jouer"> </a></h2><p>L'implémentation de notre pile n'est pas terminée. Vous allez devoir à présent implémenter la méthode <strong>depile()</strong>. Celle-ci ne prend pas de paramètres (a part bien sûr <strong>self</strong> que vous n'oublierez pas !) et renvoie la valeur qui a été sorti de la pile. 
Vous serez attentif</p>
<ul>
<li>à modifier la propriété longueur</li>
<li>à ne pas provoquer d'erreur si il n'y a rien dans la pile. Dans ce cas, vous renverrez <strong>None</strong>.</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">class</span> <span class="nc">Pile</span><span class="p">():</span>
    <span class="sd">&quot;&quot;&quot;Implémentation basique d&#39;une pile&quot;&quot;&quot;</span>
    <span class="k">def</span> <span class="fm">__init__</span><span class="p">(</span><span class="bp">self</span><span class="p">):</span>
        <span class="sd">&quot;&quot;&quot;Initialisation de l&#39;instance&quot;&quot;&quot;</span>
        
        <span class="c1"># Initialisation des propriétés publiques</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">=</span> <span class="mi">0</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="kc">None</span> <span class="c1"># None signifie que la pile est vide</span>
        
        <span class="c1"># Initialisation du reste de la pile</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">__reste</span> <span class="o">=</span> <span class="p">[]</span>
    
    <span class="k">def</span> <span class="nf">empile</span><span class="p">(</span><span class="bp">self</span><span class="p">,</span> <span class="n">valeur</span><span class="p">):</span>
        <span class="sd">&quot;&quot;&quot;empile la valeur passée en paramètre&quot;&quot;&quot;</span>
        
        <span class="k">if</span> <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">&gt;</span> <span class="mi">0</span><span class="p">:</span>
            <span class="c1"># Le sommet de la pile passe dans le reste</span>
            <span class="bp">self</span><span class="o">.</span><span class="n">__reste</span><span class="o">.</span><span class="n">append</span><span class="p">(</span><span class="bp">self</span><span class="o">.</span><span class="n">sommet</span><span class="p">)</span>
        <span class="c1"># le nouveau sommet est la valeur qu&#39;on empile</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">sommet</span> <span class="o">=</span> <span class="n">valeur</span>
        <span class="c1"># La longueur de la pile augmente de 1</span>
        <span class="bp">self</span><span class="o">.</span><span class="n">longueur</span> <span class="o">+=</span> <span class="mi">1</span>
        
    <span class="c1"># YOUR CODE HERE</span>
    <span class="k">raise</span> <span class="ne">NotImplementedError</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Testez votre classe dans cette cellule</span>
<span class="n">ma_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">empile</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Vérification du fonctionnement de la classe Pile</span>
<span class="n">ma_pile</span> <span class="o">=</span> <span class="n">Pile</span><span class="p">()</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">empile</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
<span class="n">ma_pile</span><span class="o">.</span><span class="n">empile</span><span class="p">(</span><span class="mi">5</span><span class="p">)</span>
<span class="k">assert</span> <span class="n">ma_pile</span><span class="o">.</span><span class="n">sommet</span> <span class="o">==</span> <span class="mi">5</span>
<span class="k">assert</span> <span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span> <span class="o">==</span> <span class="mi">2</span>
<span class="k">assert</span> <span class="n">ma_pile</span><span class="o">.</span><span class="n">depile</span><span class="p">()</span> <span class="o">==</span> <span class="mi">5</span>
<span class="k">assert</span> <span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span> <span class="o">==</span> <span class="mi">1</span>
<span class="k">assert</span> <span class="n">ma_pile</span><span class="o">.</span><span class="n">depile</span><span class="p">()</span> <span class="o">==</span> <span class="mi">3</span>
<span class="k">assert</span> <span class="n">ma_pile</span><span class="o">.</span><span class="n">longueur</span> <span class="o">==</span> <span class="mi">0</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

</div>
 
