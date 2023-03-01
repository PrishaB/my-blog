---
keywords: fastai
description: Documentation/Analysis
title: Documentation/Analysis
toc: true 
badges: true
comments: true
categories: [jupyter]
image: 
nb_path: _notebooks/2022-09-05-documentanalysis.ipynb
layout: notebook
---

<!--
#################################################
### THIS FILE WAS AUTOGENERATED! DO NOT EDIT! ###
#################################################
# file to edit: _notebooks/2022-09-05-documentanalysis.ipynb
-->

<div class="container" id="notebook-container">
        
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Class</p>
<ul>
<li>basic building block</li>
<li>must be given keyword "class" in java (at the top)<ul>
<li>followed by class name</li>
<li>followed by methods and variables</li>
</ul>
</li>
<li>class declaration includes:<ul>
<li>Modifiers: A class can be public or has default access.</li>
<li>class keyword: The class keyword is used to create a class.</li>
<li>Class name: The name must begin with an initial letter (capitalized by convention).</li>
<li>Superclass (if any): The name of the class's parent (superclass), if any, preceded by the keyword extends. A class can only extend (subclass) one parent.</li>
<li>Interfaces (if any): A comma-separated list of interfaces implemented by the class, if any, preceded by the keyword implements. A class can implement more than one interface.</li>
<li>Body: The class body surrounded by braces, { }.</li>
</ul>
</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-java"><pre><span></span><span class="c1">//to create a class</span>
<span class="kd">public</span> <span class="kd">class</span> <span class="nc">Main</span> <span class="p">{</span>
    <span class="kt">int</span> <span class="n">x</span> <span class="o">=</span> <span class="mi">5</span><span class="p">;</span>
  <span class="p">}</span>
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
<div class=" highlight hl-java"><pre><span></span><span class="c1">//multiple classes</span>
<span class="kd">class</span> <span class="nc">Second</span> <span class="p">{</span>
    <span class="kd">public</span> <span class="kd">static</span> <span class="kt">void</span> <span class="nf">main</span><span class="p">(</span><span class="n">String</span><span class="o">[]</span> <span class="n">args</span><span class="p">)</span> <span class="p">{</span>
      <span class="n">Main</span> <span class="n">myObj</span> <span class="o">=</span> <span class="k">new</span> <span class="n">Main</span><span class="p">();</span>
      <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="n">myObj</span><span class="p">.</span><span class="na">x</span><span class="p">);</span>
    <span class="p">}</span>
  <span class="p">}</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Instance of a Object</p>
<ul>
<li>non-static variables defined outside any method, constructor, block, etc.</li>
<li>has a separate copy or instance</li>
<li>belongs to a class</li>
<li>instance variables are in the class but outside methods</li>
<li>have different defaults that are later specified</li>
<li>can only be used when an object is made</li>
<li>is destroyed with the object it's assoc. with</li>
<li>not necessary to be initialized</li>
<li>accessible in the same class that declares them</li>
<li>cannot be declared static, abstract, etc.<ul>
<li>only final and transient</li>
<li>can be any fof the four java modifiers: private, public, protected, and default</li>
</ul>
</li>
<li>include: boolean, byte, short, int, double, float, long, Object, char</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-java"><pre><span></span><span class="c1">//to create an object</span>
<span class="kd">public</span> <span class="kd">class</span> <span class="nc">Main</span> <span class="p">{</span>
  <span class="kt">int</span> <span class="n">x</span> <span class="o">=</span> <span class="mi">5</span><span class="p">;</span>

  <span class="kd">public</span> <span class="kd">static</span> <span class="kt">void</span> <span class="nf">main</span><span class="p">(</span><span class="n">String</span><span class="o">[]</span> <span class="n">args</span><span class="p">)</span> <span class="p">{</span>
    <span class="n">Main</span> <span class="n">myObj</span> <span class="o">=</span> <span class="k">new</span> <span class="n">Main</span><span class="p">();</span>
    <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="n">myObj</span><span class="p">.</span><span class="na">x</span><span class="p">);</span>
  <span class="p">}</span>
