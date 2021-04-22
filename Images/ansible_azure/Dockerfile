FROM centos:centos7.9.2009

RUN yum check-update; \
    yum install -y gcc libffi-devel python3 epel-release; \
    yum install -y openssh-clients; \
    yum install -y sshpass; \
    yum install -y nano; \
    pip3 install --upgrade pip
RUN pip3 install ansible[azure]; \
    ansible-galaxy collection install azure.azcollection; \
    yum install -y wget; \
    wget https://raw.githubusercontent.com/ansible-collections/azure/dev/requirements-azure.txt; \
    pip3 install -r requirements-azure.txt
RUN curl https://packages.microsoft.com/config/rhel/7/prod.repo | tee /etc/yum.repos.d/microsoft.repo; \
    yum install -y powershell; \
    pwsh -c "Install-Module -Name Az -force"; \
    pwsh -c "Import-Module Az"
