---
title: "Schema"
linkTitle: "Schema"
weight: 11
date: 2023-03-15
description: >
  API Schema definitions for Jenkins CRD
---

{{% pageinfo %}}
This document contains API scheme for `jenkins-operator` Custom Resource Definition manifest
{{% /pageinfo %}}

<p>Packages:</p>
<ul>
<li>
<a href="#jenkins.io">jenkins.io</a>
</li>
</ul>
<h2 id="jenkins.io">jenkins.io</h2>
<p>
<p>Package v1alpha2 contains API Schema definitions for the jenkins.io v1alpha2 API group</p>
</p>
Resource Types:
<ul><li>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Jenkins">Jenkins</a>
</li></ul>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Jenkins">Jenkins
</h3>
<p>
<p>Jenkins is the Schema for the jenkins API</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>apiVersion</code></br>
string</td>
<td>
<code>
jenkins.io/v1alpha2
</code>
</td>
</tr>
<tr>
<td>
<code>kind</code></br>
string
</td>
<td><code>Jenkins</code></td>
</tr>
<tr>
<td>
<code>metadata</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#objectmeta-v1-meta">
Kubernetes meta/v1.ObjectMeta
</a>
</em>
</td>
<td>
Refer to the Kubernetes API documentation for the fields of the
<code>metadata</code> field.
</td>
</tr>
<tr>
<td>
<code>spec</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsSpec">
JenkinsSpec
</a>
</em>
</td>
<td>
<p>Spec defines the desired state of the Jenkins</p>
<br/>
<br/>
<table>
<tr>
<td>
<code>master</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsMaster">
JenkinsMaster
</a>
</em>
</td>
<td>
<p>Master represents Jenkins master pod properties and Jenkins plugins.
Every single change here requires a pod restart.</p>
</td>
</tr>
<tr>
<td>
<code>seedJobs</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SeedJob">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SeedJob
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>SeedJobs defines list of Jenkins Seed Job configurations
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configuration#configure-seed-jobs-and-pipelines">
  https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configuring-seed-jobs-and-pipelines/</a></p>