<span class="p">}</span>
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
<div class=" highlight hl-java"><pre><span></span><span class="c1">//multiple objects</span>
<span class="kd">public</span> <span class="kd">class</span> <span class="nc">Main</span> <span class="p">{</span>
    <span class="kt">int</span> <span class="n">x</span> <span class="o">=</span> <span class="mi">5</span><span class="p">;</span>
  
    <span class="kd">public</span> <span class="kd">static</span> <span class="kt">void</span> <span class="nf">main</span><span class="p">(</span><span class="n">String</span><span class="o">[]</span> <span class="n">args</span><span class="p">)</span> <span class="p">{</span>
      <span class="n">Main</span> <span class="n">myObj1</span> <span class="o">=</span> <span class="k">new</span> <span class="n">Main</span><span class="p">();</span>  <span class="c1">// Object 1</span>
      <span class="n">Main</span> <span class="n">myObj2</span> <span class="o">=</span> <span class="k">new</span> <span class="n">Main</span><span class="p">();</span>  <span class="c1">// Object 2</span>
      <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="n">myObj1</span><span class="p">.</span><span class="na">x</span><span class="p">);</span>
      <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="n">myObj2</span><span class="p">.</span><span class="na">x</span><span class="p">);</span>
    <span class="p">}</span>
  <span class="p">}</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Methods</p>
<ul>
<li>a block of code only running when called</li>
<li>used to pass data, (parameters)</li>
<li>perform actions, known also as functions</li>
<li>reuse code and define the code once to use repetitively</li>
<li>in the example below:<ul>
<li>myMethod() = name of method</li>
<li>static --&gt; means that the method belongs to the Main class and not an object of the Main class.</li>
<li>void --&gt; this method doesn't return a value</li>
</ul>
</li>
<li>to call a method, write the method's name w/ 2 parentheses and a semicolon</li>
</ul>

</div>
</div>
</div>
    {% raw %}
    
<div class="cell border-box-sizing code_cell rendered">
<div class="input">

<div class="inner_cell">
    <div class="input_area">
<div class=" highlight hl-java"><pre><span></span><span class="c1">//basic method syntax</span>
<span class="kd">public</span> <span class="kd">class</span> <span class="nc">Main</span> <span class="p">{</span>
    <span class="kd">static</span> <span class="kt">void</span> <span class="nf">myMethod</span><span class="p">()</span> <span class="p">{</span>
      <span class="c1">// code to be executed</span>
    <span class="p">}</span>
  <span class="p">}</span>
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
<div class=" highlight hl-java"><pre><span></span><span class="c1">//calling a method</span>
<span class="kd">public</span> <span class="kd">class</span> <span class="nc">Main</span> <span class="p">{</span>
    <span class="kd">static</span> <span class="kt">void</span> <span class="nf">myMethod</span><span class="p">()</span> <span class="p">{</span>
      <span class="n">System</span><span class="p">.</span><span class="na">out</span><span class="p">.</span><span class="na">println</span><span class="p">(</span><span class="s">&quot;I just got hired!&quot;</span><span class="p">);</span>
    <span class="p">}</span>
  
    <span class="kd">public</span> <span class="kd">static</span> <span class="kt">void</span> <span class="nf">main</span><span class="p">(</span><span class="n">String</span><span class="o">[]</span> <span class="n">args</span><span class="p">)</span> <span class="p">{</span>
      <span class="n">myMethod</span><span class="p">();</span>
    <span class="p">}</span>
  <span class="p">}</span>
  
  <span class="c1">// Outputs &quot;I just got hired!&quot;</span>
</pre></div>

    </div>
</div>
</div>

</div>
    {% endraw %}

<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Object Mutation</p>
<ul>
<li>faults inserted into a program that distinguish the mutant from the original program</li>
<li>certain objects are mutable vs. immutable</li>
<li>strings are immutable; will always rep. the same string<ul>
<li>but StringBuilder is mutable; it has methods to delete, insert, or replace characters</li>
</ul>
</li>
<li>mutable types seem more powerful than immutable ones<ul>
<li>mutable is safer from bugs than immutable</li>
<li>easier to understand than immutable</li>
</ul>
</li>
</ul>

</div>
</div>
</div>
<div class="cell border-box-sizing text_cell rendered"><div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<p>Console vs. GUI vs. Code.org</p>
<ul>
<li>console: console class in java provides methods to access character-based console device</li>
<li>GUI = graphical user interface; graphical representation where users interact w/ software/devices through clickable icons</li>
<li>CLI: console/text/character based representation where user types commands into a terminal to operate or navigate the software/devices</li>
<li>Code.org: thus is CLI; typing of commands, character-based</li>
</ul>

</div>
</div>
</div>
</div>
 
