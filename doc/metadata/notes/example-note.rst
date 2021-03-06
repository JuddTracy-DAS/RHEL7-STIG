The tasks in the security role enable the appropriate Linux Security Module
(LSM) for the operating system.

For Ubuntu, openSUSE and SUSE Linux Enterprise 12 systems, AppArmor is installed and
enabled. This change takes effect immediately.

For CentOS or Red Hat Enterprise Linux systems, SELinux is enabled (in
enforcing mode) and its user tools are automatically installed. If SELinux is
not in enforcing mode already, a reboot is required to enable SELinux and
relabel the filesystem.

.. warning::

    Relabeling a filesystem takes time and the server must be offline for the
    relabeling to complete. Filesystems with large amounts of files and
    filesystems on slow disks will cause the relabeling process to take more
    time.

Deployers can opt out of this change by setting the following Ansible variable:

.. code-block:: yaml

    rhel7stig_disruption_high: no
