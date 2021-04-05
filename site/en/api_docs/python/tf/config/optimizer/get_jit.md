description: Get if JIT compilation is enabled.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.config.optimizer.get_jit" />
<meta itemprop="path" content="Stable" />
</div>

# tf.config.optimizer.get_jit

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/framework/config.py#L80-L91">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Get if JIT compilation is enabled.

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.config.optimizer.get_jit`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.config.optimizer.get_jit()
</code></pre>



<!-- Placeholder for "Used in" -->

Note that optimizations are only applied to code that is compiled into a
graph. In eager mode, which is the TF2 API default, that means only code that
is defined under a tf.function decorator.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
If JIT compilation is enabled.
</td>
</tr>

</table>

