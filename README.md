munin-gluster
===============

Munin GlusterFS plugin for glusterfs 3.2+

This plugin can graph:
 - Open and maximum fd count
 - Read performance per brick (tested performance, not actual read throughput)
 - Write performance per brick (tested performance, not actual write throughput)

####Examples

Create a symbolic link to `glusterfs_<volume>_<brick-server>_<open|readperf|writeperf>`:

       ln -s /usr/share/munin/plugins/glusterfs_ /etc/munin/plugins/glusterfs_volume1__open
           graph open calls for all bricks

       ln -s /usr/share/munin/plugins/glusterfs_ /etc/munin/plugins/glusterfs_volume2_192.168.1.3_writeperf
           graph write performance for brick on 192.168.1.3 belonging to volume volume2


####Munin configuration
Add the following to your /etc/munin/plugin-conf.d/gluster.conf:

    [glusterfs_*]
     user root                   # Mandatory
     env.blocksize <blocksize>   # Optional
     env.blockcount <blockcount> # Optional


####Revision log:
 - 1: Add multiple volumes support, cleanup graphs
 - 0.1  01/31/2013: First version of the GlusterFS Munin plugin
