# dm-zoned-cgroup
make weighted proportional I/O bandwidth sharing for dm-zoned 

# path
/usr/src/{kernel_Ver}/driver/md/dm-zoned.h \n
/usr/src/{kernel_Ver}/driver/md/dm-zoned-metadata.c \n
/usr/src/{kernel_Ver}/driver/md/dm-zoned-target.c \n

# how to use
First you need to use dm-zoned-tools \n
And make device (may find device name dm-0)\n

mount that device \n

# set weight
After you make the device, need to make Cgroup \n
mkdir /sys/fs/cgroup/blkio/{cgroup_name} \n
echo {weight} >> /sys/fs/cgroup/blkio/{cgroup_name}/blkio.dmz.weight \n
- weight value must between 10~1000 \n

# I/O test
echo $$ > /sys/fs/cgroup/blkio/{cgroup_name}/tasks