</td>
</tr>
<tr>
<td>
<code>validateSecurityWarnings</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>ValidateSecurityWarnings enables or disables validating potential security warnings in Jenkins plugins via admission webhooks.</p>
</td>
</tr>
<tr>
<td>
<code>notifications</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Notification">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Notification
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Notifications defines list of a services which are used to inform about Jenkins status
Can be used to integrate chat services like Slack, Microsoft Teams or Mailgun</p>
</td>
</tr>
<tr>
<td>
<code>service</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Service">
Service
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Service is Kubernetes service of Jenkins master HTTP pod
Defaults to :
port: 8080
type: ClusterIP</p>
</td>
</tr>
<tr>
<td>
<code>slaveService</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Service">
Service
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Service is Kubernetes service of Jenkins slave pods
Defaults to :
port: 50000
type: ClusterIP</p>
</td>
</tr>
<tr>
<td>
<code>backup</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Backup">
Backup
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Backup defines configuration of Jenkins backup
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/">https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/</a></p>
</td>
</tr>
<tr>
<td>
<code>restore</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Restore">
Restore
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Backup defines configuration of Jenkins backup restore
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/">https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/</a></p>
</td>
</tr>
<tr>
<td>
<code>groovyScripts</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.GroovyScripts">
GroovyScripts
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>GroovyScripts defines configuration of Jenkins customization via groovy scripts</p>
</td>
</tr>
<tr>
<td>
<code>configurationAsCode</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ConfigurationAsCode">
ConfigurationAsCode
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ConfigurationAsCode defines configuration of Jenkins customization via Configuration as Code Jenkins plugin</p>
</td>
</tr>
<tr>
<td>
<code>roles</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#roleref-v1-rbac">
[]Kubernetes rbac/v1.RoleRef
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Roles defines list of extra RBAC roles for the Jenkins Master pod service account</p>
</td>
</tr>
<tr>
<td>
<code>serviceAccount</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ServiceAccount">
ServiceAccount
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ServiceAccount defines Jenkins master service account attributes</p>
</td>
</tr>
<tr>
<td>
<code>jenkinsAPISettings</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsAPISettings">
JenkinsAPISettings
</a>
</em>
</td>
<td>
<p>JenkinsAPISettings defines configuration used by the operator to gain admin access to the Jenkins API</p>
</td>
</tr>
</table>
</td>
</tr>
<tr>
<td>
<code>status</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsStatus">
JenkinsStatus
</a>
</em>
</td>
<td>
<p>Status defines the observed state of Jenkins</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.AppliedGroovyScript">AppliedGroovyScript
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsStatus">JenkinsStatus</a>)
</p>
<p>
<p>AppliedGroovyScript is the applied groovy script in Jenkins by the operator.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>configurationType</code></br>
<em>
string
</em>
</td>
<td>
<p>ConfigurationType is the name of the configuration type(base-groovy, user-groovy, user-casc)</p>
</td>
</tr>
<tr>
<td>
<code>source</code></br>
<em>
string
</em>
</td>
<td>
<p>Source is the name of source where is located groovy script</p>
</td>
</tr>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
<p>Name is the name of the groovy script</p>
</td>
</tr>
<tr>
<td>
<code>hash</code></br>
<em>
string
</em>
</td>
<td>
<p>Hash is the hash of the groovy script and secrets which it uses</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.AuthorizationStrategy">AuthorizationStrategy
(<code>string</code> alias)</p></h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsAPISettings">JenkinsAPISettings</a>)
</p>
<p>
<p>AuthorizationStrategy defines authorization strategy of the operator for the Jenkins API</p>
</p>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Backup">Backup
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>Backup defines configuration of Jenkins backup.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>containerName</code></br>
<em>
string
</em>
</td>
<td>
<p>ContainerName is the container name responsible for backup operation</p>
</td>
</tr>
<tr>
<td>
<code>action</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Handler">
Handler
</a>
</em>
</td>
<td>
<p>Action defines action which performs backup in backup container sidecar</p>
</td>
</tr>
<tr>
<td>
<code>interval</code></br>
<em>
uint64
</em>
</td>
<td>
<p>Interval tells how often make backup in seconds
Defaults to 30.</p>
</td>
</tr>
<tr>
<td>
<code>makeBackupBeforePodDeletion</code></br>
<em>
bool
</em>
</td>
<td>
<p>MakeBackupBeforePodDeletion tells operator to make backup before Jenkins master pod deletion</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ConfigMapRef">ConfigMapRef
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Customization">Customization</a>)
</p>
<p>
<p>ConfigMapRef is reference to Kubernetes ConfigMap.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ConfigurationAsCode">ConfigurationAsCode
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>ConfigurationAsCode defines configuration of Jenkins customization via Configuration as Code Jenkins plugin.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>Customization</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Customization">
Customization
</a>
</em>
</td>
<td>
<p>
(Members of <code>Customization</code> are embedded into this type.)
</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Container">Container
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsMaster">JenkinsMaster</a>)
</p>
<p>
<p>Container defines Kubernetes container attributes.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
<p>Name of the container specified as a DNS_LABEL.
Each container in a pod must have a unique name (DNS_LABEL).</p>
</td>
</tr>
<tr>
<td>
<code>image</code></br>
<em>
string
</em>
</td>
<td>
<p>Docker image name.
More info: <a href="https://kubernetes.io/docs/concepts/containers/images">https://kubernetes.io/docs/concepts/containers/images</a></p>
</td>
</tr>
<tr>
<td>
<code>imagePullPolicy</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#pullpolicy-v1-core">
Kubernetes core/v1.PullPolicy
</a>
</em>
</td>
<td>
<p>Image pull policy.
One of Always, Never, IfNotPresent.
Defaults to Always.</p>
</td>
</tr>
<tr>
<td>
<code>resources</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#resourcerequirements-v1-core">
Kubernetes core/v1.ResourceRequirements
</a>
</em>
</td>
<td>
<p>Compute Resources required by this container.
More info: <a href="https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/">https://kubernetes.io/docs/concepts/configuration/manage-compute-resources-container/</a></p>
</td>
</tr>
<tr>
<td>
<code>command</code></br>
<em>
[]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Entrypoint array. Not executed within a shell.
The docker image&rsquo;s ENTRYPOINT is used if this is not provided.
Variable references $(VAR_NAME) are expanded using the container&rsquo;s environment. If a variable
cannot be resolved, the reference in the input string will be unchanged. The $(VAR_NAME) syntax
can be escaped with a double $$, ie: $$(VAR_NAME). Escaped references will never be expanded,
regardless of whether the variable exists or not.
More info: <a href="https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/#running-a-command-in-a-shell">https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/#running-a-command-in-a-shell</a></p>
</td>
</tr>
<tr>
<td>
<code>args</code></br>
<em>
[]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Arguments to the entrypoint.
The docker image&rsquo;s CMD is used if this is not provided.
Variable references $(VAR_NAME) are expanded using the container&rsquo;s environment. If a variable
cannot be resolved, the reference in the input string will be unchanged. The $(VAR_NAME) syntax
can be escaped with a double $$, ie: $$(VAR_NAME). Escaped references will never be expanded,
regardless of whether the variable exists or not.
More info: <a href="https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/#running-a-command-in-a-shell">https://kubernetes.io/docs/tasks/inject-data-application/define-command-argument-container/#running-a-command-in-a-shell</a></p>
</td>
</tr>
<tr>
<td>
<code>workingDir</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Container&rsquo;s working directory.
If not specified, the container runtime&rsquo;s default will be used, which
might be configured in the container image.</p>
</td>
</tr>
<tr>
<td>
<code>ports</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#containerport-v1-core">
[]Kubernetes core/v1.ContainerPort
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>List of ports to expose from the container. Exposing a port here gives
the system additional information about the network connections a
container uses, but is primarily informational. Not specifying a port here
DOES NOT prevent that port from being exposed. Any port which is
listening on the default &ldquo;0.0.0.0&rdquo; address inside a container will be
accessible from the network.</p>
</td>
</tr>
<tr>
<td>
<code>envFrom</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#envfromsource-v1-core">
[]Kubernetes core/v1.EnvFromSource
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>List of sources to populate environment variables in the container.
The keys defined within a source must be a C_IDENTIFIER. All invalid keys
will be reported as an event when the container is starting. When a key exists in multiple
sources, the value associated with the last source will take precedence.
Values defined by an Env with a duplicate key will take precedence.</p>
</td>
</tr>
<tr>
<td>
<code>env</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#envvar-v1-core">
[]Kubernetes core/v1.EnvVar
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>List of environment variables to set in the container.</p>
</td>
</tr>
<tr>
<td>
<code>volumeMounts</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#volumemount-v1-core">
[]Kubernetes core/v1.VolumeMount
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Pod volumes to mount into the container&rsquo;s filesystem.</p>
</td>
</tr>
<tr>
<td>
<code>livenessProbe</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#probe-v1-core">
Kubernetes core/v1.Probe
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Periodic probe of container liveness.
Container will be restarted if the probe fails.</p>
</td>
</tr>
<tr>
<td>
<code>readinessProbe</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#probe-v1-core">
Kubernetes core/v1.Probe
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Periodic probe of container service readiness.
Container will be removed from service endpoints if the probe fails.</p>
</td>
</tr>
<tr>
<td>
<code>lifecycle</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#lifecycle-v1-core">
Kubernetes core/v1.Lifecycle
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Actions that the management system should take in response to container lifecycle events.</p>
</td>
</tr>
<tr>
<td>
<code>securityContext</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#securitycontext-v1-core">
Kubernetes core/v1.SecurityContext
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Security options the pod should run with.
More info: <a href="https://kubernetes.io/docs/concepts/policy/security-context/">https://kubernetes.io/docs/concepts/policy/security-context/</a>
More info: <a href="https://kubernetes.io/docs/tasks/configure-pod-container/security-context/">https://kubernetes.io/docs/tasks/configure-pod-container/security-context/</a></p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Customization">Customization
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.ConfigurationAsCode">ConfigurationAsCode</a>, 
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.GroovyScripts">GroovyScripts</a>)
</p>
<p>
<p>Customization defines configuration of Jenkins customization.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>secret</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretRef">
SecretRef
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>configurations</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ConfigMapRef">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ConfigMapRef
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.GroovyScripts">GroovyScripts
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>GroovyScripts defines configuration of Jenkins customization via groovy scripts.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>Customization</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Customization">
Customization
</a>
</em>
</td>
<td>
<p>
(Members of <code>Customization</code> are embedded into this type.)
</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Handler">Handler
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Backup">Backup</a>, 
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Restore">Restore</a>)
</p>
<p>
<p>Handler defines a specific action that should be taken.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>exec</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#execaction-v1-core">
Kubernetes core/v1.ExecAction
</a>
</em>
</td>
<td>
<p>Exec specifies the action to take.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsAPISettings">JenkinsAPISettings
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>JenkinsAPISettings defines configuration used by the operator to gain admin access to the Jenkins API</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>authorizationStrategy</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.AuthorizationStrategy">
AuthorizationStrategy
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsCredentialType">JenkinsCredentialType
(<code>string</code> alias)</p></h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.SeedJob">SeedJob</a>)
</p>
<p>
<p>JenkinsCredentialType defines type of Jenkins credential used to seed job mechanism.</p>
</p>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsMaster">JenkinsMaster
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>JenkinsMaster defines the Jenkins master pod attributes and plugins,
every single change requires a Jenkins master pod restart.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>annotations</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Annotations is an unstructured key value map stored with a resource that may be
set by external tools to store and retrieve arbitrary metadata. They are not
queryable and should be preserved when modifying objects.
More info: <a href="http://kubernetes.io/docs/user-guide/annotations">http://kubernetes.io/docs/user-guide/annotations</a></p>
</td>
</tr>
<tr>
<td>
<code>labels</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Map of string keys and values that can be used to organize and categorize
(scope and select) objects. May match selectors of replication controllers
and services.
More info: <a href="http://kubernetes.io/docs/user-guide/labels">http://kubernetes.io/docs/user-guide/labels</a></p>
</td>
</tr>
<tr>
<td>
<code>nodeSelector</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>NodeSelector is a selector which must be true for the pod to fit on a node.
Selector which must match a node&rsquo;s labels for the pod to be scheduled on that node.
More info: <a href="https://kubernetes.io/docs/concepts/configuration/assign-pod-node/">https://kubernetes.io/docs/concepts/configuration/assign-pod-node/</a></p>
</td>
</tr>
<tr>
<td>
<code>securityContext</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#podsecuritycontext-v1-core">
Kubernetes core/v1.PodSecurityContext
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>SecurityContext that applies to all the containers of the Jenkins
Master. As per kubernetes specification, it can be overridden
for each container individually.
Defaults to:
runAsUser: 1000
fsGroup: 1000</p>
</td>
</tr>
<tr>
<td>
<code>containers</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Container">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Container
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>List of containers belonging to the pod.
Containers cannot currently be added or removed.
There must be at least one container in a Pod.
Defaults to:
- image: jenkins/jenkins:lts
imagePullPolicy: Always
livenessProbe:
failureThreshold: 12
httpGet:
path: /login
port: http
scheme: HTTP
initialDelaySeconds: 80
periodSeconds: 10
successThreshold: 1
timeoutSeconds: 5
name: jenkins-master
readinessProbe:
failureThreshold: 3
httpGet:
path: /login
port: http
scheme: HTTP
initialDelaySeconds: 30
periodSeconds: 10
successThreshold: 1
timeoutSeconds: 1
resources:
limits:
cpu: 1500m
memory: 3Gi
requests:
cpu: &ldquo;1&rdquo;
memory: 600Mi</p>
</td>
</tr>
<tr>
<td>
<code>imagePullSecrets</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#localobjectreference-v1-core">
[]Kubernetes core/v1.LocalObjectReference
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ImagePullSecrets is an optional list of references to secrets in the same namespace to use for pulling any of the images used by this PodSpec.
If specified, these secrets will be passed to individual puller implementations for them to use. For example,
in the case of docker, only DockerConfig type secrets are honored.
More info: <a href="https://kubernetes.io/docs/concepts/containers/images#specifying-imagepullsecrets-on-a-pod">https://kubernetes.io/docs/concepts/containers/images#specifying-imagepullsecrets-on-a-pod</a></p>
</td>
</tr>
<tr>
<td>
<code>volumes</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#volume-v1-core">
[]Kubernetes core/v1.Volume
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>List of volumes that can be mounted by containers belonging to the pod.
More info: <a href="https://kubernetes.io/docs/concepts/storage/volumes">https://kubernetes.io/docs/concepts/storage/volumes</a></p>
</td>
</tr>
<tr>
<td>
<code>tolerations</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#toleration-v1-core">
[]Kubernetes core/v1.Toleration
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>If specified, the pod&rsquo;s tolerations.</p>
</td>
</tr>
<tr>
<td>
<code>basePlugins</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Plugin">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Plugin
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>BasePlugins contains plugins required by operator
Defaults to :
- name: kubernetes
version: &ldquo;1.30.11&rdquo;
- name: workflow-job
version: &ldquo;2.42&rdquo;
- name: workflow-aggregator
version: &ldquo;2.6&rdquo;
- name: git
version: &ldquo;4.10.0&rdquo;
- name: job-dsl
version: &ldquo;1.78.1&rdquo;
- name: configuration-as-code
version: &ldquo;1.55&rdquo;
- name: kubernetes-credentials-provider
version: &ldquo;0.20&rdquo;</p>
</td>
</tr>
<tr>
<td>
<code>plugins</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Plugin">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Plugin
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Plugins contains plugins required by user</p>
</td>
</tr>
<tr>
<td>
<code>disableCSRFProtection</code></br>
<em>
bool
</em>
</td>
<td>
<p>DisableCSRFProtection allows you to toggle CSRF Protection on Jenkins</p>
</td>
</tr>
<tr>
<td>
<code>priorityClassName</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>PriorityClassName for Jenkins master pod</p>
</td>
</tr>
<tr>
<td>
<code>hostAliases</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#hostalias-v1-core">
[]Kubernetes core/v1.HostAlias
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>HostAliases for Jenkins master pod and SeedJob agent</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsSpec">JenkinsSpec
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Jenkins">Jenkins</a>)
</p>
<p>
<p>JenkinsSpec defines the desired state of Jenkins</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>master</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsMaster">
JenkinsMaster
</a>
</em>
</td>
<td>
<p>Master represents Jenkins master pod properties and Jenkins plugins.
Every single change here requires a pod restart.</p>
</td>
</tr>
<tr>
<td>
<code>seedJobs</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SeedJob">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SeedJob
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>SeedJobs defines list of Jenkins Seed Job configurations
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configuration#configure-seed-jobs-and-pipelines">https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configuration#configure-seed-jobs-and-pipelines</a></p>
</td>
</tr>
<tr>
<td>
<code>validateSecurityWarnings</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>ValidateSecurityWarnings enables or disables validating potential security warnings in Jenkins plugins via admission webhooks.</p>
</td>
</tr>
<tr>
<td>
<code>notifications</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Notification">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Notification
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Notifications defines list of a services which are used to inform about Jenkins status
Can be used to integrate chat services like Slack, Microsoft Teams or Mailgun</p>
</td>
</tr>
<tr>
<td>
<code>service</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Service">
Service
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Service is Kubernetes service of Jenkins master HTTP pod
Defaults to :
port: 8080
type: ClusterIP</p>
</td>
</tr>
<tr>
<td>
<code>slaveService</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Service">
Service
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Service is Kubernetes service of Jenkins slave pods
Defaults to :
port: 50000
type: ClusterIP</p>
</td>
</tr>
<tr>
<td>
<code>backup</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Backup">
Backup
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Backup defines configuration of Jenkins backup
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/">https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/</a></p>
</td>
</tr>
<tr>
<td>
<code>restore</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Restore">
Restore
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Backup defines configuration of Jenkins backup restore
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/">https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configure-backup-and-restore/</a></p>
</td>
</tr>
<tr>
<td>
<code>groovyScripts</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.GroovyScripts">
GroovyScripts
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>GroovyScripts defines configuration of Jenkins customization via groovy scripts</p>
</td>
</tr>
<tr>
<td>
<code>configurationAsCode</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ConfigurationAsCode">
ConfigurationAsCode
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ConfigurationAsCode defines configuration of Jenkins customization via Configuration as Code Jenkins plugin</p>
</td>
</tr>
<tr>
<td>
<code>roles</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#roleref-v1-rbac">
[]Kubernetes rbac/v1.RoleRef
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Roles defines list of extra RBAC roles for the Jenkins Master pod service account</p>
</td>
</tr>
<tr>
<td>
<code>serviceAccount</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ServiceAccount">
ServiceAccount
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ServiceAccount defines Jenkins master service account attributes</p>
</td>
</tr>
<tr>
<td>
<code>jenkinsAPISettings</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsAPISettings">
JenkinsAPISettings
</a>
</em>
</td>
<td>
<p>JenkinsAPISettings defines configuration used by the operator to gain admin access to the Jenkins API</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsStatus">JenkinsStatus
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Jenkins">Jenkins</a>)
</p>
<p>
<p>JenkinsStatus defines the observed state of Jenkins</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>operatorVersion</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>OperatorVersion is the operator version which manages this CR</p>
</td>
</tr>
<tr>
<td>
<code>provisionStartTime</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#time-v1-meta">
Kubernetes meta/v1.Time
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>ProvisionStartTime is a time when Jenkins master pod has been created</p>
</td>
</tr>
<tr>
<td>
<code>baseConfigurationCompletedTime</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#time-v1-meta">
Kubernetes meta/v1.Time
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>BaseConfigurationCompletedTime is a time when Jenkins base configuration phase has been completed</p>
</td>
</tr>
<tr>
<td>
<code>userConfigurationCompletedTime</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#time-v1-meta">
Kubernetes meta/v1.Time
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>UserConfigurationCompletedTime is a time when Jenkins user configuration phase has been completed</p>
</td>
</tr>
<tr>
<td>
<code>restoredBackup</code></br>
<em>
uint64
</em>
</td>
<td>
<em>(Optional)</em>
<p>RestoredBackup is the restored backup number after Jenkins master pod restart</p>
</td>
</tr>
<tr>
<td>
<code>lastBackup</code></br>
<em>
uint64
</em>
</td>
<td>
<em>(Optional)</em>
<p>LastBackup is the latest backup number</p>
</td>
</tr>
<tr>
<td>
<code>pendingBackup</code></br>
<em>
uint64
</em>
</td>
<td>
<em>(Optional)</em>
<p>PendingBackup is the pending backup number</p>
</td>
</tr>
<tr>
<td>
<code>backupDoneBeforePodDeletion</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>BackupDoneBeforePodDeletion tells if backup before pod deletion has been made</p>
</td>
</tr>
<tr>
<td>
<code>userAndPasswordHash</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>UserAndPasswordHash is a SHA256 hash made from user and password</p>
</td>
</tr>
<tr>
<td>
<code>createdSeedJobs</code></br>
<em>
[]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>CreatedSeedJobs contains list of seed job id already created in Jenkins</p>
</td>
</tr>
<tr>
<td>
<code>appliedGroovyScripts</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.AppliedGroovyScript">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.AppliedGroovyScript
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>AppliedGroovyScripts is a list with all applied groovy scripts in Jenkins by the operator</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Mailgun">Mailgun
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Notification">Notification</a>)
</p>
<p>
<p>Mailgun is handler for Mailgun email service notification channel.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>domain</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>apiKeySecretKeySelector</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretKeySelector">
SecretKeySelector
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>recipient</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>from</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.MicrosoftTeams">MicrosoftTeams
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Notification">Notification</a>)
</p>
<p>
<p>MicrosoftTeams is handler for Microsoft MicrosoftTeams notification channel.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>webHookURLSecretKeySelector</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretKeySelector">
SecretKeySelector
</a>
</em>
</td>
<td>
<p>The web hook URL to MicrosoftTeams App</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Notification">Notification
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>Notification is a service configuration used to send notifications about Jenkins status.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>level</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.NotificationLevel">
NotificationLevel
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>verbose</code></br>
<em>
bool
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>slack</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Slack">
github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Slack
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>teams</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.MicrosoftTeams">
github.com/jenkinsci/kubernetes-operator/api/v1alpha2.MicrosoftTeams
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>mailgun</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Mailgun">
github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Mailgun
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>smtp</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SMTP">
github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SMTP
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.NotificationLevel">NotificationLevel
(<code>string</code> alias)</p></h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Notification">Notification</a>)
</p>
<p>
<p>NotificationLevel defines the level of a Notification.</p>
</p>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Plugin">Plugin
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsMaster">JenkinsMaster</a>)
</p>
<p>
<p>Plugin defines Jenkins plugin.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
<p>Name is the name of Jenkins plugin</p>
</td>
</tr>
<tr>
<td>
<code>version</code></br>
<em>
string
</em>
</td>
<td>
<p>Version is the version of Jenkins plugin</p>
</td>
</tr>
<tr>
<td>
<code>downloadURL</code></br>
<em>
string
</em>
</td>
<td>
<p>DownloadURL is the custom url from where plugin has to be downloaded.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.PluginData">PluginData
</h3>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>Version</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>Kind</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.PluginInfo">PluginInfo
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.PluginsInfo">PluginsInfo</a>)
</p>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>securityWarnings</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Warning">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Warning
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.PluginsInfo">PluginsInfo
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.SecurityValidator">SecurityValidator</a>)
</p>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>plugins</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.PluginInfo">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.PluginInfo
</a>
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Restore">Restore
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>Restore defines configuration of Jenkins backup restore operation.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>containerName</code></br>
<em>
string
</em>
</td>
<td>
<p>ContainerName is the container name responsible for restore backup operation</p>
</td>
</tr>
<tr>
<td>
<code>action</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Handler">
Handler
</a>
</em>
</td>
<td>
<p>Action defines action which performs restore backup in restore container sidecar</p>
</td>
</tr>
<tr>
<td>
<code>getLatestAction</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Handler">
Handler
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>GetLatestAction defines action which returns the latest backup number. If there is no backup &ldquo;-1&rdquo; should be
returned.</p>
</td>
</tr>
<tr>
<td>
<code>recoveryOnce</code></br>
<em>
uint64
</em>
</td>
<td>
<em>(Optional)</em>
<p>RecoveryOnce if want to restore specific backup set this field and then Jenkins will be restarted and desired backup will be restored</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SMTP">SMTP
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Notification">Notification</a>)
</p>
<p>
<p>SMTP is handler for sending emails via this protocol.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>usernameSecretKeySelector</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretKeySelector">
SecretKeySelector
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>passwordSecretKeySelector</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretKeySelector">
SecretKeySelector
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>port</code></br>
<em>
int
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>server</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>tlsInsecureSkipVerify</code></br>
<em>
bool
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>from</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>to</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretKeySelector">SecretKeySelector
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Mailgun">Mailgun</a>, 
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.MicrosoftTeams">MicrosoftTeams</a>, 
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.SMTP">SMTP</a>, 
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Slack">Slack</a>)
</p>
<p>
<p>SecretKeySelector selects a key of a Secret.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>secret</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#localobjectreference-v1-core">
Kubernetes core/v1.LocalObjectReference
</a>
</em>
</td>
<td>
<p>The name of the secret in the pod&rsquo;s namespace to select from.</p>
</td>
</tr>
<tr>
<td>
<code>key</code></br>
<em>
string
</em>
</td>
<td>
<p>The key of the secret to select from.  Must be a valid secret key.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretRef">SecretRef
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Customization">Customization</a>)
</p>
<p>
<p>SecretRef is reference to Kubernetes secret.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>name</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecurityValidator">SecurityValidator
</h3>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>PluginDataCache</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.PluginsInfo">
PluginsInfo
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>isCached</code></br>
<em>
bool
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>Attempts</code></br>
<em>
int
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>checkingPeriod</code></br>
<em>
time.Duration
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SeedJob">SeedJob
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>SeedJob defines configuration for seed job
More info: <a href="https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configuration/#configure-seed-jobs-and-pipelines">https://jenkinsci.github.io/kubernetes-operator/docs/getting-started/latest/configuration/#configure-seed-jobs-and-pipelines</a>.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>id</code></br>
<em>
string
</em>
</td>
<td>
<p>ID is the unique seed job name</p>
</td>
</tr>
<tr>
<td>
<code>credentialID</code></br>
<em>
string
</em>
</td>
<td>
<p>CredentialID is the Kubernetes secret name which stores repository access credentials</p>
</td>
</tr>
<tr>
<td>
<code>description</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Description is the description of the seed job</p>
</td>
</tr>
<tr>
<td>
<code>targets</code></br>
<em>
string
</em>
</td>
<td>
<p>Targets is the repository path where are seed job definitions</p>
</td>
</tr>
<tr>
<td>
<code>repositoryBranch</code></br>
<em>
string
</em>
</td>
<td>
<p>RepositoryBranch is the repository branch where are seed job definitions</p>
</td>
</tr>
<tr>
<td>
<code>repositoryUrl</code></br>
<em>
string
</em>
</td>
<td>
<p>RepositoryURL is the repository access URL. Can be SSH or HTTPS.</p>
</td>
</tr>
<tr>
<td>
<code>credentialType</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.JenkinsCredentialType">
JenkinsCredentialType
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>JenkinsCredentialType is the <a href="https://jenkinsci.github.io/kubernetes-credentials-provider-plugin/">https://jenkinsci.github.io/kubernetes-credentials-provider-plugin/</a> credential type</p>
</td>
</tr>
<tr>
<td>
<code>bitbucketPushTrigger</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>BitbucketPushTrigger is used for Bitbucket web hooks</p>
</td>
</tr>
<tr>
<td>
<code>githubPushTrigger</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>GitHubPushTrigger is used for GitHub web hooks</p>
</td>
</tr>
<tr>
<td>
<code>buildPeriodically</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>BuildPeriodically is setting for scheduled trigger</p>
</td>
</tr>
<tr>
<td>
<code>pollSCM</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>PollSCM is setting for polling changes in SCM</p>
</td>
</tr>
<tr>
<td>
<code>ignoreMissingFiles</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>IgnoreMissingFiles is setting for Job DSL API plugin to ignore files that miss</p>
</td>
</tr>
<tr>
<td>
<code>additionalClasspath</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>AdditionalClasspath is setting for Job DSL API plugin to set Additional Classpath</p>
</td>
</tr>
<tr>
<td>
<code>failOnMissingPlugin</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>FailOnMissingPlugin is setting for Job DSL API plugin that fails job if required plugin is missing</p>
</td>
</tr>
<tr>
<td>
<code>unstableOnDeprecation</code></br>
<em>
bool
</em>
</td>
<td>
<em>(Optional)</em>
<p>UnstableOnDeprecation is setting for Job DSL API plugin that sets build status as unstable if build using deprecated features</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Service">Service
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>Service defines Kubernetes service attributes</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>annotations</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Annotations is an unstructured key value map stored with a resource that may be
set by external tools to store and retrieve arbitrary metadata. They are not
queryable and should be preserved when modifying objects.
More info: <a href="http://kubernetes.io/docs/user-guide/annotations">http://kubernetes.io/docs/user-guide/annotations</a></p>
</td>
</tr>
<tr>
<td>
<code>labels</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Route service traffic to pods with label keys and values matching this
selector. If empty or not present, the service is assumed to have an
external process managing its endpoints, which Kubernetes will not
modify. Only applies to types ClusterIP, NodePort, and LoadBalancer.
Ignored if type is ExternalName.
More info: <a href="https://kubernetes.io/docs/concepts/services-networking/service/">https://kubernetes.io/docs/concepts/services-networking/service/</a></p>
</td>
</tr>
<tr>
<td>
<code>type</code></br>
<em>
<a href="https://kubernetes.io/docs/reference/generated/kubernetes-api/v1.18/#servicetype-v1-core">
Kubernetes core/v1.ServiceType
</a>
</em>
</td>
<td>
<em>(Optional)</em>
<p>Type determines how the Service is exposed. Defaults to ClusterIP. Valid
options are ExternalName, ClusterIP, NodePort, and LoadBalancer.
&ldquo;ExternalName&rdquo; maps to the specified externalName.
&ldquo;ClusterIP&rdquo; allocates a cluster-internal IP address for load-balancing to
endpoints. Endpoints are determined by the selector or if that is not
specified, by manual construction of an Endpoints object. If clusterIP is
&ldquo;None&rdquo;, no virtual IP is allocated and the endpoints are published as a
set of endpoints rather than a stable IP.
&ldquo;NodePort&rdquo; builds on ClusterIP and allocates a port on every node which
routes to the clusterIP.
&ldquo;LoadBalancer&rdquo; builds on NodePort and creates an
external load-balancer (if supported in the current cloud) which routes
to the clusterIP.
More info: <a href="https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services---service-types">https://kubernetes.io/docs/concepts/services-networking/service/#publishing-services&mdash;service-types</a></p>
</td>
</tr>
<tr>
<td>
<code>port</code></br>
<em>
int32
</em>
</td>
<td>
<p>The port that are exposed by this service.
More info: <a href="https://kubernetes.io/docs/concepts/services-networking/service/#virtual-ips-and-service-proxies">https://kubernetes.io/docs/concepts/services-networking/service/#virtual-ips-and-service-proxies</a></p>
</td>
</tr>
<tr>
<td>
<code>nodePort</code></br>
<em>
int32
</em>
</td>
<td>
<em>(Optional)</em>
<p>The port on each node on which this service is exposed when type=NodePort or LoadBalancer.
Usually assigned by the system. If specified, it will be allocated to the service
if unused or else creation of the service will fail.
Default is to auto-allocate a port if the ServiceType of this Service requires one.
More info: <a href="https://kubernetes.io/docs/concepts/services-networking/service/#type-nodeport">https://kubernetes.io/docs/concepts/services-networking/service/#type-nodeport</a></p>
</td>
</tr>
<tr>
<td>
<code>loadBalancerSourceRanges</code></br>
<em>
[]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>If specified and supported by the platform, this will restrict traffic through the cloud-provider
load-balancer will be restricted to the specified client IPs. This field will be ignored if the
cloud-provider does not support the feature.&rdquo;
More info: <a href="https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/#restricting-cloud-metadata-api-access">https://kubernetes.io/docs/tasks/administer-cluster/securing-a-cluster/#restricting-cloud-metadata-api-access</a></p>
</td>
</tr>
<tr>
<td>
<code>loadBalancerIP</code></br>
<em>
string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Only applies to Service Type: LoadBalancer
LoadBalancer will get created with the IP specified in this field.
This feature depends on whether the underlying cloud-provider supports specifying
the loadBalancerIP when a load balancer is created.
This field will be ignored if the cloud-provider does not support the feature.</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.ServiceAccount">ServiceAccount
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.JenkinsSpec">JenkinsSpec</a>)
</p>
<p>
<p>ServiceAccount defines Kubernetes service account attributes</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>annotations</code></br>
<em>
map[string]string
</em>
</td>
<td>
<em>(Optional)</em>
<p>Annotations is an unstructured key value map stored with a resource that may be
set by external tools to store and retrieve arbitrary metadata. They are not
queryable and should be preserved when modifying objects.
More info: <a href="http://kubernetes.io/docs/user-guide/annotations">http://kubernetes.io/docs/user-guide/annotations</a></p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Slack">Slack
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Notification">Notification</a>)
</p>
<p>
<p>Slack is handler for Slack notification channel.</p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>webHookURLSecretKeySelector</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.SecretKeySelector">
SecretKeySelector
</a>
</em>
</td>
<td>
<p>The web hook URL to Slack App</p>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Version">Version
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.Warning">Warning</a>)
</p>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>firstVersion</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>lastVersion</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<h3 id="github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Warning">Warning
</h3>
<p>
(<em>Appears on:</em>
<a href="#github.com%2fjenkinsci%2fkubernetes-operator%2fapi%2fv1alpha2.PluginInfo">PluginInfo</a>)
</p>
<p>
</p>
<table>
<thead>
<tr>
<th>Field</th>
<th>Description</th>
</tr>
</thead>
<tbody>
<tr>
<td>
<code>versions</code></br>
<em>
<a href="#github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Version">
[][]github.com/jenkinsci/kubernetes-operator/api/v1alpha2.Version
</a>
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>id</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>message</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>url</code></br>
<em>
string
</em>
</td>
<td>
</td>
</tr>
<tr>
<td>
<code>active</code></br>
<em>
bool
</em>
</td>
<td>
</td>
</tr>
</tbody>
</table>
<hr/>
<p><em>
Generated with <code>gen-crd-api-reference-docs</code>
on git commit <code>76078d5f</code>.
</em></p>
