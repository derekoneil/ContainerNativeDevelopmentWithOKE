# Troubleshooting

## OCI Capacity

- If Terraform or Helm is unable to instantiate a compute image or a load balancer, the cause could be a service limit being exceeded in the OCI tenancy. Check the OCI console (Compute->Instances and Networking->Load Balancers) to ensure that no extra OCI components are running. If an environment needs to be deleted/cleaned and re-created, ensure after deletion that all compute instances and load balancers are in fact in the 'terminated' state in the OCI console before trying to re-create.

- Example Service Limit Error from Terraform:

  oci_core_instance.TFInstanceK8sWorker: Status: 400; Code: LimitExceeded; OPC Request ID: /223E8390CDF939FF37388D4B02B53BDC/7F5A810FFAA8D556E5A16B08270E7A25; Message: You have reached your service limit of 1 in this Availability Domain for VM.Standard1.1. Please try launching the instance in a different Availability Domain or Region, or try using a different shape. If you have reached all Service limits, please contact Oracle support to request a limit increase.


## Kubectl Errors

- Kubectl proxy not working, dashboard does not load in browser. This is usually caused by the load balancer not being fully provisioned in OCI. Verify load balancer health in OCI console (Networking->Load Balancers->Health column). If the health is 'Unknown', most likely the load balancer is still being provisioned, which can take between 5 and 15 minutes. If the health is 'Critical' for more than 10 minutes, try deleting the load balancer (... menu->Terminate) and recreating it by re-running `terraform apply` (assuming this is a terraform-created load balancer in Lab 200). Note that after recreating the load balancer, the kubeconfig file will be out of date. Instructions f for refreshing `kubectl` using `terraform output` are included in Lab 200.

  Possible errors caused by load balancer issues may look like:
  - I0309 11:30:11.494513   16565 logs.go:41] http: proxy error: read tcp 192.168.1.226:49199->129.213.67.19:443: read: connection reset by peer
  - I0309 11:30:12.670309   16565 logs.go:41] http: proxy error: EOF
