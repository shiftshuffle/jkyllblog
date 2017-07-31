---
layout: post
title:  "Synthetic_Mycoplasma"
date:   2017-03-03 09:11:03
description:
thumbnail: nudib.jpg
categories: [code]
comments: true
# Information for the author block
author: Shift Shuffle
---

<div tabindex="-1" id="notebook" class="border-box-sizing">
  <div class="container" id="notebook-container">

<div class="cell border-box-sizing text_cell rendered">
<div class="prompt input_prompt">
</div>
<div class="inner_cell">
<div class="text_cell_render border-box-sizing rendered_html">
<h2 id="nucleotide-message-:)">nucleotide message :)<a class="anchor-link" href="#nucleotide-message-:)">&#182;</a></h2><p>lets see if i found some message here
<a href="http://www.ncbi.nlm.nih.gov/nuccore/296455217?report=fasta">JCVI-syn1.0</a></p>
<p>(i erased the secret mail to them :p)</p>

</div>
</div>
</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">dic</span><span class="o">=</span><span class="p">[</span> <span class="s">&quot;TAG&quot;</span> <span class="o">=&gt;</span> <span class="mi">97</span><span class="p">,</span> <span class="s">&quot;GCA&quot;</span> <span class="o">=&gt;</span> <span class="mi">107</span><span class="p">,</span> <span class="s">&quot;TCC&quot;</span> <span class="o">=&gt;</span> <span class="mi">117</span><span class="p">,</span> <span class="s">&quot;AGA&quot;</span> <span class="o">=&gt;</span> <span class="mi">52</span><span class="p">,</span> <span class="s">&quot;CAC&quot;</span> <span class="o">=&gt;</span> <span class="mi">47</span><span class="p">,</span>
   <span class="s">&quot;AGT&quot;</span> <span class="o">=&gt;</span> <span class="mi">98</span><span class="p">,</span>  <span class="s">&quot;AAC&quot;</span> <span class="o">=&gt;</span> <span class="mi">108</span><span class="p">,</span> <span class="s">&quot;TTG&quot;</span> <span class="o">=&gt;</span> <span class="mi">118</span><span class="p">,</span> <span class="s">&quot;GCG&quot;</span> <span class="o">=&gt;</span> <span class="mi">53</span><span class="p">,</span> <span class="s">&quot;CCA&quot;</span> <span class="o">=&gt;</span> <span class="mi">61</span><span class="p">,</span>
   <span class="s">&quot;TTT&quot;</span> <span class="o">=&gt;</span> <span class="mi">99</span><span class="p">,</span>  <span class="s">&quot;CAA&quot;</span> <span class="o">=&gt;</span> <span class="mi">109</span><span class="p">,</span> <span class="s">&quot;GTC&quot;</span> <span class="o">=&gt;</span> <span class="mi">119</span><span class="p">,</span> <span class="s">&quot;GCC&quot;</span> <span class="o">=&gt;</span> <span class="mi">54</span><span class="p">,</span> <span class="s">&quot;CGA&quot;</span> <span class="o">=&gt;</span> <span class="mi">46</span><span class="p">,</span>
   <span class="s">&quot;ATT&quot;</span> <span class="o">=&gt;</span> <span class="mi">100</span><span class="p">,</span> <span class="s">&quot;TGC&quot;</span> <span class="o">=&gt;</span> <span class="mi">110</span><span class="p">,</span> <span class="s">&quot;GGT&quot;</span> <span class="o">=&gt;</span> <span class="mi">120</span><span class="p">,</span> <span class="s">&quot;TAT&quot;</span> <span class="o">=&gt;</span> <span class="mi">55</span><span class="p">,</span> <span class="s">&quot;GAG&quot;</span> <span class="o">=&gt;</span> <span class="mi">33</span><span class="p">,</span>
   <span class="s">&quot;TAA&quot;</span> <span class="o">=&gt;</span> <span class="mi">101</span><span class="p">,</span> <span class="s">&quot;CGT&quot;</span> <span class="o">=&gt;</span> <span class="mi">111</span><span class="p">,</span> <span class="s">&quot;CAT&quot;</span> <span class="o">=&gt;</span> <span class="mi">121</span><span class="p">,</span> <span class="s">&quot;CGC&quot;</span> <span class="o">=&gt;</span> <span class="mi">56</span><span class="p">,</span> <span class="s">&quot;CAG&quot;</span> <span class="o">=&gt;</span> <span class="mi">58</span><span class="p">,</span>
   <span class="s">&quot;GGC&quot;</span> <span class="o">=&gt;</span> <span class="mi">102</span><span class="p">,</span> <span class="s">&quot;ACA&quot;</span> <span class="o">=&gt;</span> <span class="mi">112</span><span class="p">,</span> <span class="s">&quot;TGG&quot;</span> <span class="o">=&gt;</span> <span class="mi">122</span><span class="p">,</span> <span class="s">&quot;GTA&quot;</span> <span class="o">=&gt;</span> <span class="mi">57</span><span class="p">,</span> <span class="s">&quot;GGA&quot;</span> <span class="o">=&gt;</span> <span class="mi">34</span><span class="p">,</span>
   <span class="s">&quot;TAC&quot;</span> <span class="o">=&gt;</span> <span class="mi">103</span><span class="p">,</span> <span class="s">&quot;TTA&quot;</span> <span class="o">=&gt;</span> <span class="mi">113</span><span class="p">,</span> <span class="s">&quot;TCT&quot;</span> <span class="o">=&gt;</span> <span class="mi">48</span><span class="p">,</span>  <span class="s">&quot;ATA&quot;</span> <span class="o">=&gt;</span> <span class="mi">32</span><span class="p">,</span> <span class="s">&quot;GTG&quot;</span><span class="o">=&gt;</span> <span class="mi">44</span><span class="p">,</span>
   <span class="s">&quot;TCA&quot;</span> <span class="o">=&gt;</span> <span class="mi">104</span><span class="p">,</span> <span class="s">&quot;CTA&quot;</span> <span class="o">=&gt;</span> <span class="mi">114</span><span class="p">,</span> <span class="s">&quot;CTT&quot;</span> <span class="o">=&gt;</span> <span class="mi">49</span><span class="p">,</span>  <span class="s">&quot;GGG&quot;</span> <span class="o">=&gt;</span> <span class="mi">10</span><span class="p">,</span> <span class="s">&quot;TCG&quot;</span> <span class="o">=&gt;</span> <span class="mi">64</span><span class="p">,</span>
   <span class="s">&quot;CTG&quot;</span> <span class="o">=&gt;</span> <span class="mi">105</span><span class="p">,</span> <span class="s">&quot;GCT&quot;</span> <span class="o">=&gt;</span> <span class="mi">115</span><span class="p">,</span> <span class="s">&quot;ACT&quot;</span> <span class="o">=&gt;</span> <span class="mi">50</span><span class="p">,</span>  <span class="s">&quot;AGC&quot;</span> <span class="o">=&gt;</span> <span class="mi">62</span><span class="p">,</span> <span class="s">&quot;CCC&quot;</span> <span class="o">=&gt;</span> <span class="mi">45</span><span class="p">,</span>
   <span class="s">&quot;GTT&quot;</span> <span class="o">=&gt;</span> <span class="mi">106</span><span class="p">,</span> <span class="s">&quot;TGA&quot;</span> <span class="o">=&gt;</span> <span class="mi">116</span><span class="p">,</span> <span class="s">&quot;AAT&quot;</span> <span class="o">=&gt;</span> <span class="mi">51</span><span class="p">,</span>  <span class="s">&quot;CGG&quot;</span> <span class="o">=&gt;</span> <span class="mi">60</span><span class="p">];</span>
