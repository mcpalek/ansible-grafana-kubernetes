# ansible-grafana-kubernetes

Ansible playbook for installing Prometheus and Grafana in the existing kubernetes cluster

In the hosts.ini fili you should write the IP address of your Kubernetes master node

You can run the script using the command below:

ansible-playbook playbook.yaml -i hosts.ini  --key-file ~/.ssh/ansible --ask-become-pass


Grafana user is admin

To get the grafana password run the command below:

kubectl get secret -n monitoring prometheus-grafana -o jsonpath="{.data.admin-password}" | base64 --decode; echo

After the installation is finished you will be able to access 

      Grafana: http://<node-ip>:32000
      Prometheus: http://<node-ip>:32001
      Alertmanager: http://<node-ip>:32002

