# dm-zoned-cgroup
make weighted proportional I/O bandwidth sharing for dm-zoned 

# path
/usr/src/{kernel_Ver}/driver/md/dm-zoned.h

/usr/src/{kernel_Ver}/driver/md/dm-zoned-metadata.c

/usr/src/{kernel_Ver}/driver/md/dm-zoned-target.c 

# how to use
First you need to use dm-zoned-tools 

And make device (may find device name dm-0)

mount that device 

# set weight
After you make the device, need to make Cgroup 

mkdir /sys/fs/cgroup/blkio/{cgroup_name} 

echo {weight} >> /sys/fs/cgroup/blkio/{cgroup_name}/blkio.dmz.weight 

- weight value must between 10~1000 

# I/O test
echo $$ > /sys/fs/cgroup/blkio/{cgroup_name}/tasks
