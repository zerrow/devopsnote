## DevOps Notes

## Expanding HDD Size on Huawei Cloud

To expand the HDD size on a Huawei cloud instance, follow these steps:

## 1. Follow the Official Guide

Refer to the Huawei documentation:  
https://support.huaweicloud.com/intl/en-us/usermanual-evs/evs_01_0109.html

## 2. Check Current Disk Status

Run the following command:

    lsblk

Example output:

    vda    252:0    0  200G  0 disk
    └─vda1 252:1    0  100G  0 part /

## 3. Grow the Partition

Use `growpart` to expand the partition:

    growpart /dev/vda 1

## 4. Check Filesystem Type and Disk Info

Run:

    lsblk -f

## 5. Resize the Filesystem (for ext4)

If your filesystem is ext4, use:

    resize2fs /dev/vda1

## Done

Your disk space should now reflect the new size.
