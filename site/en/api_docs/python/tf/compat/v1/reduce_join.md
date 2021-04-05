description: Joins all strings into a single string, or joins along an axis.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.compat.v1.reduce_join" />
<meta itemprop="path" content="Stable" />
</div>

# tf.compat.v1.reduce_join

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/ops/string_ops.py#L321-L344">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Joins all strings into a single string, or joins along an axis.

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.strings.reduce_join`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.compat.v1.reduce_join(
    inputs, axis=None, keep_dims=None, separator='', name=None,
    reduction_indices=None, keepdims=None
)
</code></pre>



<!-- Placeholder for "Used in" -->

```
>>> tf.strings.reduce_join([['abc','123'],
...                         ['def','456']]).numpy()
b'abc123def456'
>>> tf.strings.reduce_join([['abc','123'],
...                         ['def','456']], axis=-1).numpy()
array([b'abc123', b'def456'], dtype=object)
>>> tf.strings.reduce_join([['abc','123'],
...                         ['def','456']],
...                        axis=-1,
...                        separator=" ").numpy()
array([b'abc 123', b'def 456'], dtype=object)
```

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Args</h2></th></tr>

<tr>
<td>
`inputs`
</td>
<td>
A <a href="../../../tf.md#string"><code>tf.string</code></a> tensor.
</td>
</tr><tr>
<td>
`axis`
</td>
<td>
Which axis to join along. The default behavior is to join all
elements, producing a scalar.
</td>
</tr><tr>
<td>
`keepdims`
</td>
<td>
If true, retains reduced dimensions with length 1.
</td>
</tr><tr>
<td>
`separator`
</td>
<td>
a string added between each string being joined.
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
A <a href="../../../tf.md#string"><code>tf.string</code></a> tensor.
</td>
</tr>

</table>

