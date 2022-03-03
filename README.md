# Deploy IBM Observability by Instana

Instana is the first and only fully automated Application Performance Management (APM) solution designed specifically for the challenges of managing microservice and cloud-native applications. You can find more information about Instana at [IBM Observability by Instana Knowledge Center](https://www.ibm.com/docs/en/obi/current). 

This repository provides Ansible-way to deploy Instana on an existing single virtual machine (with 16 cores and 64 gb RAM). This is a [self-hosted container-based installation of Instana](https://www.ibm.com/docs/en/obi/current?topic=installer-container-based-installation).

### 1. Pre-requisites
Please ensure that the following pre-requisites are met before executing the ansible scripts to deploy CP4WAIOps.

1. You need an ansible-controller machine from which the scripts are executed. This could be your laptop or a dedicated linux machine. This can only be a Mac or Linux machine and NOT Windows.
2. Install Python 3.10+ on the ansible-controller. Check the version with 'python --version'.
3. Install Ansible 2.12+ on the ansible-controller.Check the version with 'ansible --version'.
4. Ensure that the Python used by Ansible matches with the Python version on the ansible-controller.
5. A sinle VM with 16 cores / 64 gb RAM and Ubuntu 20.04 is required. Ensure that it is reachable from ansible-controller.


**Notes**:
1. The scripts are tested with Python 3.10.1 and Ansible 2.12.1 on MacOS.
2. The scripts are work-in-progress and could be updated at any time.
3. The script is meant for setup of Instana sandbox environment only and not for production.


### 2. Run the scripts to deploy Instana

1. You need to clone the repository on ansible-controller machine. 

2. Open 'roles/install-instana/defaults/main.yml' file and provide your values  against the variables (replace the 'put-your-...-here' string with your value in each case).

3. Also update the FQDN or IP Address of the VM on which Instana is going to be setup in the file 'hosts'. 

4. Run the following command to execute the ansible script, which deploys Instana. 

```
ansible-playbook -i hosts install-instana.yml
```
It would take about 30 to 45 minutes for the installation to complete. Once the installation is completed, the URL to access the Instana console and the credentials to login are presented on the screen. Use them to access the console and checkout the features as described in [IBM Observability by Instana Knowledge Center](https://www.ibm.com/docs/en/obi/current).