</pre></div>

</div>
</div>
</div>

</div>
<div class="cell border-box-sizing code_cell rendered">
<div class="input">
<div class="prompt input_prompt">In&nbsp;[1]:</div>
<div class="inner_cell">
  <div class="input_area">
<div class=" highlight hl-julia"><pre><span></span><span class="n">file</span> <span class="o">=</span> <span class="n">open</span><span class="p">(</span><span class="s">&quot;Synthetic_M.fasta&quot;</span><span class="p">,</span><span class="s">&quot;r&quot;</span><span class="p">)</span>
<span class="n">readline</span><span class="p">(</span><span class="n">file</span><span class="p">)</span>
<span class="n">lines</span><span class="o">=</span><span class="n">readlines</span><span class="p">(</span><span class="n">file</span><span class="p">)</span>

<span class="k">for</span> <span class="n">i</span><span class="o">=</span> <span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">lines</span><span class="p">)</span>
  <span class="n">lines</span><span class="p">[</span><span class="n">i</span><span class="p">]</span><span class="o">=</span><span class="n">lines</span><span class="p">[</span><span class="n">i</span><span class="p">][</span><span class="mi">1</span><span class="p">:</span><span class="n">length</span><span class="p">(</span><span class="n">lines</span><span class="p">[</span><span class="n">i</span><span class="p">])</span><span class="o">-</span><span class="mi">1</span><span class="p">]</span>
<span class="k">end</span>

<span class="n">sample</span><span class="o">=</span><span class="n">join</span><span class="p">(</span><span class="n">lines</span><span class="p">)</span>
<span class="n">close</span><span class="p">(</span><span class="n">file</span><span class="p">)</span>

