---
layout: post
title:  "Renverse Moi, Si tu peux."
date:   2016-06-20 09:11:03
description: Julia Code
thumbnail: map2.jpg
categories: [pydefis,challenge,math,code]
comments: true
author: Shift Shuffle
---

<div class="alert alert-info">

  Problem <a href="https://callicode.fr/pydefis/Reverse/txt"> Here </a>
</div>

# Solution


<div tabindex="-1" id="notebook" class="border-box-sizing">
  <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="Renverse-moi-si-tu-peux">Renverse moi <em>si tu peux</em><a class="anchor-link" href="#Renverse-moi-si-tu-peux">&#182;</a></h2><h3 id="Chifrement">Chifrement<a class="anchor-link" href="#Chifrement">&#182;</a></h3>$$ Key =[ SK_0,SK_1,SK_2 ... SK_{19}] $$$$KeyA= 0 \oplus SK_0 \oplus SK_1  ...  \oplus SK_{19}$$$$nKeypos = mod(KeyA,20)$$$$chiffre = clair\oplus(SK_{nKeypos}*KeyA)$$$$KeyA= mod(KeyA+chiffre,256)$$$$nkeypos=mod(chiffre,20)$$
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">Key</span><span class="o">=</span><span class="n">rand</span><span class="p">(</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span><span class="p">,</span><span class="mi">20</span><span class="p">)</span>
<span class="n">clair</span><span class="o">=</span><span class="s">&quot;hello this is a test :)&quot;</span>
<span class="n">crypted</span><span class="o">=</span><span class="n">String</span><span class="p">[]</span>
<span class="n">decrypted</span><span class="o">=</span><span class="n">Char</span><span class="p">[]</span>
<span class="n">chiff</span><span class="o">=</span><span class="kt">Uint8</span><span class="p">[]</span>


<span class="n">KeyA</span><span class="o">=</span><span class="mi">0</span>
<span class="k">for</span> <span class="n">i</span> <span class="k">in</span> <span class="n">Key</span>
  <span class="n">KeyA</span><span class="o">$=</span><span class="n">i</span>
<span class="k">end</span>

