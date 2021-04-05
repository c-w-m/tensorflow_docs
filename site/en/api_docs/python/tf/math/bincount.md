description: Counts the number of occurrences of each value in an integer array.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.math.bincount" />
<meta itemprop="path" content="Stable" />
</div>

# tf.math.bincount

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/ops/math_ops.py#L3392-L3464">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Counts the number of occurrences of each value in an integer array.

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.math.bincount(
    arr, weights=None, minlength=None, maxlength=None, dtype=tf.dtypes.int32,
    name=None
)
</code></pre>



<!-- Placeholder for "Used in" -->

If `minlength` and `maxlength` are not given, returns a vector with length
`tf.reduce_max(arr) + 1` if `arr` is non-empty, and length 0 otherwise.
If `weights` are non-None, then index `i` of the output stores the sum of the
value in `weights` at each index where the corresponding value in `arr` is
`i`.

```python
values = tf.constant([1,1,2,3,2,4,4,5])
tf.math.bincount(values) #[0 2 2 1 2 1]
```
Vector length = Maximum element in vector `values` is 5. Adding 1, which is 6
                will be the vector length.

Each bin value in the output indicates number of occurrences of the particular
index. Here, index 1 in output has a value 2. This indicates value 1 occurs
two times in `values`.

```python
values = tf.constant([1,1,2,3,2,4,4,5])
weights = tf.constant([1,5,0,1,0,5,4,5])
tf.math.bincount(values, weights=weights) #[0 6 0 1 9 5]
```
Bin will be incremented by the corresponding weight instead of 1.
Here, index 1 in output has a value 6. This is the summation of weights
corresponding to the value in `values`.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Args</h2></th></tr>

<tr>
<td>
`arr`
</td>
<td>
An int32 tensor of non-negative values.
</td>
</tr><tr>
<td>
`weights`
</td>
<td>
If non-None, must be the same shape as arr. For each value in
`arr`, the bin will be incremented by the corresponding weight instead of
1.
</td>
</tr><tr>
<td>
`minlength`
</td>
<td>
If given, ensures the output has length at least `minlength`,
padding with zeros at the end if necessary.
</td>
</tr><tr>
<td>
`maxlength`
</td>
<td>
If given, skips values in `arr` that are equal or greater than
`maxlength`, ensuring that the output has length at most `maxlength`.
</td>
</tr><tr>
<td>
`dtype`
</td>
<td>
If `weights` is None, determines the type of the output bins.
</td>
</tr><tr>
<td>
`name`
</td>
<td>
A name scope for the associated operations (optional).
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Returns</h2></th></tr>
<tr class="alt">
<td colspan="2">
A vector with the same dtype as `weights` or the given `dtype`. The bin
values.
</td>
</tr>

</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Raises</h2></th></tr>
<tr class="alt">
<td colspan="2">
`InvalidArgumentError` if negative values are provided as an input.
</td>
</tr>

</table>

