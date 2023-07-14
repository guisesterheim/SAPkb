### 1. Update EBS volume on AWS

### 2. Once inside the OS

- Resize the logical volume: ```lvresize -r /dev/vg_hana_data/lv_hana_data```
- Resize the physical volume: ```pvresize /dev/nvme1n1 /dev/nvme7n1```
- Extend the logical volume: ```lvextend -l +100%FREE /dev/vg_hana_data/lv_hana_data```
- Grow the file system: ```xfs_growfs /hana/dataUP```

### 3. Other useful commands:
- lvs - Show logical volumes
- vgs - Show volume groups

Assumptions: 
- It's using nvme
- It's tested on Linux/SUSE