<span class="c"># KeyA=convert(Uint8,KeyA)</span>
<span class="n">nKeypos</span><span class="o">=</span><span class="p">(</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span>


<span class="k">for</span> <span class="n">i</span> <span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">clair</span><span class="p">)</span>
  <span class="n">chiffre</span><span class="o">=</span><span class="n">clair</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">$</span><span class="n">Key</span><span class="p">[</span><span class="n">nKeypos</span><span class="p">]</span><span class="o">*</span><span class="n">KeyA</span>
  <span class="c">#crypted*=hex(chiffre)*&quot; &quot;</span>
  <span class="n">chiffre</span><span class="o">=</span><span class="nb">convert</span><span class="p">(</span><span class="kt">Uint8</span><span class="p">,</span><span class="n">chiffre</span><span class="p">)</span>
  <span class="n">push!</span><span class="p">(</span><span class="n">crypted</span><span class="p">,</span><span class="n">hex</span><span class="p">(</span><span class="n">chiffre</span><span class="p">))</span>
  <span class="n">push!</span><span class="p">(</span><span class="n">chiff</span><span class="p">,</span><span class="n">chiffre</span><span class="p">)</span>
  <span class="c">#println(hex(chiffre))</span>
  <span class="n">KeyA</span><span class="o">=</span><span class="p">(</span><span class="n">KeyA</span><span class="o">+</span><span class="n">chiffre</span><span class="p">)</span><span class="o">%</span><span class="mi">256</span>
  <span class="n">nKeypos</span><span class="o">=</span><span class="n">chiffre</span><span class="o">%</span><span class="mi">20</span><span class="o">+</span><span class="mi">1</span>
<span class="k">end</span>

<span class="n">join</span><span class="p">(</span><span class="n">crypted</span><span class="p">,</span><span class="s">&quot; &quot;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[1]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&#34;87 e1 79 dc 7b ae e6 cb 31 e 12 62 9a e6 cc 24 87 3 65 84 32 fe d5&#34;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[48]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">KeyA</span><span class="o">=</span><span class="mi">0</span>
<span class="k">for</span> <span class="n">i</span> <span class="k">in</span> <span class="n">Key</span>
  <span class="n">KeyA</span><span class="o">$=</span><span class="n">i</span>
<span class="k">end</span>

<span class="c"># KeyA=convert(Uint8,KeyA)</span>
<span class="n">nKeypos</span><span class="o">=</span><span class="p">(</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span>


<span class="k">for</span> <span class="n">i</span> <span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">clair</span><span class="p">)</span>
  <span class="n">clear</span><span class="o">=</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">$</span><span class="n">Key</span><span class="p">[</span><span class="n">nKeypos</span><span class="p">]</span><span class="o">*</span><span class="n">KeyA</span>
  <span class="c">#crypted*=hex(chiffre)*&quot; &quot;</span>
  <span class="n">clear</span><span class="o">=</span><span class="nb">convert</span><span class="p">(</span><span class="kt">Uint8</span><span class="p">,</span><span class="n">clear</span><span class="p">)</span>
  <span class="n">clear</span><span class="o">=</span><span class="n">char</span><span class="p">(</span><span class="n">clear</span><span class="p">)</span>
  <span class="n">push!</span><span class="p">(</span><span class="n">decrypted</span><span class="p">,</span><span class="n">clear</span><span class="p">)</span>
  <span class="c">#println(hex(chiffre))</span>
  <span class="n">KeyA</span><span class="o">=</span><span class="p">(</span><span class="n">KeyA</span><span class="o">+</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="o">%</span><span class="mi">256</span>
  <span class="n">nKeypos</span><span class="o">=</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">%</span><span class="mi">20</span><span class="o">+</span><span class="mi">1</span>
<span class="k">end</span>

<span class="n">join</span><span class="p">(</span><span class="n">decrypted</span><span class="p">,</span><span class="s">&quot;&quot;</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt output_prompt">Out[48]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>&#34;hello this is a test :)hello this is a test :)&#34;</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[49]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">KeyA</span><span class="o">=</span><span class="mi">0</span>
<span class="k">for</span> <span class="n">i</span> <span class="k">in</span> <span class="n">Key</span>
  <span class="n">KeyA</span><span class="o">$=</span><span class="n">i</span>
<span class="k">end</span>

<span class="c"># KeyA=convert(Uint8,KeyA)</span>
<span class="n">println</span><span class="p">(</span><span class="n">KeyA</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">Key</span><span class="p">[(</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span><span class="p">])</span>
<span class="n">println</span><span class="p">((</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">Key</span><span class="p">)</span>
<span class="c"># println(Key[(KeyA%20)+1]*KeyA)</span>
<span class="n">l</span><span class="o">=</span><span class="n">Key</span><span class="p">[(</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span><span class="p">]</span><span class="o">*</span><span class="n">KeyA</span>
<span class="c"># println(l%256)</span>
<span class="n">l</span><span class="o">=</span><span class="nb">convert</span><span class="p">(</span><span class="kt">Uint8</span><span class="p">,</span><span class="n">l</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">l</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>173
139
14
[162,104,155,118,172,1,151,4,138,233,251,250,13,139,102,37,149,93,31,196]
239
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[50]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">n</span><span class="o">=</span><span class="p">(</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span>
<span class="c"># println(n)</span>
<span class="n">nu</span><span class="o">=</span><span class="kt">Uint64</span><span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">chiff</span><span class="p">)</span>
  <span class="n">n</span><span class="o">=</span><span class="p">(</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span>
  <span class="k">if</span> <span class="n">n</span> <span class="k">in</span> <span class="n">nu</span>
<span class="c">#         println(n)</span>
      <span class="k">break</span>
  <span class="k">else</span>
  <span class="n">push!</span><span class="p">(</span><span class="n">nu</span><span class="p">,</span><span class="n">n</span><span class="p">)</span>
  <span class="k">end</span>   
<span class="k">end</span>

<span class="n">m</span><span class="o">=</span><span class="n">findin</span><span class="p">(</span><span class="n">nu</span><span class="p">,</span><span class="n">n</span><span class="p">)[</span><span class="mi">1</span><span class="p">]</span>
<span class="n">push!</span><span class="p">(</span><span class="n">nu</span><span class="p">,</span><span class="n">n</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">nu</span><span class="p">)</span>
<span class="n">nu</span><span class="o">=</span><span class="n">nu</span><span class="p">[</span><span class="n">m</span><span class="p">:</span><span class="k">end</span><span class="p">]</span>
<span class="n">println</span><span class="p">(</span><span class="n">m</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>Uint64[16,6,2,1,4,15,11,4]
5
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[91]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">n</span><span class="o">=</span><span class="p">(</span><span class="n">KeyA</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span>
<span class="n">nustop</span><span class="o">=</span><span class="kt">Uint64</span><span class="p">[]</span>
<span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">chiff</span><span class="p">)</span><span class="o">-</span><span class="mi">1</span>
  <span class="n">n</span><span class="o">=</span><span class="p">(</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">%</span><span class="mi">20</span><span class="p">)</span><span class="o">+</span><span class="mi">1</span>
  <span class="n">push!</span><span class="p">(</span><span class="n">nustop</span><span class="p">,</span><span class="n">n</span><span class="p">)</span>
<span class="k">end</span>

<span class="n">println</span><span class="p">(</span><span class="n">nustop</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>Uint64[16,6,2,1,4,15,11,4,10,15,19,19,15,11,5,17,16,4,2,13,11,15]
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="D&#233;ductions">D&#233;ductions<a class="anchor-link" href="#D&#233;ductions">&#182;</a></h2>$$chiff[m+1] \oplus clair[m+1] = KeyA*SK_{nKeypos}$$$$KeyA=mod(KeyA+chiff[m+1],256)$$$$...$$$$KeyA=mod(KeyA+chiff[m+s],256)$$$$chiff[m+s+1] \oplus clair[m+s+1] = KeyA*SK_{nKeypos}$$
</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[81]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">s</span><span class="o">=</span><span class="n">length</span><span class="p">(</span><span class="n">nu</span><span class="p">)</span>
<span class="n">possibleKeyA</span><span class="o">=</span><span class="kt">Int</span><span class="p">[]</span>
<span class="n">possibleKeyA2</span><span class="o">=</span><span class="kt">Int</span><span class="p">[]</span>
<span class="n">possibleValues</span><span class="o">=</span><span class="kt">Int</span><span class="p">[]</span>
<span class="n">f</span><span class="o">=</span><span class="p">(</span><span class="kt">Int</span> <span class="o">=&gt;</span> <span class="n">Array</span><span class="p">)[]</span>
<span class="n">f2</span><span class="o">=</span><span class="p">(</span><span class="kt">Int</span> <span class="o">=&gt;</span> <span class="n">Array</span><span class="p">)[]</span>



<span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
  <span class="n">f</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">=</span><span class="kt">Int</span><span class="p">[]</span>
<span class="k">end</span>

<span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
  <span class="n">f2</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">=</span><span class="kt">Int</span><span class="p">[]</span>
<span class="k">end</span>

<span class="k">for</span> <span class="n">j</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
  <span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
      <span class="k">if</span> <span class="p">(</span><span class="n">i</span><span class="o">*</span><span class="n">j</span><span class="p">)</span><span class="o">%</span><span class="mi">256</span><span class="o">==</span><span class="n">chiff</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="mi">1</span><span class="p">]</span><span class="o">$</span><span class="n">clair</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="mi">1</span><span class="p">]</span>
          <span class="n">push!</span><span class="p">(</span><span class="n">f</span><span class="p">[</span><span class="n">j</span><span class="p">],</span><span class="n">i</span><span class="p">)</span>
<span class="c">#             println((j,i))</span>
      <span class="k">end</span>
  <span class="k">end</span>
<span class="k">end</span>

<span class="k">for</span> <span class="n">j</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
  <span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
      <span class="k">if</span> <span class="p">(</span><span class="n">i</span><span class="o">*</span><span class="n">j</span><span class="p">)</span><span class="o">%</span><span class="mi">256</span><span class="o">==</span><span class="n">chiff</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="n">s</span><span class="p">]</span><span class="o">$</span><span class="n">clair</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="n">s</span><span class="p">]</span>
          <span class="n">push!</span><span class="p">(</span><span class="n">f2</span><span class="p">[</span><span class="n">j</span><span class="p">],</span><span class="n">i</span><span class="p">)</span>
<span class="c">#             println((j,i))</span>
      <span class="k">end</span>
  <span class="k">end</span>
<span class="k">end</span>



<span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">0</span><span class="p">:</span><span class="mi">255</span>
  <span class="k">if</span> <span class="n">f</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">!=</span><span class="p">[]</span>
      <span class="n">sKeyA</span><span class="o">=</span><span class="n">i</span>
      <span class="n">csKeyA</span><span class="o">=</span><span class="n">sKeyA</span>
      <span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="n">m</span><span class="o">+</span><span class="mi">1</span><span class="p">:</span><span class="n">m</span><span class="o">+</span><span class="n">s</span>
      <span class="n">csKeyA</span><span class="o">=</span><span class="p">(</span><span class="n">csKeyA</span><span class="o">+</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="o">%</span><span class="mi">256</span>
          <span class="k">for</span> <span class="n">value</span> <span class="k">in</span> <span class="n">f</span><span class="p">[</span><span class="n">sKeyA</span><span class="p">]</span>
              <span class="k">if</span> <span class="k">in</span><span class="p">(</span><span class="n">value</span><span class="p">,</span><span class="n">f2</span><span class="p">[</span><span class="n">csKeyA</span><span class="p">])</span>
                  <span class="n">println</span><span class="p">(</span><span class="n">sKeyA</span><span class="p">)</span>
                  <span class="n">push!</span><span class="p">(</span><span class="n">possibleKeyA</span><span class="p">,</span><span class="n">sKeyA</span><span class="p">)</span>
                  <span class="n">push!</span><span class="p">(</span><span class="n">possibleKeyA2</span><span class="p">,</span><span class="n">csKeyA</span><span class="p">)</span>
                  <span class="n">push!</span><span class="p">(</span><span class="n">possibleValues</span><span class="p">,</span><span class="n">value</span><span class="p">)</span>
                  <span class="n">println</span><span class="p">(</span><span class="n">value</span><span class="p">)</span>
              <span class="k">end</span>
          <span class="k">end</span>
      <span class="k">end</span>
  <span class="k">end</span>
<span class="k">end</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>26
35
26
163
101
118
229
118
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[82]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">println</span><span class="p">(</span><span class="n">possibleKeyA</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">possibleValues</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">possibleKeyA2</span><span class="p">)</span>

<span class="n">chiff</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="mi">1</span><span class="p">]</span><span class="o">$</span><span class="n">clair</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="mi">1</span><span class="p">]</span><span class="o">==</span><span class="p">(</span><span class="n">possibleKeyA</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">*</span><span class="n">possibleValues</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span><span class="o">%</span><span class="mi">256</span>
<span class="n">chiff</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="n">s</span><span class="p">]</span><span class="o">$</span><span class="n">clair</span><span class="p">[</span><span class="n">m</span><span class="o">+</span><span class="n">s</span><span class="p">]</span><span class="o">==</span><span class="p">(</span><span class="n">possibleKeyA2</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span><span class="o">*</span><span class="n">possibleValues</span><span class="p">[</span><span class="mi">1</span><span class="p">])</span><span class="o">%</span><span class="mi">256</span>


<span class="c"># f[possibleKeyA[1]]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>[26,26,101,229]
[35,163,118,118]
[200,200,196,68]
</pre>
</div>
</div>

<div class="output_area"><div class="prompt output_prompt">Out[82]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>true</pre>
</div>

</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[84]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">ancientKeyA</span><span class="o">=</span><span class="kt">Int</span><span class="p">[]</span>

<span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">possibleKeyA</span><span class="p">)</span>
  <span class="n">sKeyA</span><span class="o">=</span><span class="n">possibleKeyA</span><span class="p">[</span><span class="n">i</span><span class="p">]</span>
  <span class="n">r</span><span class="o">=</span><span class="mi">0</span>
  <span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="n">m</span>
      <span class="n">r</span><span class="o">+=</span><span class="p">(</span><span class="n">chiff</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="o">%</span><span class="mi">256</span>
  <span class="k">end</span>
  <span class="n">sKeyA</span><span class="o">=</span><span class="p">(</span><span class="n">sKeyA</span><span class="o">-</span><span class="n">r</span><span class="p">)</span><span class="o">%</span><span class="mi">256</span>



  <span class="n">push!</span><span class="p">(</span><span class="n">ancientKeyA</span><span class="p">,</span><span class="n">sKeyA</span><span class="p">)</span>
<span class="k">end</span>


<span class="n">println</span><span class="p">(</span><span class="n">ancientKeyA</span><span class="p">)</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>[226,226,45,173]
</pre>
</div>
</div>

</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[93]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">SK</span><span class="o">=</span><span class="p">[</span><span class="mi">0</span> <span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="mi">20</span><span class="p">]</span>
<span class="n">println</span><span class="p">(</span><span class="n">possibleKeyA</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">possibleValues</span><span class="p">)</span>
<span class="n">println</span><span class="p">(</span><span class="n">possibleKeyA2</span><span class="p">)</span>

<span class="n">SK</span><span class="p">[</span><span class="n">nustop</span><span class="p">[</span><span class="n">m</span><span class="p">]]</span><span class="o">=</span><span class="n">possibleValues</span><span class="p">[</span><span class="mi">1</span><span class="p">]</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>[26,26,101,229]
[35,163,118,118]
[200,200,196,68]
</pre>
</div>
</div>

<div class="output_area"><div class="prompt output_prompt">Out[93]:</div>


<div class="output_text output_subarea output_execute_result">
<pre>35</pre>
</div>

</div>

</div>
</div>

</div>
  </div>
</div>