<span class="c"># println(sample[length(sample)-20:length(sample)])</span>

<span class="n">passphrase</span><span class="o">=</span><span class="s">&quot;TTAACTAGCTAA&quot;</span>
<span class="n">stop</span><span class="o">=</span><span class="mi">0</span>
<span class="k">for</span> <span class="n">k</span><span class="o">=</span><span class="mi">1</span><span class="p">:</span><span class="mi">4</span>

  <span class="n">start</span><span class="o">=</span><span class="n">search</span><span class="p">(</span><span class="n">sample</span><span class="p">,</span><span class="n">passphrase</span><span class="p">,</span><span class="n">stop</span><span class="o">+</span><span class="mi">1</span><span class="p">)[</span><span class="mi">1</span><span class="p">]</span>
  <span class="n">stop</span><span class="o">=</span><span class="n">search</span><span class="p">(</span><span class="n">sample</span><span class="p">,</span><span class="n">passphrase</span><span class="p">,</span><span class="n">start</span><span class="o">+</span><span class="mi">1</span><span class="p">)[</span><span class="mi">1</span><span class="p">]</span>

  <span class="n">w</span><span class="o">=</span><span class="s">&quot;&quot;</span>
  <span class="k">for</span> <span class="n">i</span><span class="o">=</span><span class="n">start</span><span class="p">:</span><span class="mi">3</span><span class="p">:</span><span class="n">stop</span><span class="o">-</span><span class="mi">1</span>
      <span class="n">u</span><span class="o">=</span><span class="n">sample</span><span class="p">[</span><span class="n">i</span><span class="p">:</span><span class="n">i</span><span class="o">+</span><span class="mi">2</span><span class="p">]</span>
      <span class="k">if</span> <span class="n">haskey</span><span class="p">(</span><span class="n">dic</span><span class="p">,</span><span class="n">u</span><span class="p">)</span>
          <span class="n">w</span><span class="o">*=</span><span class="n">string</span><span class="p">(</span><span class="n">char</span><span class="p">(</span><span class="n">dic</span><span class="p">[</span><span class="n">u</span><span class="p">]))</span>
      <span class="k">end</span>
  <span class="k">end</span>
  <span class="n">print</span><span class="p">(</span><span class="n">w</span><span class="p">)</span>
  <span class="n">print</span><span class="p">(</span><span class="s">&quot;</span><span class="se">\n\n</span><span class="s">&quot;</span><span class="p">)</span>
<span class="k">end</span>
</pre></div>

</div>
</div>
</div>

<div class="output_wrapper">
<div class="output">


<div class="output_area"><div class="prompt"></div>
<div class="output_subarea output_stream output_stdout output_text">
<pre>q2&gt;eclyde hutchison, adriana jiga, radha krishnakumar, jan moy, monzia moodie, marvin frazier, holly baden-tilson, jason mitchell, dana busam, justin johnson, lakshmi devi viswanathan, jessica hostetler, robert friedman, vladimir noskov, jayshree zaveri.
&#34;see things not as they are, but as they might be.&#34;

q2&gt;ej. craig venter institute 2009
abcdefghijklmnopqrstuvwxyz
0123456789@-=/:&lt;&gt;&#34;!.,
synthetic genomics, inc.
&lt;!doctype html&gt;&lt;html&gt;&lt;head&gt;&lt;title&gt;genome team&lt;/title&gt;&lt;/head&gt;&lt;body&gt;&lt;a href=&#34;http://www.jcvi.org/&#34;&gt;the jcvi&lt;/a&gt;&lt;p&gt;prove youve decoded this watermark by emailing us &lt;a href=&#34;mailto:solveit&#34;&gt;here!&lt;/a&gt;&lt;/p&gt;&lt;/body&gt;&lt;/html&gt;f5

q2&gt;emikkel algire, michael montague, sanjay vashee, carole lartigue, chuck merryman, nina alperovich, nacyra assad-garcia, gwyn benders, ray-yuan chuang, evgenia denisova, daniel gibson, john glass, zhi-qing qi.
&#34;to live, to err, to fall, to triumph, to recreate life out of life.&#34; - james joycef5

q2&gt;ecynthia andrews-pfannkoch, quang phan, li ma, hamilton smith, adi ramon, christian tagwerker, j craig venter, eula wilturner, lei young, shibu yooseph, prabha iyer, tim stockwell, diana radune, bridget szczypinski, scott durkin, nadia fedorova, javier quinones, hanna tekleab.
&#34;what i cannot build, i cannot understand.&#34; - richard feynmanf5

</pre>
</div>
</div>

</div>
</div>

</div>
  </div>
</div>
