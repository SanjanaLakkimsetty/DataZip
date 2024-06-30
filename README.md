<h1>Creating Kubernetes config to launch Clickhouse & Superset pods in Minikube & connecting them</h1>

<h2> Overview</h2>
<p>This repository contains the necessary Kubernetes configuration files to deploy Clickhouse and Apache Superset on Minikube. The goal is to establish a stateful Clickhouse deployment with persistent storage and configure Superset, a business intelligence tool, to create reports and visualizations using data from Clickhouse.</p>

<h2>Prerequisites</h2>
<ul>
    <li>Kubernetes knowledge & minikube installed on local</li>
    <li> Kubernetes Knowledge: Understanding of Kubernetes concepts and commands.</li>
    <li>Docker knowledge</li>
    <li>Clickhouse → Read about it a bit. It's an open source data warehouse which can be operated using SQL queries</li>
  <li>Superset → It's a BI (business intelligence tool to create report & charts on data from data sources like clickhouse, postgres, etc... )
</li>
</ul>

<h2> Steps to Deploy</h2>
<ol>
    <li><strong> Deploy Clickhouse</strong>
        <p>Create a StatefulSet for Clickhouse with a persistent storage of 10GB. Expose the native port 9000 for Superset to connect.</p>
    </li>
    <li><strong> Deploy Superset</strong>
        <p>Create a Deployment for Superset. The configuration includes environment variables for the initial setup.</p>
    </li>
    <li><strong> Access Superset</strong>
        <p>Open Superset in your browser:</p>
        <pre><code>minikube service superset</code></pre>
    </li>
    <li><strong> Connect Clickhouse to Superset</strong>
        <p>
            <ol>
                <li>Go to the Superset URL in your browser.</li>
                <li>Navigate to <strong>Data &gt; Databases &gt; (+ Database button)</strong>.</li>
                <li>Choose Clickhouse from the list.</li>
                <li>Add the Clickhouse URL: <code>clickhouse://default@&lt;Clickhouse-Service-Name&gt;:9000/default</code></li>
                <li>Click <strong>Connect</strong>.</li>
            </ol>
        </p>
    </li>
</ol>

<h2>Submission Details</h2>
<p>All YAML files are placed in the root directory for ease of testing. The configurations are uploaded to this GitHub repository.</p>

</body>
</html>
