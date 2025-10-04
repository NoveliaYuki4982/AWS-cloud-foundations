# Important Steps
- Create a volume:

![](./images/3-creating_volume.png)

- After attaching the volume to the instance we can connect to the instance. Then we mount this new block and we get the result below:

![](./images/4-mounted_disk.png)

- After creating a snapshot it appears in the snapshots tab:

![](./images/5-create_snapshot.png)

- Now we want to test if the snapshot is working. We now delete the file using ``sudo rm /mnt/data-store/file.txt``:

![](./images/6-deleted_file_ec2.png)

- And then we restore the snapshot we made previously to get back the deleted file. After connecting to the same EC2 instance, we can see that in this new volume we can see the file we deleted earlier:

![](./images/7-restored_volume.png)

![](./images/8-restored_file_ec2.png)