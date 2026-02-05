```
TASK [smo_deploy : Verify custom Helm plugins are installed] *******************************************************************************
ok: [smo-node-1]

TASK [smo_deploy : Display installed Helm plugins] *****************************************************************************************
ok: [smo-node-1] => {
    "helm_plugins.stdout_lines": [
        "NAME    \tVERSION\tDESCRIPTION                                                                                         ",
        "deploy  \t1.0.0  \tinstall (upgrade if release exists) parent charty and all subcharts as separate but related releases",
        "cm-push \t0.10.3 \tPush chart package to ChartMuseum                                                                   ",
        "undeploy\t1.0.0  \tdelete parent chart and subcharts that were deployed as separate releases                           "
    ]
}

TASK [smo_deploy : Verify deploy and undeploy plugins are present] *************************************************************************
ok: [smo-node-1] => {
    "changed": false,
    "msg": "ONAP custom Helm plugins successfully installed"
}

TASK [smo_deploy : Check if helm-push plugin is installed] *********************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Install helm-push plugin] ***********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Add upstream Helm repositories] *****************************************************************************************
changed: [smo-node-1]

TASK [smo_deploy : Update Helm repositories] ***********************************************************************************************
changed: [smo-node-1]

TASK [smo_deploy : List available charts from upstream] ************************************************************************************
ok: [smo-node-1]

TASK [smo_deploy : Display available upstream charts] **************************************************************************************
ok: [smo-node-1] => {
    "msg": "Using upstream Helm repositories. Charts available: 31689"
}

TASK [smo_deploy : Check if ChartMuseum is running] ****************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Create charts directory] ************************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Start ChartMuseum container] ********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for ChartMuseum to be ready] ***************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Add local ChartMuseum repository] ***************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Build ONAP charts from source] ******************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Package and upload ONAP charts to ChartMuseum] **************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Build Non-RT RIC charts from source] ************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Package and upload Non-RT RIC charts to ChartMuseum] ********************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Update local Helm repository] *******************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : List available local charts] ********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Display available local charts] *****************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Verify Helm setup] ******************************************************************************************************
ok: [smo-node-1]

TASK [smo_deploy : Display configured Helm repositories] ***********************************************************************************
ok: [smo-node-1] => {
    "msg": [
        "Configured Helm repositories:",
        [
            "NAME                           \tURL                                                              ",
            "oran-snapshot                  \thttps://nexus3.o-ran-sc.org/repository/helm.snapshot/            ",
            "oran-release                   \thttps://nexus3.o-ran-sc.org/repository/helm.release/             ",
            "strimzi                        \thttps://strimzi.io/charts/                                       ",
            "openebs                        \thttps://openebs.github.io/openebs                                ",
            "mariadb-operator               \thttps://helm.mariadb.com/mariadb-operator                        ",
            "local                          \thttp://localhost:18080                                           ",
            "stable                         \thttps://charts.helm.sh/stable                                    ",
            "nfs-subdir-external-provisioner\thttps://kubernetes-sigs.github.io/nfs-subdir-external-provisioner",
            "bitnami                        \thttps://charts.bitnami.com/bitnami                               ",
            "onap-new                       \thttps://nexus3.onap.org/repository/onap-helm-release/            "
        ],
        "ChartMuseum enabled: False",
        "Custom Helm plugins installed: deploy, undeploy"
    ]
}

TASK [smo_deploy : Include SMO installation tasks] *****************************************************************************************
included: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml for smo-node-1

TASK [smo_deploy : Create post-renderer script directory] **********************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Check if yq is installed] ***********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Download and install yq] ************************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Verify yq installation] *************************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Display yq version] *****************************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Copy post-renderer script] **********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Check if external mappings file exists] *********************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Fail if file specified but doesn't exist] *******************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Read mappings from file] ************************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Parse mappings from file] ***********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Display file-based mappings count] **************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Combine inline and file-based mappings] *********************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Use inline mappings only] ***********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Generate post-renderer configuration] ***********************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Display post-renderer configuration summary] ****************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Determine override files based on flavor and custom settings] ***********************************************************
ok: [smo-node-1]

TASK [smo_deploy : Check if flavor override files exist] ***********************************************************************************
ok: [smo-node-1] => (item=/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml)
ok: [smo-node-1] => (item=/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml)

TASK [smo_deploy : Display override file status] *******************************************************************************************
ok: [smo-node-1] => {
    "msg": [
        "Deployment Configuration:",
        "Flavor: default",
        "Mode: release",
        "ONAP Override: /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml",
        "Non-RT RIC Override: /opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml",
        "Using ChartMuseum: False",
        "Post-Renderer: False"
    ]
}

TASK [smo_deploy : Warn if override files are missing] *************************************************************************************
skipping: [smo-node-1] => (item={'changed': False, 'stat': {'exists': True, 'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'mode': '0644', 'isdir': False, 'ischr': False, 'isblk': False, 'isreg': True, 'isfifo': False, 'islnk': False, 'issock': False, 'uid': 0, 'gid': 0, 'size': 2307, 'inode': 53346663, 'dev': 2050, 'nlink': 1, 'atime': 1770142564.3083904, 'mtime': 1770142272.6352303, 'ctime': 1770142272.6303487, 'wusr': True, 'rusr': True, 'xusr': False, 'wgrp': False, 'rgrp': True, 'xgrp': False, 'woth': False, 'roth': True, 'xoth': False, 'isuid': False, 'isgid': False, 'blocks': 8, 'block_size': 4096, 'device_type': 0, 'readable': True, 'writeable': True, 'executable': False, 'pw_name': 'root', 'gr_name': 'root', 'checksum': '20d49f4db828f1eceb81fd991b07ac74e79585f4', 'mimetype': 'text/plain', 'charset': 'us-ascii', 'version': '2566673057', 'attributes': ['extents'], 'attr_flags': 'e'}, 'invocation': {'module_args': {'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'follow': False, 'get_checksum': True, 'get_mime': True, 'get_attributes': True, 'get_selinux_context': False, 'checksum_algorithm': 'sha1'}}, 'failed': False, 'item': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'ansible_loop_var': 'item'}) 
skipping: [smo-node-1] => (item={'changed': False, 'stat': {'exists': True, 'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'mode': '0644', 'isdir': False, 'ischr': False, 'isblk': False, 'isreg': True, 'isfifo': False, 'islnk': False, 'issock': False, 'uid': 0, 'gid': 0, 'size': 6161, 'inode': 16253652, 'dev': 2050, 'nlink': 1, 'atime': 1770202734.913476, 'mtime': 1769974640.1624591, 'ctime': 1769974640.1624591, 'wusr': True, 'rusr': True, 'xusr': False, 'wgrp': False, 'rgrp': True, 'xgrp': False, 'woth': False, 'roth': True, 'xoth': False, 'isuid': False, 'isgid': False, 'blocks': 16, 'block_size': 4096, 'device_type': 0, 'readable': True, 'writeable': True, 'executable': False, 'pw_name': 'root', 'gr_name': 'root', 'checksum': 'a739d903501e1f2d8dd01fc2da808634c34aada8', 'mimetype': 'text/plain', 'charset': 'utf-8', 'version': '4032419688', 'attributes': ['extents'], 'attr_flags': 'e'}, 'invocation': {'module_args': {'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'follow': False, 'get_checksum': True, 'get_mime': True, 'get_attributes': True, 'get_selinux_context': False, 'checksum_algorithm': 'sha1'}}, 'failed': False, 'item': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'ansible_loop_var': 'item'}) 
skipping: [smo-node-1]

TASK [smo_deploy : Check if SMO is already deployed] ***************************************************************************************
ok: [smo-node-1]

TASK [smo_deploy : Remove existing Helm releases] ******************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for pods to terminate] *********************************************************************************************
skipping: [smo-node-1]

TASK [smo_deploy : Set Helm repository based on mode] **************************************************************************************
ok: [smo-node-1]

TASK [smo_deploy : Deploy ONAP components] *************************************************************************************************
[ERROR]: Task failed: Module failed: non-zero return code
Origin: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml:183:3

181   tags: install
182
183 - name: Deploy ONAP components
      ^ column 3

fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm upgrade --install onap oran-release/onap   --namespace onap  --create-namespace    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:00:28.424189", "end": "2026-02-04 12:47:36.486733", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 12:47:08.062544", "stderr": "Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided", "stderr_lines": ["Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided"], "stdout": "Release \"onap\" does not exist. Installing it now.", "stdout_lines": ["Release \"onap\" does not exist. Installing it now."]}

PLAY RECAP *********************************************************************************************************************************
smo-node-1                 : ok=44   changed=12   unreachable=0    failed=1    skipped=45   rescued=0    ignored=0   

 source /home/agnik/Desktop/deployoran/smoansible3/smo-install-ansible/ansible-venv/bin/activate && ansible-playbook -i inventory.ini deploy-smo.yml 2>&1 | tee /tmp/ansible-full.log | tail -200

TASK [smo_deploy : Verify custom Helm plugins are installed] *******************
ok: [smo-node-1]

TASK [smo_deploy : Display installed Helm plugins] *****************************
ok: [smo-node-1] => {
    "helm_plugins.stdout_lines": [
        "NAME    \tVERSION\tDESCRIPTION                                                                                         ",
        "deploy  \t1.0.0  \tinstall (upgrade if release exists) parent charty and all subcharts as separate but related releases",
        "cm-push \t0.10.3 \tPush chart package to ChartMuseum                                                                   ",
        "undeploy\t1.0.0  \tdelete parent chart and subcharts that were deployed as separate releases                           "
    ]
}

TASK [smo_deploy : Verify deploy and undeploy plugins are present] *************
ok: [smo-node-1] => {
    "changed": false,
    "msg": "ONAP custom Helm plugins successfully installed"
}

TASK [smo_deploy : Check if helm-push plugin is installed] *********************
skipping: [smo-node-1]

TASK [smo_deploy : Install helm-push plugin] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Add upstream Helm repositories] *****************************
changed: [smo-node-1]

TASK [smo_deploy : Update Helm repositories] ***********************************
changed: [smo-node-1]

TASK [smo_deploy : List available charts from upstream] ************************
ok: [smo-node-1]

TASK [smo_deploy : Display available upstream charts] **************************
ok: [smo-node-1] => {
    "msg": "Using upstream Helm repositories. Charts available: 31689"
}

TASK [smo_deploy : Check if ChartMuseum is running] ****************************
skipping: [smo-node-1]

TASK [smo_deploy : Create charts directory] ************************************
skipping: [smo-node-1]

TASK [smo_deploy : Start ChartMuseum container] ********************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for ChartMuseum to be ready] ***************************
skipping: [smo-node-1]

TASK [smo_deploy : Add local ChartMuseum repository] ***************************
skipping: [smo-node-1]

TASK [smo_deploy : Build ONAP charts from source] ******************************
skipping: [smo-node-1]

TASK [smo_deploy : Package and upload ONAP charts to ChartMuseum] **************
skipping: [smo-node-1]

TASK [smo_deploy : Build Non-RT RIC charts from source] ************************
skipping: [smo-node-1]

TASK [smo_deploy : Package and upload Non-RT RIC charts to ChartMuseum] ********
skipping: [smo-node-1]

TASK [smo_deploy : Update local Helm repository] *******************************
skipping: [smo-node-1]

TASK [smo_deploy : List available local charts] ********************************
skipping: [smo-node-1]

TASK [smo_deploy : Display available local charts] *****************************
skipping: [smo-node-1]

TASK [smo_deploy : Verify Helm setup] ******************************************
ok: [smo-node-1]

TASK [smo_deploy : Display configured Helm repositories] ***********************
ok: [smo-node-1] => {
    "msg": [
        "Configured Helm repositories:",
        [
            "NAME                           \tURL                                                              ",
            "oran-snapshot                  \thttps://nexus3.o-ran-sc.org/repository/helm.snapshot/            ",
            "oran-release                   \thttps://nexus3.o-ran-sc.org/repository/helm.release/             ",
            "strimzi                        \thttps://strimzi.io/charts/                                       ",
            "openebs                        \thttps://openebs.github.io/openebs                                ",
            "mariadb-operator               \thttps://helm.mariadb.com/mariadb-operator                        ",
            "local                          \thttp://localhost:18080                                           ",
            "stable                         \thttps://charts.helm.sh/stable                                    ",
            "nfs-subdir-external-provisioner\thttps://kubernetes-sigs.github.io/nfs-subdir-external-provisioner",
            "bitnami                        \thttps://charts.bitnami.com/bitnami                               ",
            "onap-new                       \thttps://nexus3.onap.org/repository/onap-helm-release/            "
        ],
        "ChartMuseum enabled: False",
        "Custom Helm plugins installed: deploy, undeploy"
    ]
}

TASK [smo_deploy : Include SMO installation tasks] *****************************
included: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml for smo-node-1

TASK [smo_deploy : Create post-renderer script directory] **********************
skipping: [smo-node-1]

TASK [smo_deploy : Check if yq is installed] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Download and install yq] ************************************
skipping: [smo-node-1]

TASK [smo_deploy : Verify yq installation] *************************************
skipping: [smo-node-1]

TASK [smo_deploy : Display yq version] *****************************************
skipping: [smo-node-1]

TASK [smo_deploy : Copy post-renderer script] **********************************
skipping: [smo-node-1]

TASK [smo_deploy : Check if external mappings file exists] *********************
skipping: [smo-node-1]

TASK [smo_deploy : Fail if file specified but doesn't exist] *******************
skipping: [smo-node-1]

TASK [smo_deploy : Read mappings from file] ************************************
skipping: [smo-node-1]

TASK [smo_deploy : Parse mappings from file] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Display file-based mappings count] **************************
skipping: [smo-node-1]

TASK [smo_deploy : Combine inline and file-based mappings] *********************
skipping: [smo-node-1]

TASK [smo_deploy : Use inline mappings only] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Generate post-renderer configuration] ***********************
skipping: [smo-node-1]

TASK [smo_deploy : Display post-renderer configuration summary] ****************
skipping: [smo-node-1]

TASK [smo_deploy : Determine override files based on flavor and custom settings] ***
ok: [smo-node-1]

TASK [smo_deploy : Check if flavor override files exist] ***********************
ok: [smo-node-1] => (item=/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml)
ok: [smo-node-1] => (item=/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml)

TASK [smo_deploy : Display override file status] *******************************
ok: [smo-node-1] => {
    "msg": [
        "Deployment Configuration:",
        "Flavor: default",
        "Mode: release",
        "ONAP Override: /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml",
        "Non-RT RIC Override: /opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml",
        "Using ChartMuseum: False",
        "Post-Renderer: False"
    ]
}

TASK [smo_deploy : Warn if override files are missing] *************************
skipping: [smo-node-1] => (item={'changed': False, 'stat': {'exists': True, 'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'mode': '0644', 'isdir': False, 'ischr': False, 'isblk': False, 'isreg': True, 'isfifo': False, 'islnk': False, 'issock': False, 'uid': 0, 'gid': 0, 'size': 2307, 'inode': 53346663, 'dev': 2050, 'nlink': 1, 'atime': 1770142564.3083904, 'mtime': 1770142272.6352303, 'ctime': 1770142272.6303487, 'wusr': True, 'rusr': True, 'xusr': False, 'wgrp': False, 'rgrp': True, 'xgrp': False, 'woth': False, 'roth': True, 'xoth': False, 'isuid': False, 'isgid': False, 'blocks': 8, 'block_size': 4096, 'device_type': 0, 'readable': True, 'writeable': True, 'executable': False, 'pw_name': 'root', 'gr_name': 'root', 'checksum': '20d49f4db828f1eceb81fd991b07ac74e79585f4', 'mimetype': 'text/plain', 'charset': 'us-ascii', 'version': '2566673057', 'attributes': ['extents'], 'attr_flags': 'e'}, 'invocation': {'module_args': {'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'follow': False, 'get_checksum': True, 'get_mime': True, 'get_attributes': True, 'get_selinux_context': False, 'checksum_algorithm': 'sha1'}}, 'failed': False, 'item': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'ansible_loop_var': 'item'}) 
skipping: [smo-node-1] => (item={'changed': False, 'stat': {'exists': True, 'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'mode': '0644', 'isdir': False, 'ischr': False, 'isblk': False, 'isreg': True, 'isfifo': False, 'islnk': False, 'issock': False, 'uid': 0, 'gid': 0, 'size': 6161, 'inode': 16253652, 'dev': 2050, 'nlink': 1, 'atime': 1770202734.913476, 'mtime': 1769974640.1624591, 'ctime': 1769974640.1624591, 'wusr': True, 'rusr': True, 'xusr': False, 'wgrp': False, 'rgrp': True, 'xgrp': False, 'woth': False, 'roth': True, 'xoth': False, 'isuid': False, 'isgid': False, 'blocks': 16, 'block_size': 4096, 'device_type': 0, 'readable': True, 'writeable': True, 'executable': False, 'pw_name': 'root', 'gr_name': 'root', 'checksum': 'a739d903501e1f2d8dd01fc2da808634c34aada8', 'mimetype': 'text/plain', 'charset': 'utf-8', 'version': '4032419688', 'attributes': ['extents'], 'attr_flags': 'e'}, 'invocation': {'module_args': {'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'follow': False, 'get_checksum': True, 'get_mime': True, 'get_attributes': True, 'get_selinux_context': False, 'checksum_algorithm': 'sha1'}}, 'failed': False, 'item': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'ansible_loop_var': 'item'}) 
skipping: [smo-node-1]

TASK [smo_deploy : Check if SMO is already deployed] ***************************
ok: [smo-node-1]

TASK [smo_deploy : Remove existing Helm releases] ******************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for pods to terminate] *********************************
skipping: [smo-node-1]

TASK [smo_deploy : Set Helm repository based on mode] **************************
ok: [smo-node-1]

TASK [smo_deploy : Deploy ONAP components] *************************************
[ERROR]: Task failed: Module failed: non-zero return code
Origin: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml:183:3

181   tags: install
182
183 - name: Deploy ONAP components
      ^ column 3

fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm upgrade --install onap oran-release/onap   --namespace onap  --create-namespace    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:00:26.048196", "end": "2026-02-04 13:11:57.361369", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 13:11:31.313173", "stderr": "Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided", "stderr_lines": ["Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided"], "stdout": "Release \"onap\" does not exist. Installing it now.", "stdout_lines": ["Release \"onap\" does not exist. Installing it now."]}

PLAY RECAP *********************************************************************
smo-node-1                 : ok=44   changed=6    unreachable=0    failed=1    skipped=45   rescued=0    ignored=0   

(ansible-venv) agnik@agnik-Alpha-15-A3DD:~/Desktop/deployoran/11ansable/smo-install-ansible$ grep -A 30 "FAILED\|fatal:" /tmp/ansible-full.log | head -50
fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm upgrade --install onap oran-release/onap   --namespace onap  --create-namespace    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:00:26.048196", "end": "2026-02-04 13:11:57.361369", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 13:11:31.313173", "stderr": "Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided", "stderr_lines": ["Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided"], "stdout": "Release \"onap\" does not exist. Installing it now.", "stdout_lines": ["Release \"onap\" does not exist. Installing it now."]}

PLAY RECAP *********************************************************************
smo-node-1                 : ok=44   changed=6    unreachable=0    failed=1    skipped=45   rescued=0    ignored=0   

(ansible-venv) agnik@agnik-Alpha-15-A3DD:~/Desktop/deployoran/11ansable/smo-install-ansible$ tail -100 /tmp/ansible-full.log | grep -B 20 "PLAY RECAP"
TASK [smo_deploy : Remove existing Helm releases] ******************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for pods to terminate] *********************************
skipping: [smo-node-1]

TASK [smo_deploy : Set Helm repository based on mode] **************************
ok: [smo-node-1]

TASK [smo_deploy : Deploy ONAP components] *************************************
[ERROR]: Task failed: Module failed: non-zero return code
Origin: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml:183:3

181   tags: install
182
183 - name: Deploy ONAP components
      ^ column 3

fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm upgrade --install onap oran-release/onap   --namespace onap  --create-namespace    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:00:26.048196", "end": "2026-02-04 13:11:57.361369", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 13:11:31.313173", "stderr": "Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided", "stderr_lines": ["Error: execution error at (onap/charts/policy/charts/postgres/templates/secrets.yaml:16:3): masterPassword not provided"], "stdout": "Release \"onap\" does not exist. Installing it now.", "stdout_lines": ["Release \"onap\" does not exist. Installing it now."]}

PLAY RECAP *********************************************************************
(ansible-venv) agnik@agnik-Alpha-15-A3DD:~/Desktop/deployoran/11ansable/smo-install-ansible$ source /home/agnik/Desktop/deployoran/smoansible3/smo-install-ansible/ansible-venv/bin/activate && ansible-playbook -i inventory.ini deploy-smo.yml 2>&1 | tee /tmp/ansible-deploy-fixed.log | tail -200

TASK [smo_deploy : Verify custom Helm plugins are installed] *******************
ok: [smo-node-1]

TASK [smo_deploy : Display installed Helm plugins] *****************************
ok: [smo-node-1] => {
    "helm_plugins.stdout_lines": [
        "NAME    \tVERSION\tDESCRIPTION                                                                                         ",
        "deploy  \t1.0.0  \tinstall (upgrade if release exists) parent charty and all subcharts as separate but related releases",
        "cm-push \t0.10.3 \tPush chart package to ChartMuseum                                                                   ",
        "undeploy\t1.0.0  \tdelete parent chart and subcharts that were deployed as separate releases                           "
    ]
}

TASK [smo_deploy : Verify deploy and undeploy plugins are present] *************
ok: [smo-node-1] => {
    "changed": false,
    "msg": "ONAP custom Helm plugins successfully installed"
}

TASK [smo_deploy : Check if helm-push plugin is installed] *********************
skipping: [smo-node-1]

TASK [smo_deploy : Install helm-push plugin] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Add upstream Helm repositories] *****************************
changed: [smo-node-1]

TASK [smo_deploy : Update Helm repositories] ***********************************
changed: [smo-node-1]

TASK [smo_deploy : List available charts from upstream] ************************
ok: [smo-node-1]

TASK [smo_deploy : Display available upstream charts] **************************
ok: [smo-node-1] => {
    "msg": "Using upstream Helm repositories. Charts available: 31689"
}

TASK [smo_deploy : Check if ChartMuseum is running] ****************************
skipping: [smo-node-1]

TASK [smo_deploy : Create charts directory] ************************************
skipping: [smo-node-1]

TASK [smo_deploy : Start ChartMuseum container] ********************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for ChartMuseum to be ready] ***************************
skipping: [smo-node-1]

TASK [smo_deploy : Add local ChartMuseum repository] ***************************
skipping: [smo-node-1]

TASK [smo_deploy : Build ONAP charts from source] ******************************
skipping: [smo-node-1]

TASK [smo_deploy : Package and upload ONAP charts to ChartMuseum] **************
skipping: [smo-node-1]

TASK [smo_deploy : Build Non-RT RIC charts from source] ************************
skipping: [smo-node-1]

TASK [smo_deploy : Package and upload Non-RT RIC charts to ChartMuseum] ********
skipping: [smo-node-1]

TASK [smo_deploy : Update local Helm repository] *******************************
skipping: [smo-node-1]

TASK [smo_deploy : List available local charts] ********************************
skipping: [smo-node-1]

TASK [smo_deploy : Display available local charts] *****************************
skipping: [smo-node-1]

TASK [smo_deploy : Verify Helm setup] ******************************************
ok: [smo-node-1]

TASK [smo_deploy : Display configured Helm repositories] ***********************
ok: [smo-node-1] => {
    "msg": [
        "Configured Helm repositories:",
        [
            "NAME                           \tURL                                                              ",
            "oran-snapshot                  \thttps://nexus3.o-ran-sc.org/repository/helm.snapshot/            ",
            "oran-release                   \thttps://nexus3.o-ran-sc.org/repository/helm.release/             ",
            "strimzi                        \thttps://strimzi.io/charts/                                       ",
            "openebs                        \thttps://openebs.github.io/openebs                                ",
            "mariadb-operator               \thttps://helm.mariadb.com/mariadb-operator                        ",
            "local                          \thttp://localhost:18080                                           ",
            "stable                         \thttps://charts.helm.sh/stable                                    ",
            "nfs-subdir-external-provisioner\thttps://kubernetes-sigs.github.io/nfs-subdir-external-provisioner",
            "bitnami                        \thttps://charts.bitnami.com/bitnami                               ",
            "onap-new                       \thttps://nexus3.onap.org/repository/onap-helm-release/            "
        ],
        "ChartMuseum enabled: False",
        "Custom Helm plugins installed: deploy, undeploy"
    ]
}

TASK [smo_deploy : Include SMO installation tasks] *****************************
included: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml for smo-node-1

TASK [smo_deploy : Create post-renderer script directory] **********************
skipping: [smo-node-1]

TASK [smo_deploy : Check if yq is installed] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Download and install yq] ************************************
skipping: [smo-node-1]

TASK [smo_deploy : Verify yq installation] *************************************
skipping: [smo-node-1]

TASK [smo_deploy : Display yq version] *****************************************
skipping: [smo-node-1]

TASK [smo_deploy : Copy post-renderer script] **********************************
skipping: [smo-node-1]

TASK [smo_deploy : Check if external mappings file exists] *********************
skipping: [smo-node-1]

TASK [smo_deploy : Fail if file specified but doesn't exist] *******************
skipping: [smo-node-1]

TASK [smo_deploy : Read mappings from file] ************************************
skipping: [smo-node-1]

TASK [smo_deploy : Parse mappings from file] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Display file-based mappings count] **************************
skipping: [smo-node-1]

TASK [smo_deploy : Combine inline and file-based mappings] *********************
skipping: [smo-node-1]

TASK [smo_deploy : Use inline mappings only] ***********************************
skipping: [smo-node-1]

TASK [smo_deploy : Generate post-renderer configuration] ***********************
skipping: [smo-node-1]

TASK [smo_deploy : Display post-renderer configuration summary] ****************
skipping: [smo-node-1]

TASK [smo_deploy : Determine override files based on flavor and custom settings] ***
ok: [smo-node-1]

TASK [smo_deploy : Check if flavor override files exist] ***********************
ok: [smo-node-1] => (item=/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml)
ok: [smo-node-1] => (item=/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml)

TASK [smo_deploy : Display override file status] *******************************
ok: [smo-node-1] => {
    "msg": [
        "Deployment Configuration:",
        "Flavor: default",
        "Mode: release",
        "ONAP Override: /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml",
        "Non-RT RIC Override: /opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml",
        "Using ChartMuseum: False",
        "Post-Renderer: False"
    ]
}

TASK [smo_deploy : Warn if override files are missing] *************************
skipping: [smo-node-1] => (item={'changed': False, 'stat': {'exists': True, 'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'mode': '0644', 'isdir': False, 'ischr': False, 'isblk': False, 'isreg': True, 'isfifo': False, 'islnk': False, 'issock': False, 'uid': 0, 'gid': 0, 'size': 2307, 'inode': 53346663, 'dev': 2050, 'nlink': 1, 'atime': 1770142564.3083904, 'mtime': 1770142272.6352303, 'ctime': 1770142272.6303487, 'wusr': True, 'rusr': True, 'xusr': False, 'wgrp': False, 'rgrp': True, 'xgrp': False, 'woth': False, 'roth': True, 'xoth': False, 'isuid': False, 'isgid': False, 'blocks': 8, 'block_size': 4096, 'device_type': 0, 'readable': True, 'writeable': True, 'executable': False, 'pw_name': 'root', 'gr_name': 'root', 'checksum': '20d49f4db828f1eceb81fd991b07ac74e79585f4', 'mimetype': 'text/plain', 'charset': 'us-ascii', 'version': '2566673057', 'attributes': ['extents'], 'attr_flags': 'e'}, 'invocation': {'module_args': {'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'follow': False, 'get_checksum': True, 'get_mime': True, 'get_attributes': True, 'get_selinux_context': False, 'checksum_algorithm': 'sha1'}}, 'failed': False, 'item': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml', 'ansible_loop_var': 'item'}) 
skipping: [smo-node-1] => (item={'changed': False, 'stat': {'exists': True, 'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'mode': '0644', 'isdir': False, 'ischr': False, 'isblk': False, 'isreg': True, 'isfifo': False, 'islnk': False, 'issock': False, 'uid': 0, 'gid': 0, 'size': 6161, 'inode': 16253652, 'dev': 2050, 'nlink': 1, 'atime': 1770202734.913476, 'mtime': 1769974640.1624591, 'ctime': 1769974640.1624591, 'wusr': True, 'rusr': True, 'xusr': False, 'wgrp': False, 'rgrp': True, 'xgrp': False, 'woth': False, 'roth': True, 'xoth': False, 'isuid': False, 'isgid': False, 'blocks': 16, 'block_size': 4096, 'device_type': 0, 'readable': True, 'writeable': True, 'executable': False, 'pw_name': 'root', 'gr_name': 'root', 'checksum': 'a739d903501e1f2d8dd01fc2da808634c34aada8', 'mimetype': 'text/plain', 'charset': 'utf-8', 'version': '4032419688', 'attributes': ['extents'], 'attr_flags': 'e'}, 'invocation': {'module_args': {'path': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'follow': False, 'get_checksum': True, 'get_mime': True, 'get_attributes': True, 'get_selinux_context': False, 'checksum_algorithm': 'sha1'}}, 'failed': False, 'item': '/opt/o-ran-sc/it-dep/smo-install/helm-override/default/oran-override.yaml', 'ansible_loop_var': 'item'}) 
skipping: [smo-node-1]

TASK [smo_deploy : Check if SMO is already deployed] ***************************
ok: [smo-node-1]

TASK [smo_deploy : Remove existing Helm releases] ******************************
skipping: [smo-node-1]

TASK [smo_deploy : Wait for pods to terminate] *********************************
skipping: [smo-node-1]

TASK [smo_deploy : Set Helm repository based on mode] **************************
ok: [smo-node-1]

TASK [smo_deploy : Deploy ONAP components] *************************************
[ERROR]: Task failed: Module failed: non-zero return code
Origin: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml:183:3

181   tags: install
182
183 - name: Deploy ONAP components
      ^ column 3

fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm deploy onap oran-release/onap   --namespace onap    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:10:15.421107", "end": "2026-02-04 13:32:58.514031", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 13:22:43.092924", "stderr": "history.go:56: 2026-02-04 13:22:50.197298951 +0000 UTC m=+0.113637452 [debug] getting history for release onap\ninstall.go:225: 2026-02-04 13:22:50.201819247 +0000 UTC m=+0.118157753 [debug] Original chart version: \"\"\ninstall.go:242: 2026-02-04 13:22:50.201867832 +0000 UTC m=+0.118206339 [debug] CHART PATH: /root/.local/share/helm/plugins/deploy/cache/onap\n\nError: plugin \"deploy\" exited with error", "stderr_lines": ["history.go:56: 2026-02-04 13:22:50.197298951 +0000 UTC m=+0.113637452 [debug] getting history for release onap", "install.go:225: 2026-02-04 13:22:50.201819247 +0000 UTC m=+0.118157753 [debug] Original chart version: \"\"", "install.go:242: 2026-02-04 13:22:50.201867832 +0000 UTC m=+0.118206339 [debug] CHART PATH: /root/.local/share/helm/plugins/deploy/cache/onap", "", "Error: plugin \"deploy\" exited with error"], "stdout": "v3.18.6\nUse cache dir: /root/.local/share/helm/plugins/deploy/cache\n0\n0\n0\n0\nfetching oran-release/onap\nrelease \"onap\" deployed\nrelease \"onap-roles-wrapper\" deployed\nrelease \"onap-repository-wrapper\" deployed\nrelease \"onap-strimzi\" deployed\nwaiting for onap-strimzi-entity-operator to be deployed\nonap-strimzi-entity-operator not found. Retry 1/60\nonap-strimzi-entity-operator not found. Retry 2/60\nonap-strimzi-entity-operator not found. Retry 3/60\nonap-strimzi-entity-operator not found. Retry 4/60\nonap-strimzi-entity-operator not found. Retry 5/60\nonap-strimzi-entity-operator not found. Retry 6/60\nonap-strimzi-entity-operator not found. Retry 7/60\nonap-strimzi-entity-operator not found. Retry 8/60\nonap-strimzi-entity-operator not found. Retry 9/60\nonap-strimzi-entity-operator not found. Retry 10/60\nonap-strimzi-entity-operator not found. Retry 11/60\nonap-strimzi-entity-operator not found. Retry 12/60\nonap-strimzi-entity-operator not found. Retry 13/60\nonap-strimzi-entity-operator not found. Retry 14/60\nonap-strimzi-entity-operator not found. Retry 15/60\nonap-strimzi-entity-operator not found. Retry 16/60\nonap-strimzi-entity-operator not found. Retry 17/60\nonap-strimzi-entity-operator not found. Retry 18/60\nonap-strimzi-entity-operator not found. Retry 19/60\nonap-strimzi-entity-operator not found. Retry 20/60\nonap-strimzi-entity-operator not found. Retry 21/60\nonap-strimzi-entity-operator not found. Retry 22/60\nonap-strimzi-entity-operator not found. Retry 23/60\nonap-strimzi-entity-operator not found. Retry 24/60\nonap-strimzi-entity-operator not found. Retry 25/60\nonap-strimzi-entity-operator not found. Retry 26/60\nonap-strimzi-entity-operator not found. Retry 27/60\nonap-strimzi-entity-operator not found. Retry 28/60\nonap-strimzi-entity-operator not found. Retry 29/60\nonap-strimzi-entity-operator not found. Retry 30/60\nonap-strimzi-entity-operator not found. Retry 31/60\nonap-strimzi-entity-operator not found. Retry 32/60\nonap-strimzi-entity-operator not found. Retry 33/60\nonap-strimzi-entity-operator not found. Retry 34/60\nonap-strimzi-entity-operator not found. Retry 35/60\nonap-strimzi-entity-operator not found. Retry 36/60\nonap-strimzi-entity-operator not found. Retry 37/60\nonap-strimzi-entity-operator not found. Retry 38/60\nonap-strimzi-entity-operator not found. Retry 39/60\nonap-strimzi-entity-operator not found. Retry 40/60\nonap-strimzi-entity-operator not found. Retry 41/60\nonap-strimzi-entity-operator not found. Retry 42/60\nonap-strimzi-entity-operator not found. Retry 43/60\nonap-strimzi-entity-operator not found. Retry 44/60\nonap-strimzi-entity-operator not found. Retry 45/60\nonap-strimzi-entity-operator not found. Retry 46/60\nonap-strimzi-entity-operator not found. Retry 47/60\nonap-strimzi-entity-operator not found. Retry 48/60\nonap-strimzi-entity-operator not found. Retry 49/60\nonap-strimzi-entity-operator not found. Retry 50/60\nonap-strimzi-entity-operator not found. Retry 51/60\nonap-strimzi-entity-operator not found. Retry 52/60\nonap-strimzi-entity-operator not found. Retry 53/60\nonap-strimzi-entity-operator not found. Retry 54/60\nonap-strimzi-entity-operator not found. Retry 55/60\nonap-strimzi-entity-operator not found. Retry 56/60\nonap-strimzi-entity-operator not found. Retry 57/60\nonap-strimzi-entity-operator not found. Retry 58/60\nonap-strimzi-entity-operator not found. Retry 59/60\nonap-strimzi-entity-operator not found. Retry 60/60", "stdout_lines": ["v3.18.6", "Use cache dir: /root/.local/share/helm/plugins/deploy/cache", "0", "0", "0", "0", "fetching oran-release/onap", "release \"onap\" deployed", "release \"onap-roles-wrapper\" deployed", "release \"onap-repository-wrapper\" deployed", "release \"onap-strimzi\" deployed", "waiting for onap-strimzi-entity-operator to be deployed", "onap-strimzi-entity-operator not found. Retry 1/60", "onap-strimzi-entity-operator not found. Retry 2/60", "onap-strimzi-entity-operator not found. Retry 3/60", "onap-strimzi-entity-operator not found. Retry 4/60", "onap-strimzi-entity-operator not found. Retry 5/60", "onap-strimzi-entity-operator not found. Retry 6/60", "onap-strimzi-entity-operator not found. Retry 7/60", "onap-strimzi-entity-operator not found. Retry 8/60", "onap-strimzi-entity-operator not found. Retry 9/60", "onap-strimzi-entity-operator not found. Retry 10/60", "onap-strimzi-entity-operator not found. Retry 11/60", "onap-strimzi-entity-operator not found. Retry 12/60", "onap-strimzi-entity-operator not found. Retry 13/60", "onap-strimzi-entity-operator not found. Retry 14/60", "onap-strimzi-entity-operator not found. Retry 15/60", "onap-strimzi-entity-operator not found. Retry 16/60", "onap-strimzi-entity-operator not found. Retry 17/60", "onap-strimzi-entity-operator not found. Retry 18/60", "onap-strimzi-entity-operator not found. Retry 19/60", "onap-strimzi-entity-operator not found. Retry 20/60", "onap-strimzi-entity-operator not found. Retry 21/60", "onap-strimzi-entity-operator not found. Retry 22/60", "onap-strimzi-entity-operator not found. Retry 23/60", "onap-strimzi-entity-operator not found. Retry 24/60", "onap-strimzi-entity-operator not found. Retry 25/60", "onap-strimzi-entity-operator not found. Retry 26/60", "onap-strimzi-entity-operator not found. Retry 27/60", "onap-strimzi-entity-operator not found. Retry 28/60", "onap-strimzi-entity-operator not found. Retry 29/60", "onap-strimzi-entity-operator not found. Retry 30/60", "onap-strimzi-entity-operator not found. Retry 31/60", "onap-strimzi-entity-operator not found. Retry 32/60", "onap-strimzi-entity-operator not found. Retry 33/60", "onap-strimzi-entity-operator not found. Retry 34/60", "onap-strimzi-entity-operator not found. Retry 35/60", "onap-strimzi-entity-operator not found. Retry 36/60", "onap-strimzi-entity-operator not found. Retry 37/60", "onap-strimzi-entity-operator not found. Retry 38/60", "onap-strimzi-entity-operator not found. Retry 39/60", "onap-strimzi-entity-operator not found. Retry 40/60", "onap-strimzi-entity-operator not found. Retry 41/60", "onap-strimzi-entity-operator not found. Retry 42/60", "onap-strimzi-entity-operator not found. Retry 43/60", "onap-strimzi-entity-operator not found. Retry 44/60", "onap-strimzi-entity-operator not found. Retry 45/60", "onap-strimzi-entity-operator not found. Retry 46/60", "onap-strimzi-entity-operator not found. Retry 47/60", "onap-strimzi-entity-operator not found. Retry 48/60", "onap-strimzi-entity-operator not found. Retry 49/60", "onap-strimzi-entity-operator not found. Retry 50/60", "onap-strimzi-entity-operator not found. Retry 51/60", "onap-strimzi-entity-operator not found. Retry 52/60", "onap-strimzi-entity-operator not found. Retry 53/60", "onap-strimzi-entity-operator not found. Retry 54/60", "onap-strimzi-entity-operator not found. Retry 55/60", "onap-strimzi-entity-operator not found. Retry 56/60", "onap-strimzi-entity-operator not found. Retry 57/60", "onap-strimzi-entity-operator not found. Retry 58/60", "onap-strimzi-entity-operator not found. Retry 59/60", "onap-strimzi-entity-operator not found. Retry 60/60"]}

PLAY RECAP *********************************************************************
smo-node-1                 : ok=44   changed=6    unreachable=0    failed=1    skipped=45   rescued=0    ignored=0   

(ansible-venv) agnik@agnik-Alpha-15-A3DD:~/Desktop/deployoran/11ansable/smo-install-ansible$ grep -i "fatal\|error" /tmp/ansible-deploy-fixed.log | tail -30
[ERROR]: Task failed: Module failed: non-zero return code
fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm deploy onap oran-release/onap   --namespace onap    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:10:15.421107", "end": "2026-02-04 13:32:58.514031", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 13:22:43.092924", "stderr": "history.go:56: 2026-02-04 13:22:50.197298951 +0000 UTC m=+0.113637452 [debug] getting history for release onap\ninstall.go:225: 2026-02-04 13:22:50.201819247 +0000 UTC m=+0.118157753 [debug] Original chart version: \"\"\ninstall.go:242: 2026-02-04 13:22:50.201867832 +0000 UTC m=+0.118206339 [debug] CHART PATH: /root/.local/share/helm/plugins/deploy/cache/onap\n\nError: plugin \"deploy\" exited with error", "stderr_lines": ["history.go:56: 2026-02-04 13:22:50.197298951 +0000 UTC m=+0.113637452 [debug] getting history for release onap", "install.go:225: 2026-02-04 13:22:50.201819247 +0000 UTC m=+0.118157753 [debug] Original chart version: \"\"", "install.go:242: 2026-02-04 13:22:50.201867832 +0000 UTC m=+0.118206339 [debug] CHART PATH: /root/.local/share/helm/plugins/deploy/cache/onap", "", "Error: plugin \"deploy\" exited with error"], "stdout": "v3.18.6\nUse cache dir: /root/.local/share/helm/plugins/deploy/cache\n0\n0\n0\n0\nfetching oran-release/onap\nrelease \"onap\" deployed\nrelease \"onap-roles-wrapper\" deployed\nrelease \"onap-repository-wrapper\" deployed\nrelease \"onap-strimzi\" deployed\nwaiting for onap-strimzi-entity-operator to be deployed\nonap-strimzi-entity-operator not found. Retry 1/60\nonap-strimzi-entity-operator not found. Retry 2/60\nonap-strimzi-entity-operator not found. Retry 3/60\nonap-strimzi-entity-operator not found. Retry 4/60\nonap-strimzi-entity-operator not found. Retry 5/60\nonap-strimzi-entity-operator not found. Retry 6/60\nonap-strimzi-entity-operator not found. Retry 7/60\nonap-strimzi-entity-operator not found. Retry 8/60\nonap-strimzi-entity-operator not found. Retry 9/60\nonap-strimzi-entity-operator not found. Retry 10/60\nonap-strimzi-entity-operator not found. Retry 11/60\nonap-strimzi-entity-operator not found. Retry 12/60\nonap-strimzi-entity-operator not found. Retry 13/60\nonap-strimzi-entity-operator not found. Retry 14/60\nonap-strimzi-entity-operator not found. Retry 15/60\nonap-strimzi-entity-operator not found. Retry 16/60\nonap-strimzi-entity-operator not found. Retry 17/60\nonap-strimzi-entity-operator not found. Retry 18/60\nonap-strimzi-entity-operator not found. Retry 19/60\nonap-strimzi-entity-operator not found. Retry 20/60\nonap-strimzi-entity-operator not found. Retry 21/60\nonap-strimzi-entity-operator not found. Retry 22/60\nonap-strimzi-entity-operator not found. Retry 23/60\nonap-strimzi-entity-operator not found. Retry 24/60\nonap-strimzi-entity-operator not found. Retry 25/60\nonap-strimzi-entity-operator not found. Retry 26/60\nonap-strimzi-entity-operator not found. Retry 27/60\nonap-strimzi-entity-operator not found. Retry 28/60\nonap-strimzi-entity-operator not found. Retry 29/60\nonap-strimzi-entity-operator not found. Retry 30/60\nonap-strimzi-entity-operator not found. Retry 31/60\nonap-strimzi-entity-operator not found. Retry 32/60\nonap-strimzi-entity-operator not found. Retry 33/60\nonap-strimzi-entity-operator not found. Retry 34/60\nonap-strimzi-entity-operator not found. Retry 35/60\nonap-strimzi-entity-operator not found. Retry 36/60\nonap-strimzi-entity-operator not found. Retry 37/60\nonap-strimzi-entity-operator not found. Retry 38/60\nonap-strimzi-entity-operator not found. Retry 39/60\nonap-strimzi-entity-operator not found. Retry 40/60\nonap-strimzi-entity-operator not found. Retry 41/60\nonap-strimzi-entity-operator not found. Retry 42/60\nonap-strimzi-entity-operator not found. Retry 43/60\nonap-strimzi-entity-operator not found. Retry 44/60\nonap-strimzi-entity-operator not found. Retry 45/60\nonap-strimzi-entity-operator not found. Retry 46/60\nonap-strimzi-entity-operator not found. Retry 47/60\nonap-strimzi-entity-operator not found. Retry 48/60\nonap-strimzi-entity-operator not found. Retry 49/60\nonap-strimzi-entity-operator not found. Retry 50/60\nonap-strimzi-entity-operator not found. Retry 51/60\nonap-strimzi-entity-operator not found. Retry 52/60\nonap-strimzi-entity-operator not found. Retry 53/60\nonap-strimzi-entity-operator not found. Retry 54/60\nonap-strimzi-entity-operator not found. Retry 55/60\nonap-strimzi-entity-operator not found. Retry 56/60\nonap-strimzi-entity-operator not found. Retry 57/60\nonap-strimzi-entity-operator not found. Retry 58/60\nonap-strimzi-entity-operator not found. Retry 59/60\nonap-strimzi-entity-operator not found. Retry 60/60", "stdout_lines": ["v3.18.6", "Use cache dir: /root/.local/share/helm/plugins/deploy/cache", "0", "0", "0", "0", "fetching oran-release/onap", "release \"onap\" deployed", "release \"onap-roles-wrapper\" deployed", "release \"onap-repository-wrapper\" deployed", "release \"onap-strimzi\" deployed", "waiting for onap-strimzi-entity-operator to be deployed", "onap-strimzi-entity-operator not found. Retry 1/60", "onap-strimzi-entity-operator not found. Retry 2/60", "onap-strimzi-entity-operator not found. Retry 3/60", "onap-strimzi-entity-operator not found. Retry 4/60", "onap-strimzi-entity-operator not found. Retry 5/60", "onap-strimzi-entity-operator not found. Retry 6/60", "onap-strimzi-entity-operator not found. Retry 7/60", "onap-strimzi-entity-operator not found. Retry 8/60", "onap-strimzi-entity-operator not found. Retry 9/60", "onap-strimzi-entity-operator not found. Retry 10/60", "onap-strimzi-entity-operator not found. Retry 11/60", "onap-strimzi-entity-operator not found. Retry 12/60", "onap-strimzi-entity-operator not found. Retry 13/60", "onap-strimzi-entity-operator not found. Retry 14/60", "onap-strimzi-entity-operator not found. Retry 15/60", "onap-strimzi-entity-operator not found. Retry 16/60", "onap-strimzi-entity-operator not found. Retry 17/60", "onap-strimzi-entity-operator not found. Retry 18/60", "onap-strimzi-entity-operator not found. Retry 19/60", "onap-strimzi-entity-operator not found. Retry 20/60", "onap-strimzi-entity-operator not found. Retry 21/60", "onap-strimzi-entity-operator not found. Retry 22/60", "onap-strimzi-entity-operator not found. Retry 23/60", "onap-strimzi-entity-operator not found. Retry 24/60", "onap-strimzi-entity-operator not found. Retry 25/60", "onap-strimzi-entity-operator not found. Retry 26/60", "onap-strimzi-entity-operator not found. Retry 27/60", "onap-strimzi-entity-operator not found. Retry 28/60", "onap-strimzi-entity-operator not found. Retry 29/60", "onap-strimzi-entity-operator not found. Retry 30/60", "onap-strimzi-entity-operator not found. Retry 31/60", "onap-strimzi-entity-operator not found. Retry 32/60", "onap-strimzi-entity-operator not found. Retry 33/60", "onap-strimzi-entity-operator not found. Retry 34/60", "onap-strimzi-entity-operator not found. Retry 35/60", "onap-strimzi-entity-operator not found. Retry 36/60", "onap-strimzi-entity-operator not found. Retry 37/60", "onap-strimzi-entity-operator not found. Retry 38/60", "onap-strimzi-entity-operator not found. Retry 39/60", "onap-strimzi-entity-operator not found. Retry 40/60", "onap-strimzi-entity-operator not found. Retry 41/60", "onap-strimzi-entity-operator not found. Retry 42/60", "onap-strimzi-entity-operator not found. Retry 43/60", "onap-strimzi-entity-operator not found. Retry 44/60", "onap-strimzi-entity-operator not found. Retry 45/60", "onap-strimzi-entity-operator not found. Retry 46/60", "onap-strimzi-entity-operator not found. Retry 47/60", "onap-strimzi-entity-operator not found. Retry 48/60", "onap-strimzi-entity-operator not found. Retry 49/60", "onap-strimzi-entity-operator not found. Retry 50/60", "onap-strimzi-entity-operator not found. Retry 51/60", "onap-strimzi-entity-operator not found. Retry 52/60", "onap-strimzi-entity-operator not found. Retry 53/60", "onap-strimzi-entity-operator not found. Retry 54/60", "onap-strimzi-entity-operator not found. Retry 55/60", "onap-strimzi-entity-operator not found. Retry 56/60", "onap-strimzi-entity-operator not found. Retry 57/60", "onap-strimzi-entity-operator not found. Retry 58/60", "onap-strimzi-entity-operator not found. Retry 59/60", "onap-strimzi-entity-operator not found. Retry 60/60"]}
(ansible-venv) agnik@agnik-Alpha-15-A3DD:~/Desktop/deployoran/11ansable/smo-install-ansible$ grep -A 50 "TASK \[smo_deploy : Deploy ONAP components\]" /tmp/ansible-deploy-fixed.log | head -60
TASK [smo_deploy : Deploy ONAP components] *************************************
[ERROR]: Task failed: Module failed: non-zero return code
Origin: /home/agnik/Desktop/deployoran/11ansable/smo-install-ansible/roles/smo_deploy/tasks/install.yml:183:3

181   tags: install
182
183 - name: Deploy ONAP components
      ^ column 3

fatal: [smo-node-1]: FAILED! => {"changed": true, "cmd": "helm deploy onap oran-release/onap   --namespace onap    --values /opt/o-ran-sc/it-dep/smo-install/helm-override/default/onap-override.yaml    --set global.flavor=default    --timeout 3600s\n", "delta": "0:10:15.421107", "end": "2026-02-04 13:32:58.514031", "failed_when_result": true, "msg": "non-zero return code", "rc": 1, "start": "2026-02-04 13:22:43.092924", "stderr": "history.go:56: 2026-02-04 13:22:50.197298951 +0000 UTC m=+0.113637452 [debug] getting history for release onap\ninstall.go:225: 2026-02-04 13:22:50.201819247 +0000 UTC m=+0.118157753 [debug] Original chart version: \"\"\ninstall.go:242: 2026-02-04 13:22:50.201867832 +0000 UTC m=+0.118206339 [debug] CHART PATH: /root/.local/share/helm/plugins/deploy/cache/onap\n\nError: plugin \"deploy\" exited with error", "stderr_lines": ["history.go:56: 2026-02-04 13:22:50.197298951 +0000 UTC m=+0.113637452 [debug] getting history for release onap", "install.go:225: 2026-02-04 13:22:50.201819247 +0000 UTC m=+0.118157753 [debug] Original chart version: \"\"", "install.go:242: 2026-02-04 13:22:50.201867832 +0000 UTC m=+0.118206339 [debug] CHART PATH: /root/.local/share/helm/plugins/deploy/cache/onap", "", "Error: plugin \"deploy\" exited with error"], "stdout": "v3.18.6\nUse cache dir: /root/.local/share/helm/plugins/deploy/cache\n0\n0\n0\n0\nfetching oran-release/onap\nrelease \"onap\" deployed\nrelease \"onap-roles-wrapper\" deployed\nrelease \"onap-repository-wrapper\" deployed\nrelease \"onap-strimzi\" deployed\nwaiting for onap-strimzi-entity-operator to be deployed\nonap-strimzi-entity-operator not found. Retry 1/60\nonap-strimzi-entity-operator not found. Retry 2/60\nonap-strimzi-entity-operator not found. Retry 3/60\nonap-strimzi-entity-operator not found. Retry 4/60\nonap-strimzi-entity-operator not found. Retry 5/60\nonap-strimzi-entity-operator not found. Retry 6/60\nonap-strimzi-entity-operator not found. Retry 7/60\nonap-strimzi-entity-operator not found. Retry 8/60\nonap-strimzi-entity-operator not found. Retry 9/60\nonap-strimzi-entity-operator not found. Retry 10/60\nonap-strimzi-entity-operator not found. Retry 11/60\nonap-strimzi-entity-operator not found. Retry 12/60\nonap-strimzi-entity-operator not found. Retry 13/60\nonap-strimzi-entity-operator not found. Retry 14/60\nonap-strimzi-entity-operator not found. Retry 15/60\nonap-strimzi-entity-operator not found. Retry 16/60\nonap-strimzi-entity-operator not found. Retry 17/60\nonap-strimzi-entity-operator not found. Retry 18/60\nonap-strimzi-entity-operator not found. Retry 19/60\nonap-strimzi-entity-operator not found. Retry 20/60\nonap-strimzi-entity-operator not found. Retry 21/60\nonap-strimzi-entity-operator not found. Retry 22/60\nonap-strimzi-entity-operator not found. Retry 23/60\nonap-strimzi-entity-operator not found. Retry 24/60\nonap-strimzi-entity-operator not found. Retry 25/60\nonap-strimzi-entity-operator not found. Retry 26/60\nonap-strimzi-entity-operator not found. Retry 27/60\nonap-strimzi-entity-operator not found. Retry 28/60\nonap-strimzi-entity-operator not found. Retry 29/60\nonap-strimzi-entity-operator not found. Retry 30/60\nonap-strimzi-entity-operator not found. Retry 31/60\nonap-strimzi-entity-operator not found. Retry 32/60\nonap-strimzi-entity-operator not found. Retry 33/60\nonap-strimzi-entity-operator not found. Retry 34/60\nonap-strimzi-entity-operator not found. Retry 35/60\nonap-strimzi-entity-operator not found. Retry 36/60\nonap-strimzi-entity-operator not found. Retry 37/60\nonap-strimzi-entity-operator not found. Retry 38/60\nonap-strimzi-entity-operator not found. Retry 39/60\nonap-strimzi-entity-operator not found. Retry 40/60\nonap-strimzi-entity-operator not found. Retry 41/60\nonap-strimzi-entity-operator not found. Retry 42/60\nonap-strimzi-entity-operator not found. Retry 43/60\nonap-strimzi-entity-operator not found. Retry 44/60\nonap-strimzi-entity-operator not found. Retry 45/60\nonap-strimzi-entity-operator not found. Retry 46/60\nonap-strimzi-entity-operator not found. Retry 47/60\nonap-strimzi-entity-operator not found. Retry 48/60\nonap-strimzi-entity-operator not found. Retry 49/60\nonap-strimzi-entity-operator not found. Retry 50/60\nonap-strimzi-entity-operator not found. Retry 51/60\nonap-strimzi-entity-operator not found. Retry 52/60\nonap-strimzi-entity-operator not found. Retry 53/60\nonap-strimzi-entity-operator not found. Retry 54/60\nonap-strimzi-entity-operator not found. Retry 55/60\nonap-strimzi-entity-operator not found. Retry 56/60\nonap-strimzi-entity-operator not found. Retry 57/60\nonap-strimzi-entity-operator not found. Retry 58/60\nonap-strimzi-entity-operator not found. Retry 59/60\nonap-strimzi-entity-operator not found. Retry 60/60", "stdout_lines": ["v3.18.6", "Use cache dir: /root/.local/share/helm/plugins/deploy/cache", "0", "0", "0", "0", "fetching oran-release/onap", "release \"onap\" deployed", "release \"onap-roles-wrapper\" deployed", "release \"onap-repository-wrapper\" deployed", "release \"onap-strimzi\" deployed", "waiting for onap-strimzi-entity-operator to be deployed", "onap-strimzi-entity-operator not found. Retry 1/60", "onap-strimzi-entity-operator not found. Retry 2/60", "onap-strimzi-entity-operator not found. Retry 3/60", "onap-strimzi-entity-operator not found. Retry 4/60", "onap-strimzi-entity-operator not found. Retry 5/60", "onap-strimzi-entity-operator not found. Retry 6/60", "onap-strimzi-entity-operator not found. Retry 7/60", "onap-strimzi-entity-operator not found. Retry 8/60", "onap-strimzi-entity-operator not found. Retry 9/60", "onap-strimzi-entity-operator not found. Retry 10/60", "onap-strimzi-entity-operator not found. Retry 11/60", "onap-strimzi-entity-operator not found. Retry 12/60", "onap-strimzi-entity-operator not found. Retry 13/60", "onap-strimzi-entity-operator not found. Retry 14/60", "onap-strimzi-entity-operator not found. Retry 15/60", "onap-strimzi-entity-operator not found. Retry 16/60", "onap-strimzi-entity-operator not found. Retry 17/60", "onap-strimzi-entity-operator not found. Retry 18/60", "onap-strimzi-entity-operator not found. Retry 19/60", "onap-strimzi-entity-operator not found. Retry 20/60", "onap-strimzi-entity-operator not found. Retry 21/60", "onap-strimzi-entity-operator not found. Retry 22/60", "onap-strimzi-entity-operator not found. Retry 23/60", "onap-strimzi-entity-operator not found. Retry 24/60", "onap-strimzi-entity-operator not found. Retry 25/60", "onap-strimzi-entity-operator not found. Retry 26/60", "onap-strimzi-entity-operator not found. Retry 27/60", "onap-strimzi-entity-operator not found. Retry 28/60", "onap-strimzi-entity-operator not found. Retry 29/60", "onap-strimzi-entity-operator not found. Retry 30/60", "onap-strimzi-entity-operator not found. Retry 31/60", "onap-strimzi-entity-operator not found. Retry 32/60", "onap-strimzi-entity-operator not found. Retry 33/60", "onap-strimzi-entity-operator not found. Retry 34/60", "onap-strimzi-entity-operator not found. Retry 35/60", "onap-strimzi-entity-operator not found. Retry 36/60", "onap-strimzi-entity-operator not found. Retry 37/60", "onap-strimzi-entity-operator not found. Retry 38/60", "onap-strimzi-entity-operator not found. Retry 39/60", "onap-strimzi-entity-operator not found. Retry 40/60", "onap-strimzi-entity-operator not found. Retry 41/60", "onap-strimzi-entity-operator not found. Retry 42/60", "onap-strimzi-entity-operator not found. Retry 43/60", "onap-strimzi-entity-operator not found. Retry 44/60", "onap-strimzi-entity-operator not found. Retry 45/60", "onap-strimzi-entity-operator not found. Retry 46/60", "onap-strimzi-entity-operator not found. Retry 47/60", "onap-strimzi-entity-operator not found. Retry 48/60", "onap-strimzi-entity-operator not found. Retry 49/60", "onap-strimzi-entity-operator not found. Retry 50/60", "onap-strimzi-entity-operator not found. Retry 51/60", "onap-strimzi-entity-operator not found. Retry 52/60", "onap-strimzi-entity-operator not found. Retry 53/60", "onap-strimzi-entity-operator not found. Retry 54/60", "onap-strimzi-entity-operator not found. Retry 55/60", "onap-strimzi-entity-operator not found. Retry 56/60", "onap-strimzi-entity-operator not found. Retry 57/60", "onap-strimzi-entity-operator not found. Retry 58/60", "onap-strimzi-entity-operator not found. Retry 59/60", "onap-strimzi-entity-operator not found. Retry 60/60"]}

PLAY RECAP *********************************************************************
smo-node-1                 : ok=44   changed=6    unreachable=0    failed=1    skipped=45   rescued=0    ignored=0   
```
