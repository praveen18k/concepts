
### How to attache new volume(disc) to existing EC2 ?
### Attach EBS volume to running EC2 instance
### Condition is, if EC2 disc is in us-east-1c than new EBS(Disc) should be in the same AZ. otherwise face latency and connectivity issues.

### Once create need to attach --> Go to Actions and select Attach volume and select Instance from drop down to select.

### Note: EBS volume should be in same AZ where your instance is running.

### Steps:

1. By default you cannot see the volume in Linux server, we need to do some configuration.

2. You can check the volume available or not using below command.

.......
lsblk
.......
* Create filesystem from volume.

sudo mkfs -t xfs /dev/xvdf

* After the filesystem creation run the below command

sudo yum install xfsprogs (AWS install thsi already but cross check)

* Create one directory, because we are mounting extra volume simila like F,G drives.

sudo mkdir /data

* Mount the create filesystem to this directory

sudo mount /dev/xvdf /data

* Now check new volume status

df -hT

o/p you will see two volumes now in linux server.
