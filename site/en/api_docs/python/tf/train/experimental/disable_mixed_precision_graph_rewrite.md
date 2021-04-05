description: Disables the mixed precision graph rewrite.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.train.experimental.disable_mixed_precision_graph_rewrite" />
<meta itemprop="path" content="Stable" />
</div>

# tf.train.experimental.disable_mixed_precision_graph_rewrite

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/training/experimental/mixed_precision.py#L365-L386">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Disables the mixed precision graph rewrite.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.train.experimental.disable_mixed_precision_graph_rewrite()
</code></pre>



<!-- Placeholder for "Used in" -->

After this is called, the mixed precision graph rewrite will no longer run for
tf.functions, and so float32 operations will no longer be converted to
float16.

This does not undo the effects of loss scaling. Any optimizers wrapped with a
LossScaleOptimizer will continue to do loss scaling, although this loss
scaling will no longer be useful, as the graph rewrite no longer converts
tf.functions to use float16.

This function is useful for unit testing. A unit test can test using the mixed
precision graph rewrite, then disable it so future unit tests continue using
float32.