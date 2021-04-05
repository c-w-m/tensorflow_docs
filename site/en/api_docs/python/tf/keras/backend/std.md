description: Standard deviation of a tensor, alongside the specified axis.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.backend.std" />
<meta itemprop="path" content="Stable" />
</div>

# tf.keras.backend.std

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/keras/backend.py#L2073-L2096">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Standard deviation of a tensor, alongside the specified axis.

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.keras.backend.std`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.keras.backend.std(
    x, axis=None, keepdims=(False)
)
</code></pre>



<!-- Placeholder for "Used in" -->

It is an alias to <a href="../../../tf/math/reduce_std.md"><code>tf.math.reduce_std</code></a>.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`x`
</td>
<td>
A tensor or variable. It should have numerical dtypes. Boolean type
inputs will be converted to float.
</td>
</tr><tr>
<td>
`axis`
</td>
<td>
An integer, the axis to compute the standard deviation. If `None`
(the default), reduces all dimensions. Must be in the range
`[-rank(x), rank(x))`.
</td>
</tr><tr>
<td>
`keepdims`
</td>
<td>
A boolean, whether to keep the dimensions or not.
If `keepdims` is `False`, the rank of the tensor is reduced
by 1. If `keepdims` is `True`, the reduced dimension is retained with
length 1.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
A tensor with the standard deviation of elements of `x` with same dtype.
Boolean type input will be converted to float.
</td>
</tr>

</table>

