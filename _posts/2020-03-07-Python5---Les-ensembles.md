---
keywords: fastai
description: Découverte de la structure d'ensembles en Python
title: Les ensembles (set)
toc: true
badges: true
comments: false
categories: [python, ISN]
nb_path: _notebooks/2020-03-07-Python5 - Les ensembles.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2020-03-07-Python5 - Les ensembles.ipynb
-->

<div class="container" id="notebook-container">
        
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">

</div>
    {% endraw %}

    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># créer un un ensemble</span>

<span class="n">ensemble</span> <span class="o">=</span> <span class="p">{</span><span class="mi">1</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">9</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">4</span><span class="p">}</span>
<span class="n">ensemble</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Comme on peut le voir, les éléments en doubles dans <em>ensemble</em> ont été éliminés et l'ordre affiché n'est pas celui dans lequel les éléments ont été saisis.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># essayons quelque chose...</span>

<span class="n">ensemble</span><span class="p">[</span><span class="mi">3</span><span class="p">]</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>l'accès aux éléments par indice comme pour les listes n'est pas possible, cela n'a tout simpliement pas de sens.</p>
<h2 id="Conversion-list-&lt;-&gt;-set">Conversion list &lt;-&gt; set<a class="anchor-link" href="#Conversion-list-&lt;-&gt;-set"> </a></h2>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">liste</span> <span class="o">=</span> <span class="p">[</span><span class="mi">1</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">9</span><span class="p">,</span><span class="mi">5</span><span class="p">,</span><span class="mi">1</span><span class="p">,</span><span class="mi">2</span><span class="p">,</span><span class="mi">4</span><span class="p">]</span>
<span class="n">ensemble</span> <span class="o">=</span> <span class="nb">set</span><span class="p">(</span><span class="n">liste</span><span class="p">)</span>
<span class="n">ensemble</span>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ensemble</span> <span class="o">=</span> <span class="p">{</span><span class="mi">1</span><span class="p">,</span> <span class="mi">9</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">4</span><span class="p">,</span> <span class="mi">2</span><span class="p">}</span>
<span class="n">liste</span> <span class="o">=</span> <span class="nb">list</span><span class="p">(</span><span class="n">ensemble</span><span class="p">)</span>
<span class="n">liste</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="M&#233;thodes-sur-les-ensembles">M&#233;thodes sur les ensembles<a class="anchor-link" href="#M&#233;thodes-sur-les-ensembles"> </a></h2><h3 id="ajout-et-retrait-:-add-et-remove">ajout et retrait : add et remove<a class="anchor-link" href="#ajout-et-retrait-:-add-et-remove"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ensemble</span> <span class="o">=</span> <span class="p">{</span><span class="mi">1</span><span class="p">,</span> <span class="mi">9</span><span class="p">,</span> <span class="mi">5</span><span class="p">,</span> <span class="mi">4</span><span class="p">,</span> <span class="mi">2</span><span class="p">}</span>
<span class="n">ensemble</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="mi">18</span><span class="p">)</span>
<span class="n">ensemble</span><span class="o">.</span><span class="n">remove</span><span class="p">(</span><span class="mi">9</span><span class="p">)</span>
<span class="n">ensemble</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Attention de bien tester si un élément est dans l'ensemble avant la suppression car sinon...</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ensemble</span><span class="o">.</span><span class="n">remove</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>et du coup ...</p>
<h3 id="tester-si-un-&#233;l&#233;ment-est-pr&#233;sent-dans-un-ensemble-:-in">tester si un &#233;l&#233;ment est pr&#233;sent dans un ensemble : in<a class="anchor-link" href="#tester-si-un-&#233;l&#233;ment-est-pr&#233;sent-dans-un-ensemble-:-in"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="mi">3</span> <span class="ow">in</span> <span class="n">ensemble</span>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="mi">18</span> <span class="ow">in</span> <span class="n">ensemble</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Longueur-et-ensemble-vide">Longueur et ensemble vide<a class="anchor-link" href="#Longueur-et-ensemble-vide"> </a></h3>
</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># l&#39;ensemble vide est noté {} ou set()</span>
<span class="n">vide</span> <span class="o">=</span> <span class="nb">set</span><span class="p">()</span>
<span class="n">vide</span><span class="o">.</span><span class="n">add</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>
<span class="n">vide</span><span class="o">.</span><span class="n">remove</span><span class="p">(</span><span class="mi">3</span><span class="p">)</span>

<span class="c1"># Calculer le nb d&#39;éléments d&#39;un ensemble</span>
<span class="nb">len</span><span class="p">(</span><span class="n">vide</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="Application">Application<a class="anchor-link" href="#Application"> </a></h3><p>Créer une fonction <strong>ensembleCarres</strong> prenant en paramètre un entier $n$ e renvoyant un ensemble contenant les carrés des entiers de 1 à $n$</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">ensembleCarres</span><span class="p">(</span><span class="n">n</span><span class="p">):</span>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="n">ec</span> <span class="o">=</span> <span class="n">ensembleCarres</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
<span class="k">assert</span> <span class="nb">len</span><span class="p">(</span><span class="n">ec</span><span class="p">)</span><span class="o">==</span><span class="mi">10</span>
<span class="k">assert</span> <span class="mi">64</span> <span class="ow">in</span> <span class="n">ec</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<ul>
<li>Créez une liste <em>l</em> de carrés jusqu'à un million. </li>
<li>Créez un ensemble <em>s</em> de carrés jusqu'à un million. </li>
<li>Recherchez si $874466246641$ est un carré</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># YOUR CODE HERE</span>
<span class="k">raise</span> <span class="ne">NotImplementedError</span><span class="p">()</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Comparez les <strong>temps de recherche d'un même nombre</strong> dans l'ensemble et dans la liste.</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%%time</span>
<span class="k">assert</span> <span class="mi">874466246641</span> <span class="ow">in</span> <span class="n">s</span>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="o">%%time</span>
<span class="k">assert</span> <span class="mi">874466246641</span> <span class="ow">in</span> <span class="n">l</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h3 id="quelques-autres-m&#233;thodes-sur-les-set">quelques autres m&#233;thodes sur les set<a class="anchor-link" href="#quelques-autres-m&#233;thodes-sur-les-set"> </a></h3>
<pre><code>s.isdisjoint(s2)
s.issubset(s2)
s.issuperset(s2)
s &lt;= s2 : inclusion (pareil avec s &gt;= s2).
s &lt; s2 : inclusion stricte (pareil avec s &gt;= s2).
set.union(s1, s2, s3) : renvoie la réunion de plusieurs sets.
set.intersection(s1, s2, s3) : renvoie l'intersection de plusieurs sets

</code></pre>
<h2 id="Exercice">Exercice<a class="anchor-link" href="#Exercice"> </a></h2><p>Créer une fonction <strong>ensembleCubes</strong> prenant en paramètre un entier $n$ e renvoyant un ensemble contenant les cubes des entiers de 1 à $n$</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">def</span> <span class="nf">ensembleCubes</span><span class="p">(</span><span class="n">n</span><span class="p">):</span>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="k">assert</span> <span class="mi">27</span> <span class="ow">in</span> <span class="n">ensembleCubes</span><span class="p">(</span><span class="mi">10</span><span class="p">)</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>En déduire en une ligne de python combien de nombres entre 1 et 100 sont à la fois des carrés et des cubes</p>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Tapez votre ligne dans la cellule ci-dessous</span>
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
<div class=" highlight hl-ipython3"><pre><span></span><span class="c1"># Attention, pas plus d&#39;une ligne de Python !!</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

</div>
 
