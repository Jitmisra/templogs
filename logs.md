```
ls/setup_k8s/scripts/setup_k8s.sh: line 291: kubeadm: command not found
Error: Home directory for user  could not be found.
$ sudo bash tools/setup_k8s/scripts/setup_k8s.sh --ip-address $SERVER_IP
Checking Ubuntu version...
Checking internet connection...
Internet connection is active.
Checking if curl is installed...
curl is already installed.
This will attempt to remove any existing cluster. Do you want to proceed? (y/N): y
Attempting to remove existing Kubernetes components...
Info: 'kubeadm' command not found. Skipping 'kubeadm reset'.
Purging Kubernetes packages...
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
Note, selecting 'kubecolor' for glob 'kube*'
Note, selecting 'kubernetes' for glob 'kube*'
Note, selecting 'kubetail' for glob 'kube*'
Note, selecting 'kubernetes-cni' for glob 'kube*'
Note, selecting 'kubernetes-split-yaml' for glob 'kube*'
Note, selecting 'kube-openapi' for glob 'kube*'
Note, selecting 'kubernetes-client' for glob 'kube*'
Note, selecting 'kubeadm' for glob 'kube*'
Note, selecting 'kubectl' for glob 'kube*'
Note, selecting 'kubelet' for glob 'kube*'
Package 'kubernetes-client' is not installed, so not removed
Package 'kubernetes' is not installed, so not removed
Package 'kubetail' is not installed, so not removed
Package 'kube-openapi' is not installed, so not removed
Package 'kubecolor' is not installed, so not removed
Package 'kubernetes-split-yaml' is not installed, so not removed
Package 'kubeadm' is not installed, so not removed
Package 'kubectl' is not installed, so not removed
Package 'kubelet' is not installed, so not removed
Package 'kubernetes-cni' is not installed, so not removed
The following package was automatically installed and is no longer required:
  runc
Use 'sudo apt autoremove' to remove it.
The following packages will be REMOVED:
  containerd*
0 upgraded, 0 newly installed, 1 to remove and 71 not upgraded.
After this operation, 143 MB disk space will be freed.
(Reading database ... 111381 files and directories currently installed.)
Removing containerd (1.7.28-0ubuntu1~22.04.1) ...
Processing triggers for man-db (2.10.2-1) ...
(Reading database ... 111347 files and directories currently installed.)
Purging configuration files for containerd (1.7.28-0ubuntu1~22.04.1) ...
Running 'apt-get autoremove'...
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following packages will be REMOVED:
  runc
0 upgraded, 0 newly installed, 1 to remove and 71 not upgraded.
After this operation, 34.6 MB disk space will be freed.
(Reading database ... 111347 files and directories currently installed.)
Removing runc (1.3.3-0ubuntu1~22.04.3) ...
Processing triggers for man-db (2.10.2-1) ...
Info: '/root/.kube' directory not found. Skipping removal.
Existing cluster cleanup attempt completed.
Disabling swap...
rm: cannot remove '/swapfile': No such file or directory
===========================================================
 Preping the ENV:  Editing /etc/sysctl.conf...
===========================================================
* Applying /etc/sysctl.d/10-console-messages.conf ...
kernel.printk = 4 4 1 7
* Applying /etc/sysctl.d/10-ipv6-privacy.conf ...
net.ipv6.conf.all.use_tempaddr = 2
net.ipv6.conf.default.use_tempaddr = 2
* Applying /etc/sysctl.d/10-kernel-hardening.conf ...
kernel.kptr_restrict = 1
* Applying /etc/sysctl.d/10-magic-sysrq.conf ...
kernel.sysrq = 176
* Applying /etc/sysctl.d/10-network-security.conf ...
net.ipv4.conf.default.rp_filter = 2
net.ipv4.conf.all.rp_filter = 2
* Applying /etc/sysctl.d/10-ptrace.conf ...
kernel.yama.ptrace_scope = 1
* Applying /etc/sysctl.d/10-zeropage.conf ...
vm.mmap_min_addr = 65536
* Applying /usr/lib/sysctl.d/50-default.conf ...
kernel.core_uses_pid = 1
net.ipv4.conf.default.rp_filter = 2
net.ipv4.conf.default.accept_source_route = 0
sysctl: setting key "net.ipv4.conf.all.accept_source_route": Invalid argument
net.ipv4.conf.default.promote_secondaries = 1
sysctl: setting key "net.ipv4.conf.all.promote_secondaries": Invalid argument
net.ipv4.ping_group_range = 0 2147483647
net.core.default_qdisc = fq_codel
fs.protected_hardlinks = 1
fs.protected_symlinks = 1
fs.protected_regular = 1
fs.protected_fifos = 1
* Applying /usr/lib/sysctl.d/50-pid-max.conf ...
kernel.pid_max = 4194304
* Applying /usr/lib/sysctl.d/99-protect-links.conf ...
fs.protected_fifos = 1
fs.protected_hardlinks = 1
fs.protected_regular = 2
fs.protected_symlinks = 1
* Applying /etc/sysctl.d/99-sysctl.conf ...
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
* Applying /etc/sysctl.d/k8s.conf ...
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.d/kubernetes.conf ...
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.conf ...
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
overlay
br_netfilter
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.d/10-console-messages.conf ...
kernel.printk = 4 4 1 7
* Applying /etc/sysctl.d/10-ipv6-privacy.conf ...
net.ipv6.conf.all.use_tempaddr = 2
net.ipv6.conf.default.use_tempaddr = 2
* Applying /etc/sysctl.d/10-kernel-hardening.conf ...
kernel.kptr_restrict = 1
* Applying /etc/sysctl.d/10-magic-sysrq.conf ...
kernel.sysrq = 176
* Applying /etc/sysctl.d/10-network-security.conf ...
net.ipv4.conf.default.rp_filter = 2
net.ipv4.conf.all.rp_filter = 2
* Applying /etc/sysctl.d/10-ptrace.conf ...
kernel.yama.ptrace_scope = 1
* Applying /etc/sysctl.d/10-zeropage.conf ...
vm.mmap_min_addr = 65536
* Applying /usr/lib/sysctl.d/50-default.conf ...
kernel.core_uses_pid = 1
net.ipv4.conf.default.rp_filter = 2
net.ipv4.conf.default.accept_source_route = 0
sysctl: setting key "net.ipv4.conf.all.accept_source_route": Invalid argument
net.ipv4.conf.default.promote_secondaries = 1
sysctl: setting key "net.ipv4.conf.all.promote_secondaries": Invalid argument
net.ipv4.ping_group_range = 0 2147483647
net.core.default_qdisc = fq_codel
fs.protected_hardlinks = 1
fs.protected_symlinks = 1
fs.protected_regular = 1
fs.protected_fifos = 1
* Applying /usr/lib/sysctl.d/50-pid-max.conf ...
kernel.pid_max = 4194304
* Applying /usr/lib/sysctl.d/99-protect-links.conf ...
fs.protected_fifos = 1
fs.protected_hardlinks = 1
fs.protected_regular = 2
fs.protected_symlinks = 1
* Applying /etc/sysctl.d/99-sysctl.conf ...
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
* Applying /etc/sysctl.d/k8s.conf ...
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.d/kubernetes.conf ...
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.conf ...
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
net.ipv4.ip_forward = 1
****************************************************************************************************************
						Installing Containerd		
****************************************************************************************************************
* Applying /etc/sysctl.d/10-console-messages.conf ...
kernel.printk = 4 4 1 7
* Applying /etc/sysctl.d/10-ipv6-privacy.conf ...
net.ipv6.conf.all.use_tempaddr = 2
net.ipv6.conf.default.use_tempaddr = 2
* Applying /etc/sysctl.d/10-kernel-hardening.conf ...
kernel.kptr_restrict = 1
* Applying /etc/sysctl.d/10-magic-sysrq.conf ...
kernel.sysrq = 176
* Applying /etc/sysctl.d/10-network-security.conf ...
net.ipv4.conf.default.rp_filter = 2
net.ipv4.conf.all.rp_filter = 2
* Applying /etc/sysctl.d/10-ptrace.conf ...
kernel.yama.ptrace_scope = 1
* Applying /etc/sysctl.d/10-zeropage.conf ...
vm.mmap_min_addr = 65536
* Applying /usr/lib/sysctl.d/50-default.conf ...
kernel.core_uses_pid = 1
net.ipv4.conf.default.rp_filter = 2
net.ipv4.conf.default.accept_source_route = 0
sysctl: setting key "net.ipv4.conf.all.accept_source_route": Invalid argument
net.ipv4.conf.default.promote_secondaries = 1
sysctl: setting key "net.ipv4.conf.all.promote_secondaries": Invalid argument
net.ipv4.ping_group_range = 0 2147483647
net.core.default_qdisc = fq_codel
fs.protected_hardlinks = 1
fs.protected_symlinks = 1
fs.protected_regular = 1
fs.protected_fifos = 1
* Applying /usr/lib/sysctl.d/50-pid-max.conf ...
kernel.pid_max = 4194304
* Applying /usr/lib/sysctl.d/99-protect-links.conf ...
fs.protected_fifos = 1
fs.protected_hardlinks = 1
fs.protected_regular = 2
fs.protected_symlinks = 1
* Applying /etc/sysctl.d/99-sysctl.conf ...
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
* Applying /etc/sysctl.d/k8s.conf ...
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.d/kubernetes.conf ...
net.bridge.bridge-nf-call-ip6tables = 1
net.bridge.bridge-nf-call-iptables = 1
net.ipv4.ip_forward = 1
* Applying /etc/sysctl.conf ...
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
fs.inotify.max_user_watches = 524288
fs.inotify.max_user_instances = 512
fs.inotify.max_queued_events = 16384
vm.max_map_count = 262144
Get:1 http://security.ubuntu.com/ubuntu jammy-security InRelease [129 kB]
Hit:2 http://us.archive.ubuntu.com/ubuntu jammy InRelease                      
Get:4 http://us.archive.ubuntu.com/ubuntu jammy-updates InRelease [128 kB]     
Get:5 http://us.archive.ubuntu.com/ubuntu jammy-backports InRelease [127 kB]
Hit:3 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  InRelease
Fetched 384 kB in 1s (398 kB/s)                          
Reading package lists... Done
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  runc
The following NEW packages will be installed:
  containerd runc
0 upgraded, 2 newly installed, 0 to remove and 71 not upgraded.
Need to get 0 B/47.4 MB of archives.
After this operation, 178 MB of additional disk space will be used.
Selecting previously unselected package runc.
(Reading database ... 111319 files and directories currently installed.)
Preparing to unpack .../runc_1.3.3-0ubuntu1~22.04.3_amd64.deb ...
Unpacking runc (1.3.3-0ubuntu1~22.04.3) ...
Selecting previously unselected package containerd.
Preparing to unpack .../containerd_1.7.28-0ubuntu1~22.04.1_amd64.deb ...
Unpacking containerd (1.7.28-0ubuntu1~22.04.1) ...
Setting up runc (1.3.3-0ubuntu1~22.04.3) ...
Setting up containerd (1.7.28-0ubuntu1~22.04.1) ...
Created symlink /etc/systemd/system/multi-user.target.wants/containerd.service → /lib/systemd/system/containerd.service.
Processing triggers for man-db (2.10.2-1) ...
Scanning processes...                                                           
Scanning candidates...                                                          
Scanning processor microcode...                                                 
Scanning linux images...                                                        

The processor microcode seems to be up-to-date.

Restarting services...
Service restarts being deferred:
 systemctl restart NetworkManager.service
 /etc/needrestart/restart.d/dbus.service
 systemctl restart getty@tty1.service
 systemctl restart networkd-dispatcher.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service
 systemctl restart user@1001.service
 systemctl restart wpa_supplicant.service

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
disabled_plugins = []
imports = []
oom_score = 0
plugin_dir = ""
required_plugins = []
root = "/var/lib/containerd"
state = "/run/containerd"
temp = ""
version = 2

[cgroup]
  path = ""

[debug]
  address = ""
  format = ""
  gid = 0
  level = ""
  uid = 0

[grpc]
  address = "/run/containerd/containerd.sock"
  gid = 0
  max_recv_message_size = 16777216
  max_send_message_size = 16777216
  tcp_address = ""
  tcp_tls_ca = ""
  tcp_tls_cert = ""
  tcp_tls_key = ""
  uid = 0

[metrics]
  address = ""
  grpc_histogram = false

[plugins]

  [plugins."io.containerd.gc.v1.scheduler"]
    deletion_threshold = 0
    mutation_threshold = 100
    pause_threshold = 0.02
    schedule_delay = "0s"
    startup_delay = "100ms"

  [plugins."io.containerd.grpc.v1.cri"]
    cdi_spec_dirs = ["/etc/cdi", "/var/run/cdi"]
    device_ownership_from_security_context = false
    disable_apparmor = false
    disable_cgroup = false
    disable_hugetlb_controller = true
    disable_proc_mount = false
    disable_tcp_service = true
    drain_exec_sync_io_timeout = "0s"
    enable_cdi = false
    enable_selinux = false
    enable_tls_streaming = false
    enable_unprivileged_icmp = false
    enable_unprivileged_ports = false
    ignore_deprecation_warnings = []
    ignore_image_defined_volumes = false
    image_pull_progress_timeout = "5m0s"
    image_pull_with_sync_fs = false
    max_concurrent_downloads = 3
    max_container_log_line_size = 16384
    netns_mounts_under_state_dir = false
    restrict_oom_score_adj = false
    sandbox_image = "registry.k8s.io/pause:3.8"
    selinux_category_range = 1024
    stats_collect_period = 10
    stream_idle_timeout = "4h0m0s"
    stream_server_address = "127.0.0.1"
    stream_server_port = "0"
    systemd_cgroup = false
    tolerate_missing_hugetlb_controller = true
    unset_seccomp_profile = ""

    [plugins."io.containerd.grpc.v1.cri".cni]
      bin_dir = "/opt/cni/bin"
      conf_dir = "/etc/cni/net.d"
      conf_template = ""
      ip_pref = ""
      max_conf_num = 1
      setup_serially = false

    [plugins."io.containerd.grpc.v1.cri".containerd]
      default_runtime_name = "runc"
      disable_snapshot_annotations = true
      discard_unpacked_layers = false
      ignore_blockio_not_enabled_errors = false
      ignore_rdt_not_enabled_errors = false
      no_pivot = false
      snapshotter = "overlayfs"

      [plugins."io.containerd.grpc.v1.cri".containerd.default_runtime]
        base_runtime_spec = ""
        cni_conf_dir = ""
        cni_max_conf_num = 0
        container_annotations = []
        pod_annotations = []
        privileged_without_host_devices = false
        privileged_without_host_devices_all_devices_allowed = false
        runtime_engine = ""
        runtime_path = ""
        runtime_root = ""
        runtime_type = ""
        sandbox_mode = ""
        snapshotter = ""

        [plugins."io.containerd.grpc.v1.cri".containerd.default_runtime.options]

      [plugins."io.containerd.grpc.v1.cri".containerd.runtimes]

        [plugins."io.containerd.grpc.v1.cri".containerd.runtimes.runc]
          base_runtime_spec = ""
          cni_conf_dir = ""
          cni_max_conf_num = 0
          container_annotations = []
          pod_annotations = []
          privileged_without_host_devices = false
          privileged_without_host_devices_all_devices_allowed = false
          runtime_engine = ""
          runtime_path = ""
          runtime_root = ""
          runtime_type = "io.containerd.runc.v2"
          sandbox_mode = "podsandbox"
          snapshotter = ""

          [plugins."io.containerd.grpc.v1.cri".containerd.runtimes.runc.options]
            BinaryName = ""
            CriuImagePath = ""
            CriuPath = ""
            CriuWorkPath = ""
            IoGid = 0
            IoUid = 0
            NoNewKeyring = false
            NoPivotRoot = false
            Root = ""
            ShimCgroup = ""
            SystemdCgroup = false

      [plugins."io.containerd.grpc.v1.cri".containerd.untrusted_workload_runtime]
        base_runtime_spec = ""
        cni_conf_dir = ""
        cni_max_conf_num = 0
        container_annotations = []
        pod_annotations = []
        privileged_without_host_devices = false
        privileged_without_host_devices_all_devices_allowed = false
        runtime_engine = ""
        runtime_path = ""
        runtime_root = ""
        runtime_type = ""
        sandbox_mode = ""
        snapshotter = ""

        [plugins."io.containerd.grpc.v1.cri".containerd.untrusted_workload_runtime.options]

    [plugins."io.containerd.grpc.v1.cri".image_decryption]
      key_model = "node"

    [plugins."io.containerd.grpc.v1.cri".registry]
      config_path = ""

      [plugins."io.containerd.grpc.v1.cri".registry.auths]

      [plugins."io.containerd.grpc.v1.cri".registry.configs]

      [plugins."io.containerd.grpc.v1.cri".registry.headers]

      [plugins."io.containerd.grpc.v1.cri".registry.mirrors]

    [plugins."io.containerd.grpc.v1.cri".x509_key_pair_streaming]
      tls_cert_file = ""
      tls_key_file = ""

  [plugins."io.containerd.internal.v1.opt"]
    path = "/opt/containerd"

  [plugins."io.containerd.internal.v1.restart"]
    interval = "10s"

  [plugins."io.containerd.internal.v1.tracing"]

  [plugins."io.containerd.metadata.v1.bolt"]
    content_sharing_policy = "shared"

  [plugins."io.containerd.monitor.v1.cgroups"]
    no_prometheus = false

  [plugins."io.containerd.nri.v1.nri"]
    disable = true
    disable_connections = false
    plugin_config_path = "/etc/nri/conf.d"
    plugin_path = "/opt/nri/plugins"
    plugin_registration_timeout = "5s"
    plugin_request_timeout = "2s"
    socket_path = "/var/run/nri/nri.sock"

  [plugins."io.containerd.runtime.v1.linux"]
    no_shim = false
    runtime = "runc"
    runtime_root = ""
    shim = "containerd-shim"
    shim_debug = false

  [plugins."io.containerd.runtime.v2.task"]
    platforms = ["linux/amd64"]
    sched_core = false

  [plugins."io.containerd.service.v1.diff-service"]
    default = ["walking"]
    sync_fs = false

  [plugins."io.containerd.service.v1.tasks-service"]
    blockio_config_file = ""
    rdt_config_file = ""

  [plugins."io.containerd.snapshotter.v1.aufs"]
    root_path = ""

  [plugins."io.containerd.snapshotter.v1.blockfile"]
    fs_type = ""
    mount_options = []
    root_path = ""
    scratch_file = ""

  [plugins."io.containerd.snapshotter.v1.btrfs"]
    root_path = ""

  [plugins."io.containerd.snapshotter.v1.devmapper"]
    async_remove = false
    base_image_size = ""
    discard_blocks = false
    fs_options = ""
    fs_type = ""
    pool_name = ""
    root_path = ""

  [plugins."io.containerd.snapshotter.v1.native"]
    root_path = ""

  [plugins."io.containerd.snapshotter.v1.overlayfs"]
    mount_options = []
    root_path = ""
    sync_remove = false
    upperdir_label = false

  [plugins."io.containerd.snapshotter.v1.zfs"]
    root_path = ""

  [plugins."io.containerd.tracing.processor.v1.otlp"]

  [plugins."io.containerd.transfer.v1.local"]
    config_path = ""
    max_concurrent_downloads = 3
    max_concurrent_uploaded_layers = 3

    [[plugins."io.containerd.transfer.v1.local".unpack_config]]
      differ = "walking"
      platform = "linux/amd64"
      snapshotter = "overlayfs"

[proxy_plugins]

[stream_processors]

  [stream_processors."io.containerd.ocicrypt.decoder.v1.tar"]
    accepts = ["application/vnd.oci.image.layer.v1.tar+encrypted"]
    args = ["--decryption-keys-path", "/etc/containerd/ocicrypt/keys"]
    env = ["OCICRYPT_KEYPROVIDER_CONFIG=/etc/containerd/ocicrypt/ocicrypt_keyprovider.conf"]
    path = "ctd-decoder"
    returns = "application/vnd.oci.image.layer.v1.tar"

  [stream_processors."io.containerd.ocicrypt.decoder.v1.tar.gzip"]
    accepts = ["application/vnd.oci.image.layer.v1.tar+gzip+encrypted"]
    args = ["--decryption-keys-path", "/etc/containerd/ocicrypt/keys"]
    env = ["OCICRYPT_KEYPROVIDER_CONFIG=/etc/containerd/ocicrypt/ocicrypt_keyprovider.conf"]
    path = "ctd-decoder"
    returns = "application/vnd.oci.image.layer.v1.tar+gzip"

[timeouts]
  "io.containerd.timeout.bolt.open" = "0s"
  "io.containerd.timeout.metrics.shimstats" = "2s"
  "io.containerd.timeout.shim.cleanup" = "5s"
  "io.containerd.timeout.shim.load" = "5s"
  "io.containerd.timeout.shim.shutdown" = "3s"
  "io.containerd.timeout.task.state" = "2s"

[ttrpc]
  address = ""
  gid = 0
  uid = 0
****************************************************************************************************************
						Installing Helm			
****************************************************************************************************************
--2025-12-23 02:30:27--  https://get.helm.sh/helm-v3.18.6-linux-amd64.tar.gz
Resolving get.helm.sh (get.helm.sh)... 13.107.213.36, 13.107.246.36, 2620:1ec:bdf::36, ...
Connecting to get.helm.sh (get.helm.sh)|13.107.213.36|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 17986975 (17M) [application/x-tar]
Saving to: ‘helm-v3.18.6-linux-amd64.tar.gz’

helm-v3.18.6-linux- 100%[===================>]  17.15M  82.6MB/s    in 0.2s    

2025-12-23 02:30:28 (82.6 MB/s) - ‘helm-v3.18.6-linux-amd64.tar.gz’ saved [17986975/17986975]

linux-amd64/
linux-amd64/README.md
linux-amd64/helm
linux-amd64/LICENSE
version.BuildInfo{Version:"v3.18.6", GitCommit:"b76a950f6835474e0906b96c9ec68a2eff3a6430", GitTreeState:"clean", GoVersion:"go1.24.6"}
***************************************************************************************************************
						Installing Kubernetes		
***************************************************************************************************************
deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.32/deb/ /
Hit:1 http://us.archive.ubuntu.com/ubuntu jammy InRelease
Hit:2 http://us.archive.ubuntu.com/ubuntu jammy-updates InRelease              
Hit:3 http://us.archive.ubuntu.com/ubuntu jammy-backports InRelease            
Hit:5 http://security.ubuntu.com/ubuntu jammy-security InRelease               
Hit:4 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  InRelease
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
71 packages can be upgraded. Run 'apt list --upgradable' to see them.
Reading package lists... Done
Building dependency tree... Done
Reading state information... Done
The following additional packages will be installed:
  cri-tools kubernetes-cni
The following NEW packages will be installed:
  cri-tools kubeadm kubectl kubelet kubernetes-cni
0 upgraded, 5 newly installed, 0 to remove and 71 not upgraded.
Need to get 92.7 MB of archives.
After this operation, 338 MB of additional disk space will be used.
Get:1 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  cri-tools 1.32.0-1.1 [16.3 MB]
Get:2 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  kubeadm 1.32.8-1.1 [12.2 MB]
Get:3 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  kubectl 1.32.8-1.1 [11.3 MB]
Get:4 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  kubernetes-cni 1.6.0-1.1 [37.8 MB]
Get:5 https://prod-cdn.packages.k8s.io/repositories/isv:/kubernetes:/core:/stable:/v1.32/deb  kubelet 1.32.8-1.1 [15.2 MB]
Fetched 92.7 MB in 3s (31.8 MB/s) 
Selecting previously unselected package cri-tools.
(Reading database ... 111381 files and directories currently installed.)
Preparing to unpack .../cri-tools_1.32.0-1.1_amd64.deb ...
Unpacking cri-tools (1.32.0-1.1) ...
Selecting previously unselected package kubeadm.
Preparing to unpack .../kubeadm_1.32.8-1.1_amd64.deb ...
Unpacking kubeadm (1.32.8-1.1) ...
Selecting previously unselected package kubectl.
Preparing to unpack .../kubectl_1.32.8-1.1_amd64.deb ...
Unpacking kubectl (1.32.8-1.1) ...
Selecting previously unselected package kubernetes-cni.
Preparing to unpack .../kubernetes-cni_1.6.0-1.1_amd64.deb ...
Unpacking kubernetes-cni (1.6.0-1.1) ...
Selecting previously unselected package kubelet.
Preparing to unpack .../kubelet_1.32.8-1.1_amd64.deb ...
Unpacking kubelet (1.32.8-1.1) ...
Setting up kubectl (1.32.8-1.1) ...
Setting up cri-tools (1.32.0-1.1) ...
Setting up kubernetes-cni (1.6.0-1.1) ...
Setting up kubeadm (1.32.8-1.1) ...
Setting up kubelet (1.32.8-1.1) ...
Scanning processes...                                                           
Scanning candidates...                                                          
Scanning processor microcode...                                                 
Scanning linux images...                                                        

The processor microcode seems to be up-to-date.

Restarting services...
Service restarts being deferred:
 systemctl restart NetworkManager.service
 /etc/needrestart/restart.d/dbus.service
 systemctl restart getty@tty1.service
 systemctl restart networkd-dispatcher.service
 systemctl restart systemd-logind.service
 systemctl restart unattended-upgrades.service
 systemctl restart user@1001.service
 systemctl restart wpa_supplicant.service

No containers need to be restarted.

No user sessions are running outdated binaries.

No VM guests are running outdated hypervisor (qemu) binaries on this host.
I1223 02:31:05.609902 1574840 initconfiguration.go:123] detected and using CRI socket: unix:///var/run/containerd/containerd.sock
I1223 02:31:05.609973 1574840 kubelet.go:196] the value of KubeletConfiguration.cgroupDriver is empty; setting it to "systemd"
I1223 02:31:05.610002 1574840 version.go:192] fetching Kubernetes version from URL: https://dl.k8s.io/release/stable-1.txt
I1223 02:31:06.062377 1574840 version.go:261] remote version is much newer: v1.35.0; falling back to: stable-1.32
I1223 02:31:06.062490 1574840 version.go:192] fetching Kubernetes version from URL: https://dl.k8s.io/release/stable-1.32.txt
[init] Using Kubernetes version: v1.32.11
[preflight] Running pre-flight checks
I1223 02:31:06.250098 1574840 checks.go:561] validating Kubernetes and kubeadm version
I1223 02:31:06.250192 1574840 checks.go:166] validating if the firewall is enabled and active
I1223 02:31:06.267323 1574840 checks.go:201] validating availability of port 6443
I1223 02:31:06.267747 1574840 checks.go:201] validating availability of port 10259
I1223 02:31:06.267808 1574840 checks.go:201] validating availability of port 10257
I1223 02:31:06.267862 1574840 checks.go:278] validating the existence of file /etc/kubernetes/manifests/kube-apiserver.yaml
I1223 02:31:06.267899 1574840 checks.go:278] validating the existence of file /etc/kubernetes/manifests/kube-controller-manager.yaml
I1223 02:31:06.267920 1574840 checks.go:278] validating the existence of file /etc/kubernetes/manifests/kube-scheduler.yaml
I1223 02:31:06.267940 1574840 checks.go:278] validating the existence of file /etc/kubernetes/manifests/etcd.yaml
I1223 02:31:06.267960 1574840 checks.go:428] validating if the connectivity type is via proxy or direct
I1223 02:31:06.267987 1574840 checks.go:467] validating http connectivity to first IP address in the CIDR
I1223 02:31:06.268032 1574840 checks.go:467] validating http connectivity to first IP address in the CIDR
I1223 02:31:06.268056 1574840 checks.go:102] validating the container runtime
I1223 02:31:06.269194 1574840 checks.go:637] validating whether swap is enabled or not
I1223 02:31:06.269291 1574840 checks.go:368] validating the presence of executable ip
I1223 02:31:06.269361 1574840 checks.go:368] validating the presence of executable iptables
I1223 02:31:06.269405 1574840 checks.go:368] validating the presence of executable mount
I1223 02:31:06.269439 1574840 checks.go:368] validating the presence of executable nsenter
I1223 02:31:06.269533 1574840 checks.go:368] validating the presence of executable ethtool
I1223 02:31:06.269565 1574840 checks.go:368] validating the presence of executable tc
I1223 02:31:06.269620 1574840 checks.go:368] validating the presence of executable touch
I1223 02:31:06.269658 1574840 checks.go:514] running all checks
I1223 02:31:06.290049 1574840 checks.go:399] checking whether the given node name is valid and reachable using net.LookupHost
I1223 02:31:06.290092 1574840 checks.go:603] validating kubelet version
I1223 02:31:06.346815 1574840 checks.go:128] validating if the "kubelet" service is enabled and active
I1223 02:31:06.367362 1574840 checks.go:201] validating availability of port 10250
I1223 02:31:06.367482 1574840 checks.go:327] validating the contents of file /proc/sys/net/ipv4/ip_forward
I1223 02:31:06.367558 1574840 checks.go:201] validating availability of port 2379
I1223 02:31:06.367626 1574840 checks.go:201] validating availability of port 2380
I1223 02:31:06.367681 1574840 checks.go:241] validating the existence and emptiness of directory /var/lib/etcd
[preflight] Pulling images required for setting up a Kubernetes cluster
[preflight] This might take a minute or two, depending on the speed of your internet connection
[preflight] You can also perform this action beforehand using 'kubeadm config images pull'
I1223 02:31:06.370401 1574840 checks.go:832] using image pull policy: IfNotPresent
W1223 02:31:06.372233 1574840 checks.go:846] detected that the sandbox image "registry.k8s.io/pause:3.8" of the container runtime is inconsistent with that used by kubeadm.It is recommended to use "registry.k8s.io/pause:3.10" as the CRI sandbox image.
I1223 02:31:06.373210 1574840 checks.go:868] pulling: registry.k8s.io/kube-apiserver:v1.32.11
I1223 02:31:10.168056 1574840 checks.go:868] pulling: registry.k8s.io/kube-controller-manager:v1.32.11
I1223 02:31:12.796364 1574840 checks.go:868] pulling: registry.k8s.io/kube-scheduler:v1.32.11
I1223 02:31:15.238134 1574840 checks.go:868] pulling: registry.k8s.io/kube-proxy:v1.32.11
I1223 02:31:19.537829 1574840 checks.go:868] pulling: registry.k8s.io/coredns/coredns:v1.11.3
I1223 02:31:21.862073 1574840 checks.go:868] pulling: registry.k8s.io/pause:3.10
I1223 02:31:22.595879 1574840 checks.go:868] pulling: registry.k8s.io/etcd:3.5.16-0
[certs] Using certificateDir folder "/etc/kubernetes/pki"
I1223 02:31:26.293106 1574840 certs.go:112] creating a new certificate authority for ca
[certs] Generating "ca" certificate and key
I1223 02:31:26.496558 1574840 certs.go:473] validating certificate period for ca certificate
[certs] Generating "apiserver" certificate and key
[certs] apiserver serving cert is signed for DNS names [aiml kubernetes kubernetes.default kubernetes.default.svc kubernetes.default.svc.cluster.local] and IPs [10.96.0.1 10.200.105.55]
[certs] Generating "apiserver-kubelet-client" certificate and key
I1223 02:31:26.959640 1574840 certs.go:112] creating a new certificate authority for front-proxy-ca
[certs] Generating "front-proxy-ca" certificate and key
I1223 02:31:27.520910 1574840 certs.go:473] validating certificate period for front-proxy-ca certificate
[certs] Generating "front-proxy-client" certificate and key
I1223 02:31:27.840136 1574840 certs.go:112] creating a new certificate authority for etcd-ca
[certs] Generating "etcd/ca" certificate and key
I1223 02:31:28.300501 1574840 certs.go:473] validating certificate period for etcd/ca certificate
[certs] Generating "etcd/server" certificate and key
[certs] etcd/server serving cert is signed for DNS names [aiml localhost] and IPs [10.200.105.55 127.0.0.1 ::1]
[certs] Generating "etcd/peer" certificate and key
[certs] etcd/peer serving cert is signed for DNS names [aiml localhost] and IPs [10.200.105.55 127.0.0.1 ::1]
[certs] Generating "etcd/healthcheck-client" certificate and key
[certs] Generating "apiserver-etcd-client" certificate and key
I1223 02:31:29.293917 1574840 certs.go:78] creating new public/private key files for signing service account users
[certs] Generating "sa" key and public key
[kubeconfig] Using kubeconfig folder "/etc/kubernetes"
I1223 02:31:29.602914 1574840 kubeconfig.go:111] creating kubeconfig file for admin.conf
[kubeconfig] Writing "admin.conf" kubeconfig file
I1223 02:31:29.811254 1574840 kubeconfig.go:111] creating kubeconfig file for super-admin.conf
[kubeconfig] Writing "super-admin.conf" kubeconfig file
I1223 02:31:30.310840 1574840 kubeconfig.go:111] creating kubeconfig file for kubelet.conf
[kubeconfig] Writing "kubelet.conf" kubeconfig file
I1223 02:31:30.817297 1574840 kubeconfig.go:111] creating kubeconfig file for controller-manager.conf
[kubeconfig] Writing "controller-manager.conf" kubeconfig file
I1223 02:31:31.064786 1574840 kubeconfig.go:111] creating kubeconfig file for scheduler.conf
[kubeconfig] Writing "scheduler.conf" kubeconfig file
[etcd] Creating static Pod manifest for local etcd in "/etc/kubernetes/manifests"
I1223 02:31:31.544812 1574840 local.go:66] [etcd] wrote Static Pod manifest for a local etcd member to "/etc/kubernetes/manifests/etcd.yaml"
[control-plane] Using manifest folder "/etc/kubernetes/manifests"
[control-plane] Creating static Pod manifest for "kube-apiserver"
I1223 02:31:31.544866 1574840 manifests.go:104] [control-plane] getting StaticPodSpecs
I1223 02:31:31.545176 1574840 certs.go:473] validating certificate period for CA certificate
I1223 02:31:31.545320 1574840 manifests.go:130] [control-plane] adding volume "ca-certs" for component "kube-apiserver"
I1223 02:31:31.545342 1574840 manifests.go:130] [control-plane] adding volume "etc-ca-certificates" for component "kube-apiserver"
I1223 02:31:31.545357 1574840 manifests.go:130] [control-plane] adding volume "k8s-certs" for component "kube-apiserver"
I1223 02:31:31.545373 1574840 manifests.go:130] [control-plane] adding volume "usr-local-share-ca-certificates" for component "kube-apiserver"
I1223 02:31:31.545386 1574840 manifests.go:130] [control-plane] adding volume "usr-share-ca-certificates" for component "kube-apiserver"
I1223 02:31:31.547151 1574840 manifests.go:159] [control-plane] wrote static Pod manifest for component "kube-apiserver" to "/etc/kubernetes/manifests/kube-apiserver.yaml"
[control-plane] Creating static Pod manifest for "kube-controller-manager"
I1223 02:31:31.547181 1574840 manifests.go:104] [control-plane] getting StaticPodSpecs
I1223 02:31:31.547564 1574840 manifests.go:130] [control-plane] adding volume "ca-certs" for component "kube-controller-manager"
I1223 02:31:31.547588 1574840 manifests.go:130] [control-plane] adding volume "etc-ca-certificates" for component "kube-controller-manager"
I1223 02:31:31.547600 1574840 manifests.go:130] [control-plane] adding volume "flexvolume-dir" for component "kube-controller-manager"
I1223 02:31:31.547613 1574840 manifests.go:130] [control-plane] adding volume "k8s-certs" for component "kube-controller-manager"
I1223 02:31:31.547626 1574840 manifests.go:130] [control-plane] adding volume "kubeconfig" for component "kube-controller-manager"
I1223 02:31:31.547641 1574840 manifests.go:130] [control-plane] adding volume "usr-local-share-ca-certificates" for component "kube-controller-manager"
I1223 02:31:31.547658 1574840 manifests.go:130] [control-plane] adding volume "usr-share-ca-certificates" for component "kube-controller-manager"
I1223 02:31:31.549276 1574840 manifests.go:159] [control-plane] wrote static Pod manifest for component "kube-controller-manager" to "/etc/kubernetes/manifests/kube-controller-manager.yaml"
[control-plane] Creating static Pod manifest for "kube-scheduler"
I1223 02:31:31.549306 1574840 manifests.go:104] [control-plane] getting StaticPodSpecs
I1223 02:31:31.549659 1574840 manifests.go:130] [control-plane] adding volume "kubeconfig" for component "kube-scheduler"
I1223 02:31:31.550769 1574840 manifests.go:159] [control-plane] wrote static Pod manifest for component "kube-scheduler" to "/etc/kubernetes/manifests/kube-scheduler.yaml"
I1223 02:31:31.550796 1574840 kubelet.go:70] Stopping the kubelet
[kubelet-start] Writing kubelet environment file with flags to file "/var/lib/kubelet/kubeadm-flags.env"
[kubelet-start] Writing kubelet configuration to file "/var/lib/kubelet/config.yaml"
[kubelet-start] Starting the kubelet
I1223 02:31:32.035098 1574840 envvar.go:172] "Feature gate default state" feature="InformerResourceVersion" enabled=false
I1223 02:31:32.035147 1574840 envvar.go:172] "Feature gate default state" feature="WatchListClient" enabled=false
I1223 02:31:32.035162 1574840 envvar.go:172] "Feature gate default state" feature="ClientsAllowCBOR" enabled=false
I1223 02:31:32.035175 1574840 envvar.go:172] "Feature gate default state" feature="ClientsPreferCBOR" enabled=false
[wait-control-plane] Waiting for the kubelet to boot up the control plane as static Pods from directory "/etc/kubernetes/manifests"
[kubelet-check] Waiting for a healthy kubelet at http://127.0.0.1:10248/healthz. This can take up to 4m0s
[kubelet-check] The kubelet is healthy after 1.001134946s
[api-check] Waiting for a healthy API server. This can take up to 4m0s
[api-check] The API server is healthy after 4.501959956s
I1223 02:31:37.542350 1574840 kubeconfig.go:665] ensuring that the ClusterRoleBinding for the kubeadm:cluster-admins Group exists
I1223 02:31:37.544206 1574840 kubeconfig.go:738] creating the ClusterRoleBinding for the kubeadm:cluster-admins Group by using super-admin.conf
I1223 02:31:37.560725 1574840 uploadconfig.go:112] [upload-config] Uploading the kubeadm ClusterConfiguration to a ConfigMap
[upload-config] Storing the configuration used in ConfigMap "kubeadm-config" in the "kube-system" Namespace
I1223 02:31:37.574725 1574840 uploadconfig.go:126] [upload-config] Uploading the kubelet component config to a ConfigMap
[kubelet] Creating a ConfigMap "kubelet-config" in namespace kube-system with the configuration for the kubelets in the cluster
I1223 02:31:37.590067 1574840 uploadconfig.go:132] [upload-config] Preserving the CRISocket information for the control-plane node
I1223 02:31:37.590110 1574840 patchnode.go:31] [patchnode] Uploading the CRI Socket information "unix:///var/run/containerd/containerd.sock" to the Node API object "aiml" as an annotation
[upload-certs] Skipping phase. Please see --upload-certs
[mark-control-plane] Marking the node aiml as control-plane by adding the labels: [node-role.kubernetes.io/control-plane node.kubernetes.io/exclude-from-external-load-balancers]
[mark-control-plane] Marking the node aiml as control-plane by adding the taints [node-role.kubernetes.io/control-plane:NoSchedule]
[bootstrap-token] Using token: v9ppzx.5phkb4mdl4ojq72z
[bootstrap-token] Configuring bootstrap tokens, cluster-info ConfigMap, RBAC Roles
[bootstrap-token] Configured RBAC rules to allow Node Bootstrap tokens to get nodes
[bootstrap-token] Configured RBAC rules to allow Node Bootstrap tokens to post CSRs in order for nodes to get long term certificate credentials
[bootstrap-token] Configured RBAC rules to allow the csrapprover controller automatically approve CSRs from a Node Bootstrap Token
[bootstrap-token] Configured RBAC rules to allow certificate rotation for all node client certificates in the cluster
[bootstrap-token] Creating the "cluster-info" ConfigMap in the "kube-public" namespace
I1223 02:31:37.657235 1574840 clusterinfo.go:47] [bootstrap-token] loading admin kubeconfig
I1223 02:31:37.658318 1574840 clusterinfo.go:58] [bootstrap-token] copying the cluster from admin.conf to the bootstrap kubeconfig
I1223 02:31:37.658815 1574840 clusterinfo.go:70] [bootstrap-token] creating/updating ConfigMap in kube-public namespace
I1223 02:31:37.663466 1574840 clusterinfo.go:84] creating the RBAC rules for exposing the cluster-info ConfigMap in the kube-public namespace
I1223 02:31:37.742912 1574840 request.go:661] Waited for 79.295582ms due to client-side throttling, not priority and fairness, request: POST:https://10.200.105.55:6443/apis/rbac.authorization.k8s.io/v1/namespaces/kube-public/roles?timeout=10s
I1223 02:31:37.943026 1574840 request.go:661] Waited for 194.37648ms due to client-side throttling, not priority and fairness, request: POST:https://10.200.105.55:6443/apis/rbac.authorization.k8s.io/v1/namespaces/kube-public/rolebindings?timeout=10s
I1223 02:31:37.947223 1574840 kubeletfinalize.go:91] [kubelet-finalize] Assuming that kubelet client certificate rotation is enabled: found "/var/lib/kubelet/pki/kubelet-client-current.pem"
[kubelet-finalize] Updating "/etc/kubernetes/kubelet.conf" to point to a rotatable kubelet client certificate and key
I1223 02:31:37.948938 1574840 kubeletfinalize.go:145] [kubelet-finalize] Restarting the kubelet to enable client certificate rotation
[addons] Applied essential addon: CoreDNS
I1223 02:31:38.743391 1574840 request.go:661] Waited for 172.413439ms due to client-side throttling, not priority and fairness, request: POST:https://10.200.105.55:6443/apis/rbac.authorization.k8s.io/v1/namespaces/kube-system/roles?timeout=10s
I1223 02:31:38.942853 1574840 request.go:661] Waited for 192.329088ms due to client-side throttling, not priority and fairness, request: POST:https://10.200.105.55:6443/apis/rbac.authorization.k8s.io/v1/namespaces/kube-system/rolebindings?timeout=10s
[addons] Applied essential addon: kube-proxy

Your Kubernetes control-plane has initialized successfully!

To start using your cluster, you need to run the following as a regular user:

  mkdir -p $HOME/.kube
  sudo cp -i /etc/kubernetes/admin.conf $HOME/.kube/config
  sudo chown $(id -u):$(id -g) $HOME/.kube/config

Alternatively, if you are the root user, you can run:

  export KUBECONFIG=/etc/kubernetes/admin.conf

You should now deploy a pod network to the cluster.
Run "kubectl apply -f [podnetwork].yaml" with one of the options listed at:
  https://kubernetes.io/docs/concepts/cluster-administration/addons/

Then you can join any number of worker nodes by running the following on each as root:

kubeadm join 10.200.105.55:6443 --token v9ppzx.5phkb4mdl4ojq72z \
	--discovery-token-ca-cert-hash sha256:c1cf65f6ef41f9c94d2024f6b5805c5daba2b05e1222b52b029cf4e26531c22a 
Setting up kubectl for user: sridharkn in home directory: /home/sridharkn
node/aiml untainted
node/aiml untainted
NAMESPACE     NAME                           READY   STATUS    RESTARTS   AGE
kube-system   etcd-aiml                      0/1     Pending   0          1s
kube-system   kube-apiserver-aiml            0/1     Pending   0          1s
kube-system   kube-controller-manager-aiml   0/1     Pending   0          3s
kube-system   kube-scheduler-aiml            0/1     Pending   0          3s
***************************************************************************************************************
						Installing CNI			
***************************************************************************************************************
poddisruptionbudget.policy/calico-kube-controllers created
serviceaccount/calico-kube-controllers created
serviceaccount/calico-node created
serviceaccount/calico-cni-plugin created
configmap/calico-config created
customresourcedefinition.apiextensions.k8s.io/bgpconfigurations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/bgpfilters.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/bgppeers.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/blockaffinities.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/caliconodestatuses.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/clusterinformations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/felixconfigurations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/globalnetworkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/globalnetworksets.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/hostendpoints.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipamblocks.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipamconfigs.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipamhandles.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ippools.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/ipreservations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/kubecontrollersconfigurations.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/networkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/networksets.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/stagedglobalnetworkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/stagedkubernetesnetworkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/stagednetworkpolicies.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/tiers.crd.projectcalico.org created
customresourcedefinition.apiextensions.k8s.io/adminnetworkpolicies.policy.networking.k8s.io created
customresourcedefinition.apiextensions.k8s.io/baselineadminnetworkpolicies.policy.networking.k8s.io created
clusterrole.rbac.authorization.k8s.io/calico-kube-controllers created
clusterrole.rbac.authorization.k8s.io/calico-node created
clusterrole.rbac.authorization.k8s.io/calico-cni-plugin created
clusterrole.rbac.authorization.k8s.io/calico-tier-getter created
clusterrolebinding.rbac.authorization.k8s.io/calico-kube-controllers created
clusterrolebinding.rbac.authorization.k8s.io/calico-node created
clusterrolebinding.rbac.authorization.k8s.io/calico-cni-plugin created
clusterrolebinding.rbac.authorization.k8s.io/calico-tier-getter created
daemonset.apps/calico-node created
deployment.apps/calico-kube-controllers created
waiting for 4/7 pods running in namespace [kube-system] with keyword [Running]
> waiting for 5/7 pods running in namespace [kube-system] with keyword [Running]
> waiting for 6/7 pods running in namespace [kube-system] with keyword [Running]
> waiting for 6/7 pods running in namespace [kube-system] with keyword [Running]
> waiting for 6/7 pods running in namespace [kube-system] with keyword [Running]
> waiting for 9/7 pods running in namespace [kube-system] with keyword [Running]
***************************************************************************************************************
NAMESPACE     NAME                                       READY   STATUS    RESTARTS   AGE
kube-system   calico-kube-controllers-64b69c8f54-j4j69   1/1     Running   0          24s
kube-system   calico-node-wjk26                          1/1     Running   0          24s
kube-system   coredns-668d6bf9bc-dppzm                   1/1     Running   0          24s
kube-system   coredns-668d6bf9bc-gc2bl                   1/1     Running   0          24s
kube-system   etcd-aiml                                  1/1     Running   0          29s
kube-system   kube-apiserver-aiml                        1/1     Running   0          29s
kube-system   kube-controller-manager-aiml               1/1     Running   0          31s
kube-system   kube-proxy-sttgl                           1/1     Running   0          24s
kube-system   kube-scheduler-aiml                        1/1     Running   0          31s
***************************************************************************************************************
$ # Step 4: Setup Helm and install plugins (cm-push, deploy, undeploy)
chmod +x smo-install/scripts/layer-0/0-setup-helm3.sh
bash smo-install/scripts/layer-0/0-setup-helm3.sh$ $ 
Helm is already installed. Skipping installation.
Checking HELM ...
version.BuildInfo{Version:"v3.18.6", GitCommit:"b76a950f6835474e0906b96c9ec68a2eff3a6430", GitTreeState:"clean", GoVersion:"go1.24.6"}
Git is already installed. Skipping installation.
Helm cm-push plugin is not installed. Installing cm-push ...
Downloading and installing helm-push v0.10.3 ...
--2025-12-23 02:32:40--  https://nexus.o-ran-sc.org/content/repositories/thirdparty/chartmuseum/helm-push/v0.10.3/helm-push-v0.10.3.tar.gz
Resolving nexus.o-ran-sc.org (nexus.o-ran-sc.org)... 38.108.68.158
Connecting to nexus.o-ran-sc.org (nexus.o-ran-sc.org)|38.108.68.158|:443... connected.
HTTP request sent, awaiting response... 200 OK
Length: 11109788 (11M) [application/x-gzip]
Saving to: ‘helm-push-v0.10.3.tar.gz’

helm-push-v0.10.3.t 100%[===================>]  10.59M  3.48MB/s    in 3.0s    

2025-12-23 02:32:46 (3.48 MB/s) - ‘helm-push-v0.10.3.tar.gz’ saved [11109788/11109788]

Make is already installed. Skipping installation.
Helm undeploy plugin is not installed. Installing undeploy plugin ...
Installed plugin: undeploy
Helm deploy plugin is not installed. Installing deploy plugin ...
Installed plugin: deploy
"oran-snapshot" has been added to your repositories
"oran-release" has been added to your repositories
"strimzi" has been added to your repositories
"openebs" has been added to your repositories
"mariadb-operator" has been added to your repositories
Hang tight while we grab the latest from your chart repositories...
...Successfully got an update from the "openebs" chart repository
...Successfully got an update from the "strimzi" chart repository
...Successfully got an update from the "mariadb-operator" chart repository
...Successfully got an update from the "oran-release" chart repository
...Successfully got an update from the "oran-snapshot" chart repository
Update Complete. ⎈Happy Helming!⎈
$ # Step 5: Verify Helm plugins are installed
helm plugin list
helm repo list$ NAME    	VERSION	DESCRIPTION                                                                                         
deploy  	1.0.0  	install (upgrade if release exists) parent charty and all subcharts as separate but related releases
cm-push 	0.10.3 	Push chart package to ChartMuseum                                                                   
undeploy	1.0.0  	delete parent chart and subcharts that were deployed as separate releases                           
$ # Step 6: Install SMO
cd smo-install/scripts/layer-2
chmod +x 2-install-oran.sh
bash 2-install-oran.sh default release
This command consists of multiple subcommands to interact with chart repositories.

It can be used to add, remove, list, and index chart repositories.

Usage:
  helm repo [command]

Available Commands:
  add         add a chart repository
  index       generate an index file given a directory containing packaged charts
  list        list chart repositories
  remove      remove one or more chart repositories
  update      update information of available charts locally from chart repositories

Flags:
  -h, --help   help for repo

Global Flags:
      --burst-limit int                 client-side default throttling limit (default 100)
      --debug                           enable verbose output
      --kube-apiserver string           the address and the port for the Kubernetes API server
      --kube-as-group stringArray       group to impersonate for the operation, this flag can be repeated to specify multiple groups.
      --kube-as-user string             username to impersonate for the operation
      --kube-ca-file string             the certificate authority file for the Kubernetes API server connection
      --kube-context string             name of the kubeconfig context to use
      --kube-insecure-skip-tls-verify   if true, the Kubernetes API server's certificate will not be checked for validity. This will make your HTTPS connections insecure
      --kube-tls-server-name string     server name to use for Kubernetes API server certificate validation. If it is not provided, the hostname used to contact the server is used
      --kube-token string               bearer token used for authentication
      --kubeconfig string               path to the kubeconfig file
  -n, --namespace string                namespace scope for this request
      --qps float32                     queries per second used when communicating with the Kubernetes API, not including bursting
      --registry-config string          path to the registry config file (default "/home/sridharkn/.config/helm/registry/config.json")
      --repository-cache string         path to the directory containing cached repository indexes (default "/home/sridharkn/.cache/helm/repository")
      --repository-config string        path to the file containing repository names and URLs (default "/home/sridharkn/.config/helm/repositories.yaml")

Use "helm repo [command] --help" for more information about a command.
$ $ $ 
Using helm override flavour: default
Pre configuring SMO ...
Release "openebs" does not exist. Installing it now.
storageclass.storage.k8s.io/smo-storage created
Installing MariaDB operator...
namespace/mariadb-operator created
SMO pre configuration done.
Starting ONAP & NONRTRIC namespaces ...
### Installing Strimzi Kafka Operator (From Helm repo strimzi) ###
Release "mariadb-operator" does not exist. Installing it now.
namespace/onap created
### Installing ONAP part (From Helm repo oran-snapshot) ###
Release "mariadb-operator-crds" does not exist. Installing it now.
Release "strimzi-kafka-operator" does not exist. Installing it now.
v3.18.6
Use cache dir: /home/sridharkn/.local/share/helm/plugins/deploy/cache
0
0
0
0
fetching oran-snapshot/onap
NAME: openebs
LAST DEPLOYED: Tue Dec 23 02:33:28 2025
NAMESPACE: openebs
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
Successfully installed OpenEBS.

Check the status by running: kubectl get pods -n openebs

The default values will install both Local PV and Replicated PV. However,
the Replicated PV will require additional configuration to be fuctional.
The Local PV offers non-replicated local storage using 3 different storage
backends i.e Hostpath, LVM and ZFS, while the Replicated PV provides one replicated highly-available
storage backend i.e Mayastor.

For more information, 
- view the online documentation at https://openebs.io/docs
- connect with an active community on our Kubernetes slack channel.
        - Sign up to Kubernetes slack: https://slack.k8s.io
        - #openebs channel: https://kubernetes.slack.com/messages/openebs
NAME: mariadb-operator
LAST DEPLOYED: Tue Dec 23 02:33:28 2025
NAMESPACE: mariadb-operator
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
mariadb-operator has been successfully deployed! 🦭

Not sure what to do next? 😅 Check out:
https://github.com/mariadb-operator/mariadb-operator/blob/main/docs/quickstart.md
NAME: mariadb-operator-crds
LAST DEPLOYED: Tue Dec 23 02:33:28 2025
NAMESPACE: mariadb-operator
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
mariadb-operator CRDs have been successfully installed! 🦭

To complete the mariadb-operator installation, please now proceed to install the
mariadb-operator chart:
https://github.com/mariadb-operator/mariadb-operator?tab=readme-ov-file#helm-installation
NAME: strimzi-kafka-operator
LAST DEPLOYED: Tue Dec 23 02:33:31 2025
NAMESPACE: strimzi-system
STATUS: deployed
REVISION: 1
TEST SUITE: None
NOTES:
Thank you for installing strimzi-kafka-operator-0.45.0

To create a Kafka cluster refer to the following documentation.

https://strimzi.io/docs/operators/latest/deploying.html#deploying-cluster-operator-helm-chart-str
history.go:56: 2025-12-23 02:33:40.765193312 +0000 UTC m=+0.072730136 [debug] getting history for release onap
install.go:225: 2025-12-23 02:33:40.770323215 +0000 UTC m=+0.077860039 [debug] Original chart version: ""
install.go:242: 2025-12-23 02:33:40.770388294 +0000 UTC m=+0.077925121 [debug] CHART PATH: /home/sridharkn/.local/share/helm/plugins/deploy/cache/onap

release "onap" deployed
release "onap-roles-wrapper" deployed
release "onap-repository-wrapper" deployed
release "onap-strimzi" deployed
waiting for onap-strimzi-entity-operator to be deployed
onap-strimzi-entity-operator not found. Retry 1/60
onap-strimzi-entity-operator not found. Retry 2/60
onap-strimzi-entity-operator not found. Retry 3/60
onap-strimzi-entity-operator not found. Retry 4/60
onap-strimzi-entity-operator not found. Retry 5/60
onap-strimzi-entity-operator not found. Retry 6/60
onap-strimzi-entity-operator found. Waiting for pod intialisation
release "onap-strimzi" deployed
release "onap-mariadb-galera" deployed
release "onap-postgres" deployed
release "onap-cps" deployed
release "onap-dcaegen2-services" deployed
release "onap-policy" deployed
release "onap-repository-wrapper" deployed
release "onap-roles-wrapper" deployed
release "onap-sdnc" deployed
namespace/nonrtric created
### Installing ORAN NONRTRIC part ###
Installing NONRTRIC from HELM Repo : oran-snapshot
Release "oran-nonrtric" does not exist. Installing it now.
NAME: oran-nonrtric
LAST DEPLOYED: Tue Dec 23 02:35:44 2025
NAMESPACE: nonrtric
STATUS: deployed
REVISION: 1
TEST SUITE: None
Copying dmeparticipant-ku from onap namespace...
dmeparticipant-ku found
secret/dmeparticipant-ku created
Waiting for the Kong deployment to be ready...
deployment.apps/oran-nonrtric-kong condition met
### Installing ORAN SMO part ###
namespace/smo created
Installing SMO from HELM Repo : oran-snapshot
Release "oran-smo" does not exist. Installing it now.
NAME: oran-smo
LAST DEPLOYED: Tue Dec 23 02:36:41 2025
NAMESPACE: smo
STATUS: deployed
REVISION: 1
TEST SUITE: None
Copying topology-exposure-ku from onap namespace...
topology-exposure-ku found
secret/topology-exposure-ku created
Copying topology-ingestion-ku from onap namespace...
topology-ingestion-ku found
secret/topology-ingestion-ku created
Copying ncmp-to-teiv-adapter-ku from onap namespace...
ncmp-to-teiv-adapter-ku found
secret/ncmp-to-teiv-adapter-ku created
Copying focom-to-teiv-adapter-ku from onap namespace...
focom-to-teiv-adapter-ku found
secret/focom-to-teiv-adapter-ku created
Copying redpanda-console-ku from onap namespace...
redpanda-console-ku found
secret/redpanda-console-ku created
Starting SMO Post Configuration ...
Waiting for capifcore deployment
deployment.apps/capifcore condition met
Waiting for servicemanager deployment
deployment.apps/servicemanager condition met
Waiting for kong deployment
deployment.apps/oran-nonrtric-kong condition met
Preloading Service Manager from ../packages/post-configuration/servicemanager-preconfig-nonrtric.yaml
ExternalIP not found, using InternalIP
Service Manager will be accessed at: http://10.200.105.55:31575
Find running services
Register provider for servicemanager
Publish  service  for servicemanager
Register provider for rappmanager
Publish  service  for rappmanager
Register provider for policymanagementservice
Publish  service  for policymanagementservice
Register provider for informationservice
Publish  service  for informationservice
Service Manager preload completed for ../packages/post-configuration/servicemanager-preconfig-nonrtric.yaml
Preloading Service Manager from ../packages/post-configuration/servicemanager-preconfig-smo.yaml
ExternalIP not found, using InternalIP
Service Manager will be accessed at: http://10.200.105.55:31575
Find running services
Register provider for policy-apex-pdp
Publish  service  for policy-apex-pdp
Register provider for policy-api
Publish  service  for policy-api
Register provider for policy-pap
Publish  service  for policy-pap
Register provider for sdnc-oam
Publish  service  for sdnc-oam
Register provider for sdnc-web
Publish  service  for sdnc-web
Register provider for cps-core
Publish  service  for cps-core
Register provider for ncmp-dmi-plugin
Publish  service  for ncmp-dmi-plugin
Register provider for dcae-ves-collector
Publish  service  for dcae-ves-collector
Register provider for topology-exposure
Publish  service  for topology-exposure
Register provider for influxdb2
Publish  service  for influxdb2
Service Manager preload completed for ../packages/post-configuration/servicemanager-preconfig-smo.yaml
SMO post configuration done.
NAME                                               READY   STATUS            RESTARTS   AGE
mariadb-galera-0                                   1/1     Running           0          3m56s
onap-cps-core-67f977b774-vr4l9                     0/1     PodInitializing   0          3m40s
onap-cps-postgres-init-config-job-p6q4k            0/1     Completed         0          3m40s
onap-cps-temporal-64d88ffcc4-rhn8p                 1/1     Running           0          3m40s
onap-cps-temporal-db-0                             1/1     Running           0          3m40s
onap-dcae-ves-collector-5d7b77bf95-2frf2           0/1     Init:0/1          0          17s
onap-dcae-ves-collector-66f4dcb7d6-847jn           1/1     Running           0          3m37s
onap-ncmp-dmi-plugin-664784d768-cqflk              0/1     Init:0/2          0          3m40s
onap-policy-apex-pdp-75498445cb-jdmgk              1/1     Running           0          3m27s
onap-policy-api-6d9d46f84b-4cr6j                   0/1     Init:1/4          0          3m26s
onap-policy-clamp-ac-a1pms-ppnt-664757fb94-c9clz   1/1     Running           0          3m27s
onap-policy-clamp-ac-http-ppnt-f65c6fc7c-jxrjd     1/1     Running           0          3m27s
onap-policy-clamp-ac-k8s-ppnt-78fb99b7db-w8l9t     1/1     Running           0          3m26s
onap-policy-clamp-ac-kserve-ppnt-96bd46764-mmg8j   1/1     Running           0          3m26s
onap-policy-clamp-ac-pf-ppnt-d69dcc66d-cl6cl       1/1     Running           0          3m27s
onap-policy-clamp-runtime-acm-6b79d6cd59-gkxxv     0/1     Init:0/2          0          3m26s
onap-policy-pap-67fcd9874d-cpmxr                   0/1     Init:0/2          0          3m26s
onap-policy-postgres-primary-5fcc987884-pkcgz      1/1     Running           0          3m26s
onap-policy-postgres-replica-55566db74b-6vs56      1/1     Running           0          3m27s
onap-postgres-primary-757f57c74-km42s              1/1     Running           0          3m48s
onap-postgres-replica-66b479ddc6-65smh             1/1     Running           0          3m48s
onap-sdnc-0                                        0/1     Init:1/3          0          3m19s
onap-sdnc-ansible-server-6f6cbf88fd-s7lz6          0/1     Init:1/2          0          3m19s
onap-sdnc-sdnrdb-init-job-rpbnp                    0/1     PodInitializing   0          3m19s
onap-sdnc-web-5f896b94f-6mgfq                      0/1     Init:0/1          0          3m19s
onap-strimzi-entity-operator-5c9965dbb9-xz54m      2/2     Running           0          4m19s
onap-strimzi-onap-strimzi-broker-0                 1/1     Running           0          5m2s
onap-strimzi-onap-strimzi-controller-1             0/1     Running           0          18s
NAME                                       READY   STATUS      RESTARTS   AGE
a1-sim-osc-0-7756867694-9vkc6              1/1     Running     0          3m7s
a1-sim-osc-1-775ff747-wsbtj                1/1     Running     0          3m7s
a1-sim-std-0-75cd5d48c5-b9qmx              1/1     Running     0          3m7s
a1-sim-std-1-6457947b84-klpvn              1/1     Running     0          3m7s
a1-sim-std2-0-7fd4898bf4-pgtvd             1/1     Running     0          3m7s
a1-sim-std2-1-67f59bfb67-76ph2             1/1     Running     0          3m7s
capifcore-ccbfbff56-8kc2j                  1/1     Running     0          3m7s
controlpanel-56cf48cb74-zxf7s              1/1     Running     0          3m7s
dmaapadapterservice-0                      1/1     Running     0          3m7s
dmeparticipant-587677f696-z8hml            1/1     Running     0          3m7s
informationservice-0                       1/1     Running     0          3m7s
nonrtricgateway-86d47b667c-x22mp           1/1     Running     0          3m7s
oran-nonrtric-kong-7bfdd99dd-wt2s7         2/2     Running     0          3m7s
oran-nonrtric-kong-init-migrations-84c55   0/1     Completed   0          3m7s
oran-nonrtric-postgresql-0                 1/1     Running     0          3m7s
policymanagementservice-0                  1/1     Running     0          3m7s
rappmanager-0                              1/1     Running     0          3m7s
servicemanager-6d68c57877-wsb68            1/1     Running     0          3m7s
topology-7d86cfb845-p8mg7                  1/1     Running     0          3m7s
NAME                                     READY   STATUS              RESTARTS      AGE
bundle-server-54cbbbc9d7-2c5hb           0/1     ContainerCreating   0             14s
cps-kafkauser-patch-bgk6s                0/1     Completed           0             58s
dfc-0                                    0/2     PodInitializing     0             14s
focom-to-teiv-adapter-6ffc7446c8-w8vjg   0/1     ContainerCreating   0             14s
ics-init-pb4zj                           0/1     PodInitializing     0             14s
influxdb2-0                              0/1     ContainerCreating   0             14s
influxdb2-init-nzzzd                     0/1     ContainerCreating   0             14s
kafka-client                             0/1     ContainerCreating   0             14s
kafka-producer-pm-json2influx-0          0/1     PodInitializing     0             14s
kafka-producer-pm-json2kafka-0           0/1     PodInitializing     0             14s
kafka-producer-pm-xml2json-0             0/1     PodInitializing     0             14s
keycloak-649dd6dd8b-7dvx4                1/1     Running             0             113s
keycloak-init-gfkjx                      0/1     Completed           0             111s
keycloak-proxy-6b76854c98-898z4          1/1     Running             0             112s
minio-0                                  0/1     PodInitializing     0             14s
minio-client                             0/1     ContainerCreating   0             14s
ncmp-to-teiv-adapter-8568c94dc6-t64xt    0/1     ContainerCreating   0             14s
opa-76849b588f-2g2tv                     0/1     ContainerCreating   0             14s
oran-smo-postgresql-0                    0/1     Init:0/1            0             14s
pm-producer-json2kafka-0                 0/2     PodInitializing     0             14s
pmlog-0                                  0/2     PodInitializing     0             14s
policy-kafkauser-patch-rxsmx             0/1     Completed           0             51s
redpanda-console-5f867cf878-kdx2v        0/1     PodInitializing     0             14s
strimzi-patch-2p4h7                      0/1     Completed           0             43s
topology-exposure-5c6d86795-fd8jj        0/1     Init:Error          1 (12s ago)   14s
topology-ingestion-69bbddd8c7-hpkcl      0/1     Init:Error          1 (12s ago)   14s
vescollector-patch-z7nlb                 0/1     Completed           0             19s
NAME               STATUS   AGE
default            Active   7m25s
kube-node-lease    Active   7m25s
kube-public        Active   7m25s
kube-system        Active   7m25s
mariadb-operator   Active   5m32s
nonrtric           Active   3m19s
onap               Active   5m32s
openebs            Active   5m32s
smo                Active   2m20s
strimzi-system     Active   5m28s
SMO Installation completed successfully in 5 minutes.
$ 
kubectl get --help' for usage.
$ kubectl get pods -A
NAMESPACE          NAME                                                READY   STATUS            RESTARTS      AGE
kube-system        calico-kube-controllers-64b69c8f54-j4j69            1/1     Running           0             10m
kube-system        calico-node-wjk26                                   1/1     Running           0             10m
kube-system        coredns-668d6bf9bc-dppzm                            1/1     Running           0             10m
kube-system        coredns-668d6bf9bc-gc2bl                            1/1     Running           0             10m
kube-system        etcd-aiml                                           1/1     Running           0             10m
kube-system        kube-apiserver-aiml                                 1/1     Running           0             10m
kube-system        kube-controller-manager-aiml                        1/1     Running           0             10m
kube-system        kube-proxy-sttgl                                    1/1     Running           0             10m
kube-system        kube-scheduler-aiml                                 1/1     Running           0             10m
mariadb-operator   mariadb-operator-5876659c44-47fdc                   1/1     Running           0             8m37s
mariadb-operator   mariadb-operator-cert-controller-768c7889d6-5mm24   1/1     Running           0             8m37s
mariadb-operator   mariadb-operator-webhook-7b8697bb-pxnqs             1/1     Running           0             8m37s
nonrtric           a1-sim-osc-0-7756867694-9vkc6                       1/1     Running           0             6m14s
nonrtric           a1-sim-osc-1-775ff747-wsbtj                         1/1     Running           0             6m14s
nonrtric           a1-sim-std-0-75cd5d48c5-b9qmx                       1/1     Running           0             6m14s
nonrtric           a1-sim-std-1-6457947b84-klpvn                       1/1     Running           0             6m14s
nonrtric           a1-sim-std2-0-7fd4898bf4-pgtvd                      1/1     Running           0             6m14s
nonrtric           a1-sim-std2-1-67f59bfb67-76ph2                      1/1     Running           0             6m14s
nonrtric           capifcore-ccbfbff56-8kc2j                           1/1     Running           0             6m14s
nonrtric           controlpanel-56cf48cb74-zxf7s                       1/1     Running           0             6m14s
nonrtric           dmaapadapterservice-0                               1/1     Running           0             6m14s
nonrtric           dmeparticipant-587677f696-z8hml                     1/1     Running           0             6m14s
nonrtric           informationservice-0                                1/1     Running           0             6m14s
nonrtric           nonrtricgateway-86d47b667c-x22mp                    1/1     Running           0             6m14s
nonrtric           oran-nonrtric-kong-7bfdd99dd-wt2s7                  2/2     Running           0             6m14s
nonrtric           oran-nonrtric-kong-init-migrations-84c55            0/1     Completed         0             6m14s
nonrtric           oran-nonrtric-postgresql-0                          1/1     Running           0             6m14s
nonrtric           policymanagementservice-0                           1/1     Running           0             6m14s
nonrtric           rappmanager-0                                       1/1     Running           0             6m14s
nonrtric           servicemanager-6d68c57877-wsb68                     1/1     Running           0             6m14s
nonrtric           topology-7d86cfb845-p8mg7                           1/1     Running           0             6m14s
onap               mariadb-galera-0                                    1/1     Running           0             7m3s
onap               onap-cps-core-67f977b774-vr4l9                      1/1     Running           0             6m47s
onap               onap-cps-postgres-init-config-job-p6q4k             0/1     Completed         0             6m47s
onap               onap-cps-temporal-64d88ffcc4-rhn8p                  1/1     Running           0             6m47s
onap               onap-cps-temporal-db-0                              1/1     Running           0             6m47s
onap               onap-dcae-ves-collector-5d7b77bf95-2frf2            1/1     Running           0             3m24s
onap               onap-ncmp-dmi-plugin-664784d768-cqflk               0/1     PodInitializing   0             6m47s
onap               onap-policy-apex-pdp-75498445cb-jdmgk               1/1     Running           0             6m34s
onap               onap-policy-api-6d9d46f84b-4cr6j                    0/1     Init:2/4          0             6m33s
onap               onap-policy-clamp-ac-a1pms-ppnt-664757fb94-c9clz    1/1     Running           0             6m34s
onap               onap-policy-clamp-ac-http-ppnt-f65c6fc7c-jxrjd      1/1     Running           0             6m34s
onap               onap-policy-clamp-ac-k8s-ppnt-78fb99b7db-w8l9t      1/1     Running           0             6m33s
onap               onap-policy-clamp-ac-kserve-ppnt-96bd46764-mmg8j    1/1     Running           0             6m33s
onap               onap-policy-clamp-ac-pf-ppnt-d69dcc66d-cl6cl        1/1     Running           0             6m34s
onap               onap-policy-clamp-runtime-acm-6b79d6cd59-gkxxv      0/1     Init:0/2          0             6m33s
onap               onap-policy-pap-67fcd9874d-cpmxr                    0/1     Init:0/2          0             6m33s
onap               onap-policy-postgres-primary-5fcc987884-pkcgz       1/1     Running           0             6m33s
onap               onap-policy-postgres-replica-55566db74b-6vs56       1/1     Running           0             6m34s
onap               onap-postgres-primary-757f57c74-km42s               1/1     Running           0             6m55s
onap               onap-postgres-replica-66b479ddc6-65smh              1/1     Running           0             6m55s
onap               onap-sdnc-0                                         1/1     Running           0             6m26s
onap               onap-sdnc-ansible-server-6f6cbf88fd-s7lz6           0/1     PodInitializing   0             6m26s
onap               onap-sdnc-sdnrdb-init-job-rpbnp                     0/1     Completed         0             6m26s
onap               onap-sdnc-web-5f896b94f-6mgfq                       0/1     PodInitializing   0             6m26s
onap               onap-strimzi-entity-operator-5c9965dbb9-xz54m       2/2     Running           0             7m26s
onap               onap-strimzi-onap-strimzi-broker-0                  1/1     Running           0             2m52s
onap               onap-strimzi-onap-strimzi-controller-1              1/1     Running           0             3m25s
openebs            openebs-localpv-provisioner-569b6d7f77-9f26l        1/1     Running           0             8m38s
smo                bundle-server-54cbbbc9d7-2c5hb                      1/1     Running           0             3m20s
smo                cps-kafkauser-patch-bgk6s                           0/1     Completed         0             4m4s
smo                dfc-0                                               0/2     PodInitializing   0             3m20s
smo                focom-to-teiv-adapter-6ffc7446c8-w8vjg              1/1     Running           0             3m20s
smo                ics-init-pb4zj                                      0/1     PodInitializing   0             3m20s
smo                influxdb2-0                                         1/1     Running           0             3m20s
smo                influxdb2-init-nzzzd                                0/1     Completed         0             3m20s
smo                kafka-client                                        1/1     Running           0             3m20s
smo                kafka-producer-pm-json2influx-0                     0/1     PodInitializing   0             3m20s
smo                kafka-producer-pm-json2kafka-0                      0/1     PodInitializing   0             3m20s
smo                kafka-producer-pm-xml2json-0                        0/1     PodInitializing   0             3m20s
smo                keycloak-649dd6dd8b-7dvx4                           1/1     Running           0             4m59s
smo                keycloak-init-gfkjx                                 0/1     Completed         0             4m57s
smo                keycloak-proxy-6b76854c98-898z4                     1/1     Running           0             4m58s
smo                minio-0                                             0/1     PodInitializing   0             3m20s
smo                minio-client                                        1/1     Running           0             3m20s
smo                ncmp-to-teiv-adapter-8568c94dc6-t64xt               1/1     Running           0             3m20s
smo                opa-76849b588f-2g2tv                                1/1     Running           0             3m20s
smo                oran-smo-postgresql-0                               0/1     Init:0/1          0             3m20s
smo                pm-producer-json2kafka-0                            0/2     PodInitializing   0             3m20s
smo                pmlog-0                                             0/2     PodInitializing   0             3m20s
smo                policy-kafkauser-patch-rxsmx                        0/1     Completed         0             3m57s
smo                redpanda-console-5f867cf878-kdx2v                   0/1     PodInitializing   0             3m20s
smo                strimzi-patch-2p4h7                                 0/1     Completed         0             3m49s
smo                topology-exposure-5c6d86795-fd8jj                   0/1     Init:Error        5 (99s ago)   3m20s
smo                topology-ingestion-69bbddd8c7-hpkcl                 0/1     Init:Error        5 (98s ago)   3m20s
smo                vescollector-patch-z7nlb                            0/1     Completed         0             3m25s
strimzi-system     strimzi-cluster-operator-b8f99bbc4-skrpt            1/1     Running           0             8m33s
$ 


```
