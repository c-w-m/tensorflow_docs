description: ClusterResolver for Google Compute Engine.

<div itemscope itemtype="http://developers.google.com/ReferenceObject">
<meta itemprop="name" content="tf.distribute.cluster_resolver.GCEClusterResolver" />
<meta itemprop="path" content="Stable" />
<meta itemprop="property" content="__init__"/>
<meta itemprop="property" content="cluster_spec"/>
<meta itemprop="property" content="master"/>
<meta itemprop="property" content="num_accelerators"/>
</div>

# tf.distribute.cluster_resolver.GCEClusterResolver

<!-- Insert buttons and diff -->

<table class="tfo-notebook-buttons tfo-api nocontent" align="left">
<td>
  <a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/distribute/cluster_resolver/gce_cluster_resolver.py#L35-L188">
    <img src="https://www.tensorflow.org/images/GitHub-Mark-32px.png" />
    View source on GitHub
  </a>
</td>
</table>



ClusterResolver for Google Compute Engine.

Inherits From: [`ClusterResolver`](../../../tf/distribute/cluster_resolver/ClusterResolver.md)

<section class="expandable">
  <h4 class="showalways">View aliases</h4>
  <p>
<b>Compat aliases for migration</b>
<p>See
<a href="https://www.tensorflow.org/guide/migrate">Migration guide</a> for
more details.</p>
<p>`tf.compat.v1.distribute.cluster_resolver.GCEClusterResolver`</p>
</p>
</section>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>tf.distribute.cluster_resolver.GCEClusterResolver(
    project, zone, instance_group, port, task_type='worker', task_id=0,
    rpc_layer='grpc', credentials='default', service=None
)
</code></pre>



<!-- Placeholder for "Used in" -->

This is an implementation of cluster resolvers for the Google Compute Engine
instance group platform. By specifying a project, zone, and instance group,
this will retrieve the IP address of all the instances within the instance
group and return a ClusterResolver object suitable for use for distributed
TensorFlow.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Args</h2></th></tr>

<tr>
<td>
`project`
</td>
<td>
Name of the GCE project.
</td>
</tr><tr>
<td>
`zone`
</td>
<td>
Zone of the GCE instance group.
</td>
</tr><tr>
<td>
`instance_group`
</td>
<td>
Name of the GCE instance group.
</td>
</tr><tr>
<td>
`port`
</td>
<td>
Port of the listening TensorFlow server (default: 8470)
</td>
</tr><tr>
<td>
`task_type`
</td>
<td>
Name of the TensorFlow job this GCE instance group of VM
instances belong to.
</td>
</tr><tr>
<td>
`task_id`
</td>
<td>
The task index for this particular VM, within the GCE
instance group. In particular, every single instance should be assigned
a unique ordinal index within an instance group manually so that they
can be distinguished from each other.
</td>
</tr><tr>
<td>
`rpc_layer`
</td>
<td>
The RPC layer TensorFlow should use to communicate across
instances.
</td>
</tr><tr>
<td>
`credentials`
</td>
<td>
GCE Credentials. If nothing is specified, this defaults to
GoogleCredentials.get_application_default().
</td>
</tr><tr>
<td>
`service`
</td>
<td>
The GCE API object returned by the googleapiclient.discovery
function. (Default: discovery.build('compute', 'v1')). If you specify a
custom service object, then the credentials parameter will be ignored.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Raises</h2></th></tr>

<tr>
<td>
`ImportError`
</td>
<td>
If the googleapiclient is not installed.
</td>
</tr>
</table>





<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2"><h2 class="add-link">Attributes</h2></th></tr>

<tr>
<td>
`environment`
</td>
<td>
Returns the current environment which TensorFlow is running in.

There are two possible return values, "google" (when TensorFlow is running
in a Google-internal environment) or an empty string (when TensorFlow is
running elsewhere).

If you are implementing a ClusterResolver that works in both the Google
environment and the open-source world (for instance, a TPU ClusterResolver
or similar), you will have to return the appropriate string depending on the
environment, which you will have to detect.

Otherwise, if you are implementing a ClusterResolver that will only work
in open-source TensorFlow, you do not need to implement this property.
</td>
</tr><tr>
<td>
`rpc_layer`
</td>
<td>

</td>
</tr><tr>
<td>
`task_id`
</td>
<td>

</td>
</tr><tr>
<td>
`task_type`
</td>
<td>

</td>
</tr>
</table>



## Methods

<h3 id="cluster_spec"><code>cluster_spec</code></h3>

<a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/distribute/cluster_resolver/gce_cluster_resolver.py#L106-L149">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>cluster_spec()
</code></pre>

Returns a ClusterSpec object based on the latest instance group info.

This returns a ClusterSpec object for use based on information from the
specified instance group. We will retrieve the information from the GCE APIs
every time this method is called.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Returns</th></tr>
<tr class="alt">
<td colspan="2">
A ClusterSpec containing host information retrieved from GCE.
</td>
</tr>

</table>



<h3 id="master"><code>master</code></h3>

<a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/distribute/cluster_resolver/gce_cluster_resolver.py#L151-L162">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>master(
    task_type=None, task_id=None, rpc_layer=None
)
</code></pre>

Retrieves the name or URL of the session master.


<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Args</th></tr>

<tr>
<td>
`task_type`
</td>
<td>
(Optional) The type of the TensorFlow task of the master.
</td>
</tr><tr>
<td>
`task_id`
</td>
<td>
(Optional) The index of the TensorFlow task of the master.
</td>
</tr><tr>
<td>
`rpc_layer`
</td>
<td>
(Optional) The RPC protocol for the given cluster.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Returns</th></tr>
<tr class="alt">
<td colspan="2">
The name or URL of the session master.
</td>
</tr>

</table>


Implementors of this function must take care in ensuring that the master
returned is up-to-date at the time to calling this function. This usually
means retrieving the master every time this function is invoked.

<h3 id="num_accelerators"><code>num_accelerators</code></h3>

<a target="_blank" href="https://github.com/tensorflow/tensorflow/blob/r2.2/tensorflow/python/distribute/cluster_resolver/cluster_resolver.py#L119-L154">View source</a>

<pre class="devsite-click-to-copy prettyprint lang-py tfo-signature-link">
<code>num_accelerators(
    task_type=None, task_id=None, config_proto=None
)
</code></pre>

Returns the number of accelerator cores per worker.

This returns the number of accelerator cores (such as GPUs and TPUs)
available per worker.

Optionally, we allow callers to specify the task_type, and task_id, for
if they want to target a specific TensorFlow process to query
the number of accelerators. This is to support heterogenous environments,
where the number of accelerators cores per host is different.

<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Args</th></tr>

<tr>
<td>
`task_type`
</td>
<td>
(Optional) The type of the TensorFlow task of the machine we
want to query.
</td>
</tr><tr>
<td>
`task_id`
</td>
<td>
(Optional) The index of the TensorFlow task of the machine we
want to query.
</td>
</tr><tr>
<td>
`config_proto`
</td>
<td>
(Optional) Configuration for starting a new session to
query how many accelerator cores it has.
</td>
</tr>
</table>



<!-- Tabular view -->
 <table class="responsive fixed orange">
<colgroup><col width="214px"><col></colgroup>
<tr><th colspan="2">Returns</th></tr>
<tr class="alt">
<td colspan="2">
A map of accelerator types to number of cores.
</td>
</tr>

</table>





