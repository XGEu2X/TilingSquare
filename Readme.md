<!doctype html>
<html>
<head>
<meta charset="utf-8">
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/github-markdown-css/3.0.1/github-markdown.min.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/highlight.js@9.18.1/lib/index.min.js">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/katex@0.11.1/dist/katex.min.css">
<link rel="stylesheet" href="https://cdn.jsdelivr.net/npm/markdown-it-texmath@0.6.5/css/texmath.css">
<link rel="stylesheet" href="https://gitcdn.xyz/repo/goessner/mdmath/master/css/vscode-texmath.css">

</head>
<body class="markdown-body">
<h1 id="tilingsquare-2" data-line="0" class="code-line">TilingSquare</h1>
<p data-line="1" class="code-line">Program to discard all the possible 4,5-sides tilings of the square with seven (maybe more) pieces.</p>
<h2 id="introduction-2" data-line="3" class="code-line">INTRODUCTION</h2>
<p data-line="4" class="code-line"><br>
Let <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>S</mi></mrow><annotation encoding="application/x-tex">S</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.05764em;">S</span></span></span></span></eq> be a square and <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> be a convex polygon. We say that <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>S</mi></mrow><annotation encoding="application/x-tex">S</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.05764em;">S</span></span></span></span></eq> can be tiled by <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.43056em;vertical-align:0em;"></span><span class="mord mathdefault">n</span></span></span></span></eq> copies of <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> if there are convex polygons <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>T</mi><mn>1</mn></msub><mo>…</mo><mo separator="true">,</mo><msub><mi>T</mi><mi>n</mi></msub></mrow><annotation encoding="application/x-tex">T_1\dots,T_n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.8777699999999999em;vertical-align:-0.19444em;"></span><span class="mord"><span class="mord mathdefault" style="margin-right:0.13889em;">T</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height:0.30110799999999993em;"><span style="top:-2.5500000000000003em;margin-left:-0.13889em;margin-right:0.05em;"><span class="pstrut" style="height:2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mtight">1</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height:0.15em;"><span></span></span></span></span></span></span><span class="mspace" style="margin-right:0.16666666666666666em;"></span><span class="minner">…</span><span class="mspace" style="margin-right:0.16666666666666666em;"></span><span class="mpunct">,</span><span class="mspace" style="margin-right:0.16666666666666666em;"></span><span class="mord"><span class="mord mathdefault" style="margin-right:0.13889em;">T</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height:0.151392em;"><span style="top:-2.5500000000000003em;margin-left:-0.13889em;margin-right:0.05em;"><span class="pstrut" style="height:2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mathdefault mtight">n</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height:0.15em;"><span></span></span></span></span></span></span></span></span></span></eq>, all congruent to <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> such that <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>S</mi><mo>=</mo><mo>⋃</mo><msub><mi>T</mi><mi>i</mi></msub></mrow><annotation encoding="application/x-tex">S=\bigcup T_i</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.05764em;">S</span><span class="mspace" style="margin-right:0.2777777777777778em;"></span><span class="mrel">=</span><span class="mspace" style="margin-right:0.2777777777777778em;"></span></span><span class="base"><span class="strut" style="height:1.00001em;vertical-align:-0.25001em;"></span><span class="mop op-symbol small-op" style="position:relative;top:-0.0000050000000000050004em;">⋃</span><span class="mspace" style="margin-right:0.16666666666666666em;"></span><span class="mord"><span class="mord mathdefault" style="margin-right:0.13889em;">T</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height:0.31166399999999994em;"><span style="top:-2.5500000000000003em;margin-left:-0.13889em;margin-right:0.05em;"><span class="pstrut" style="height:2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mathdefault mtight">i</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height:0.15em;"><span></span></span></span></span></span></span></span></span></span></eq> and the <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><msub><mi>T</mi><mi>i</mi></msub></mrow><annotation encoding="application/x-tex">T_i</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.83333em;vertical-align:-0.15em;"></span><span class="mord"><span class="mord mathdefault" style="margin-right:0.13889em;">T</span><span class="msupsub"><span class="vlist-t vlist-t2"><span class="vlist-r"><span class="vlist" style="height:0.31166399999999994em;"><span style="top:-2.5500000000000003em;margin-left:-0.13889em;margin-right:0.05em;"><span class="pstrut" style="height:2.7em;"></span><span class="sizing reset-size6 size3 mtight"><span class="mord mathdefault mtight">i</span></span></span></span><span class="vlist-s">​</span></span><span class="vlist-r"><span class="vlist" style="height:0.15em;"><span></span></span></span></span></span></span></span></span></span></eq> have disjoint interiors.</p>
<p data-line="7" class="code-line">If <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.43056em;vertical-align:0em;"></span><span class="mord mathdefault">n</span></span></span></span></eq> is an odd number, then it is easy to see that <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>S</mi></mrow><annotation encoding="application/x-tex">S</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.05764em;">S</span></span></span></span></eq> can be split into <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.43056em;vertical-align:0em;"></span><span class="mord mathdefault">n</span></span></span></span></eq> congruent rectangles. It is not known in general if <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>S</mi></mrow><annotation encoding="application/x-tex">S</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.05764em;">S</span></span></span></span></eq> can be tiled by <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.43056em;vertical-align:0em;"></span><span class="mord mathdefault">n</span></span></span></span></eq> copies of <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> when <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> is not a rectangle. The standing conjecture is as follows.</p>
<p data-line="9" class="code-line"><strong>Conjecture</strong>. If <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi><mo>≥</mo><mn>3</mn></mrow><annotation encoding="application/x-tex">n\ge 3</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.7719400000000001em;vertical-align:-0.13597em;"></span><span class="mord mathdefault">n</span><span class="mspace" style="margin-right:0.2777777777777778em;"></span><span class="mrel">≥</span><span class="mspace" style="margin-right:0.2777777777777778em;"></span></span><span class="base"><span class="strut" style="height:0.64444em;vertical-align:0em;"></span><span class="mord">3</span></span></span></span></eq> is an odd integer, then a square <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>S</mi></mrow><annotation encoding="application/x-tex">S</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.05764em;">S</span></span></span></span></eq> may be tiled by <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>n</mi></mrow><annotation encoding="application/x-tex">n</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.43056em;vertical-align:0em;"></span><span class="mord mathdefault">n</span></span></span></span></eq> congruent copies of a convex polygon <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> only if <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>T</mi></mrow><annotation encoding="application/x-tex">T</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.13889em;">T</span></span></span></span></eq> is a rectangle.</p>
<p data-line="11" class="code-line">To see references and more details about this problem and the idea which lead to code this see: <strong>aqui va la liga al articulo</strong></p>
<h2 id="what-does-this-program-2" data-line="13" class="code-line">What does this program?</h2>
<h3 id="pre-preparation-of-data-2" data-line="15" class="code-line">Pre-preparation of data</h3>
<p data-line="16" class="code-line"><br>
First we need the files with the graphs associated with the possible admissible tilings. We previously provided this files, the ones without extension and name <eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>X</mi><mi>X</mi></mrow><annotation encoding="application/x-tex">XX</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.07847em;">X</span><span class="mord mathdefault" style="margin-right:0.07847em;">X</span></span></span></span></eq>pm<eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>Y</mi></mrow><annotation encoding="application/x-tex">Y</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.22222em;">Y</span></span></span></span></eq>c<eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>Z</mi></mrow><annotation encoding="application/x-tex">Z</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.07153em;">Z</span></span></span></span></eq>, and use it as input depending of in how many tiles we want to split the square.</p>
<p data-line="19" class="code-line">(<eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>X</mi><mi>X</mi><mo>=</mo></mrow><annotation encoding="application/x-tex">XX=</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.07847em;">X</span><span class="mord mathdefault" style="margin-right:0.07847em;">X</span><span class="mspace" style="margin-right:0.2777777777777778em;"></span><span class="mrel">=</span></span></span></span></eq> number of tiles plus five)</p>
<p data-line="21" class="code-line">Example for 7 pieces:</p>
<pre><code data-line="22" class="code-line language-python"><div>Graphs7 = load_plantri(filename=<span class="hljs-string">&#x27;12pm4c3&#x27;</span>)
</div></code></pre>
<h2 id="usage-4" data-line="26" class="code-line">Usage</h2>
<h3 id="one-notebook-for-each-amount-of-tiles-2" data-line="27" class="code-line">One notebook for each amount of tiles</h3>
<p data-line="28" class="code-line">\</p>
<p data-line="30" class="code-line">In each file, named TilingSearch<eq><span class="katex"><span class="katex-mathml"><math xmlns="http://www.w3.org/1998/Math/MathML"><semantics><mrow><mi>N</mi></mrow><annotation encoding="application/x-tex">N</annotation></semantics></math></span><span class="katex-html" aria-hidden="true"><span class="base"><span class="strut" style="height:0.68333em;vertical-align:0em;"></span><span class="mord mathdefault" style="margin-right:0.10903em;">N</span></span></span></span></eq>.ipynb, we first add a new graph for each possible distinguished vertex.</p>
<pre><code data-line="32" class="code-line language-python"><div>inputs = tqdm(Graphs7)

<span class="hljs-keyword">if</span> __name__ == <span class="hljs-string">&quot;__main__&quot;</span>:
    processed_list = Parallel(n_jobs=num_cores)(delayed(add_distinguished)(G) <span class="hljs-keyword">for</span> G <span class="hljs-keyword">in</span> inputs)

Graphs7 = [G <span class="hljs-keyword">for</span> DGraph <span class="hljs-keyword">in</span> processed_list <span class="hljs-keyword">for</span> G <span class="hljs-keyword">in</span> DGraph]

print(<span class="hljs-string">f&#x27;Constructed <span class="hljs-subst">{<span class="hljs-built_in">len</span>(Graphs7)}</span> graphs with a distinguished vertex.&#x27;</span>)
save_data(Graphs7,<span class="hljs-string">&#x27;all_tiling_grahps_7.txt&#x27;</span>)
</div></code></pre>
<p data-line="44" class="code-line">After that the remaining graphs pass through some filters based in some configurations that is known are not possible.</p>
<pre><code data-line="46" class="code-line language-python"><div><span class="hljs-comment">#Graphs7 = load_data(&#x27;all_tiling_grahps_7.txt&#x27;)</span>

inputs = tqdm(Graphs7)

<span class="hljs-keyword">if</span> __name__ == <span class="hljs-string">&quot;__main__&quot;</span>:
    processed_list = Parallel(n_jobs=num_cores)(delayed(first_filter)(G) <span class="hljs-keyword">for</span> G <span class="hljs-keyword">in</span> inputs)

Graphs7 = [Graphs7[i] <span class="hljs-keyword">for</span> i <span class="hljs-keyword">in</span> <span class="hljs-built_in">range</span>(<span class="hljs-built_in">len</span>(Graphs7)) <span class="hljs-keyword">if</span> processed_list[i]]

print(<span class="hljs-string">f&#x27;Left with <span class="hljs-subst">{<span class="hljs-built_in">len</span>(Graphs7)}</span> graphs after first filter.&#x27;</span>)
save_data(Graphs7,<span class="hljs-string">&#x27;filtered_tiling_grahps_7.txt&#x27;</span>)
</div></code></pre>
<p data-line="60" class="code-line">Notice that we have commented the line in which it can be loaded the previous results instead of calculate everything from the start.
<br>
<br>
The last part consists in exhaust the remaining graphs using a deep-search algorithm to assign angles and sides to each piece and see if it could be an achievable tiling.</p>
<pre><code data-line="65" class="code-line language-python"><div><span class="hljs-comment">#Graphs7_4 = load_data(&#x27;quadrilateral_tiling_grahps_7.txt&#x27;)</span>

save_ang_perms(<span class="hljs-number">4</span>,<span class="hljs-string">&#x27;4_perms.txt&#x27;</span>)

inputs = tqdm(Graphs7_4)
numSides = <span class="hljs-number">4</span>

<span class="hljs-keyword">if</span> __name__ == <span class="hljs-string">&quot;__main__&quot;</span>:
    processed_list = Parallel(n_jobs=num_cores)(delayed(search)(ig,G,numSides) <span class="hljs-keyword">for</span> ig,G <span class="hljs-keyword">in</span> <span class="hljs-built_in">enumerate</span>(inputs))

FinalNodes = [Nodes <span class="hljs-keyword">for</span> Nodes <span class="hljs-keyword">in</span> processed_list <span class="hljs-keyword">if</span> <span class="hljs-built_in">len</span>(Nodes)&gt;<span class="hljs-number">0</span>]

print(<span class="hljs-string">f&#x27;Left with <span class="hljs-subst">{<span class="hljs-built_in">len</span>(FinalNodes)}</span> graphs.&#x27;</span>)
</div></code></pre>
<h2 id="usage-5" data-line="81" class="code-line">Usage</h2>
<p data-line="83" class="code-line">You only need to run the notebook in order. If you have run a previous filter, you can uncomment the first line of the next box to use that calculated data.</p>
<h2 id="output-2" data-line="85" class="code-line">Output</h2>
<p data-line="86" class="code-line">The output is a list of lists. Each one containing objects that says which graph it is (with the indices in the input), with which permutation of angle-types (with the index it has in the generated perms file), and some additional information used in the process.
<br>
<br>
In the case the output is empty, means that all the cases were exhausted.</p>

</body></html>
