description: Callback that streams epoch results to a csv file.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.keras.callbacks.CSVLogger" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="set_model"/>
<meta itemprop="property" content="set_params"/>
</div>

# tf.keras.callbacks.CSVLogger

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/keras/callbacks.py#L2278-L2367">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



Callback that streams epoch results to a csv file.

Inherits From: [`Callback`](../../../tf/keras/callbacks/Callback.md)

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.keras.callbacks.CSVLogger`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.keras.callbacks.CSVLogger(
    filename, separator=',', append=(False)
)
</code></pre>



<!-- Placeholder for "Used in" -->

Supports all values that can be represented as a string,
including 1D iterables such as np.ndarray.

#### Example:



```python
csv_logger = CSVLogger('training.log')
model.fit(X_train, Y_train, callbacks=[csv_logger])
```

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Arguments</h2></th></tr>

<tr>
<td>
`filename`
</td>
<td>
filename of the csv file, e.g. 'run/log.csv'.
</td>
</tr><tr>
<td>
`separator`
</td>
<td>
string used to separate elements in the csv file.
</td>
</tr><tr>
<td>
`append`
</td>
<td>
True: append if file exists (useful for continuing
training). False: overwrite existing file,
</td>
</tr>
</table>



## Methods

<h3 id="set_model"><code>set_model</code></h3>

<a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/keras/callbacks.py#L548-L549">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>set_model(
    model
)
</code></pre>




<h3 id="set_params"><code>set_params</code></h3>

<a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/keras/callbacks.py#L545-L546">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>set_params(
    params
)
</code></pre>






