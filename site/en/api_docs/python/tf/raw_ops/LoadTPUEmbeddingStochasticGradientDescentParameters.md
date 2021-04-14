description: Load SGD embedding parameters.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.raw_ops.LoadTPUEmbeddingStochasticGradientDescentParameters" />
<meta itemprop="path" content="Stable" />
</div>

# tf.raw_ops.LoadTPUEmbeddingStochasticGradientDescentParameters

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">

</table>



Load SGD embedding parameters.

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.raw_ops.LoadTPUEmbeddingStochasticGradientDescentParameters`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.raw_ops.LoadTPUEmbeddingStochasticGradientDescentParameters(
    parameters, num_shards, shard_id, table_id=-1, table_name='', config='',
    name=None
)
</code></pre>



<!-- Placeholder for "Used in" -->

An op that loads optimization parameters into HBM for embedding. Must be
preceded by a ConfigureTPUEmbeddingHost op that sets up the correct
embedding table configuration. For example, this op is used to install
parameters that are loaded from a checkpoint before a training loop is
executed.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Args</h2></th></tr>

<tr>
<td>
`parameters`
</td>
<td>
A `Tensor` of type `float32`.
Value of parameters used in the stochastic gradient descent optimization algorithm.
</td>
</tr><tr>
<td>
`num_shards`
</td>
<td>
An `int`.
</td>
</tr><tr>
<td>
`shard_id`
</td>
<td>
An `int`.
</td>
</tr><tr>
<td>
`table_id`
</td>
<td>
An optional `int` that is `>= -1`. Defaults to `-1`.
</td>
</tr><tr>
<td>
`table_name`
</td>
<td>
An optional `string`. Defaults to `""`.
</td>
</tr><tr>
<td>
`config`
</td>
<td>
An optional `string`. Defaults to `""`.
</td>
</tr><tr>
<td>
`name`
</td>
<td>
A name for the operation (optional).
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
The created Operation.
</td>
</tr>

</table>
