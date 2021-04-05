description: Formats a string template using a list of tensors.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.strings.format" />
<meta itemprop="path" content="Stable" />
</div>

# tf.strings.format

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/ops/string_ops.py#L114-L192">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Formats a string template using a list of tensors.

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.strings.format`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.strings.format(
    template, inputs, placeholder='{}', summarize=3, name=None
)
</code></pre>



<!-- Placeholder for "Used in" -->

Formats a string template using a list of tensors, abbreviating tensors by
only printing the first and last `summarize` elements of each dimension
(recursively). If formatting only one tensor into a template, the tensor does
not have to be wrapped in a list.

#### Example:

Formatting a single-tensor template:
```python
sess = tf.compat.v1.Session()
with sess.as_default():
    tensor = tf.range(10)
    formatted = tf.strings.format("tensor: {}, suffix", tensor)
    out = sess.run(formatted)
    expected = "tensor: [0 1 2 ... 7 8 9], suffix"

    assert(out.decode() == expected)
```

Formatting a multi-tensor template:
```python
sess = tf.compat.v1.Session()
with sess.as_default():
    tensor_one = tf.reshape(tf.range(100), [10, 10])
    tensor_two = tf.range(10)
    formatted = tf.strings.format("first: {}, second: {}, suffix",
      (tensor_one, tensor_two))

    out = sess.run(formatted)
    expected = ("first: [[0 1 2 ... 7 8 9]\n"
          " [10 11 12 ... 17 18 19]\n"
          " [20 21 22 ... 27 28 29]\n"
          " ...\n"
          " [70 71 72 ... 77 78 79]\n"
          " [80 81 82 ... 87 88 89]\n"
          " [90 91 92 ... 97 98 99]], second: [0 1 2 ... 7 8 9], suffix")

    assert(out.decode() == expected)
```



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Args</h2></th></tr>

<tr>
<td>
`template`
</td>
<td>
A string template to format tensor values into.
</td>
</tr><tr>
<td>
`inputs`
</td>
<td>
A list of `Tensor` objects, or a single Tensor.
The list of tensors to format into the template string. If a solitary
tensor is passed in, the input tensor will automatically be wrapped as a
list.
</td>
</tr><tr>
<td>
`placeholder`
</td>
<td>
An optional `string`. Defaults to `{}`.
At each placeholder occurring in the template, a subsequent tensor
will be inserted.
</td>
</tr><tr>
<td>
`summarize`
</td>
<td>
An optional `int`. Defaults to `3`.
When formatting the tensors, show the first and last `summarize`
entries of each tensor dimension (recursively). If set to -1, all
elements of the tensor will be shown.
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
A scalar `Tensor` of type `string`.
</td>
</tr>

</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Raises</h2></th></tr>

<tr>
<td>
`ValueError`
</td>
<td>
if the number of placeholders does not match the number of
inputs.
</td>
</tr>
</table>

