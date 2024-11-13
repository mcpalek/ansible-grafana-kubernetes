# ansible-grafana-kubernetes
Ansible playbook for installing Prometheus and Grafana in the existing kubernetes cluster
Grafana user is admin
To get the grafana password run the command below:
kubectl get secret -n monitoring prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 --decode; echo
to 

