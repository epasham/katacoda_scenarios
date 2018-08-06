#### Deploy Metricbeat

Metricbeat will automatically discover the running pods, find the proper files or ports to collect metrics from, configure Elasticsearch to parse the data, and configure Kibana with sample visualizations and dashboards by looking at the available metadata and applying technology specific modules:

`kubectl apply -f /root/course/metricbeat-kubernetes.yaml`{{execute HOST1}}

#### Verify that Filebeat is running

`kubectl get pods -n kube-system | grep metricbeat`{{execute HOST1}}

If the Filebeat pod is not running, wait a minute and retry. To see detailed information, you can run the describe command:

`kubectl describe po -l k8s-app=metricbeat -n kube-system`{{execute HOST1}}