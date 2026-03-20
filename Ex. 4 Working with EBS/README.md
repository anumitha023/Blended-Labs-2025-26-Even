# Lab 4 – Working with Amazon Elastic Block Store (EBS)

## Author

* **Name**: ANUMITHA.M.R
* **Register Number**: 212223040018

---

## Objective

The objective of this experiment is to understand how Amazon Elastic Block Store (EBS) provides persistent block-level storage for EC2 instances. This lab focuses on creating and attaching an EBS volume, formatting and mounting it on an EC2 instance, storing data, and verifying data persistence after instance reboot.

---

## Prerequisites

* Basic understanding of cloud computing concepts
* AWS account or AWS Academy Lab access
* An existing EC2 instance (Amazon Linux 2 preferred)
* Basic knowledge of Linux commands

---

## Tools Used

* AWS Management Console
* Amazon EC2
* Amazon EBS
* SSH Client (Terminal / PuTTY)

---

## Tasks Performed

### Task 1: Explore Amazon EBS

Explore the Amazon EBS service through the EC2 dashboard. Observe different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

---

### Task 2: Create an EBS Volume

Create a new EBS volume in the same Availability Zone as the EC2 instance. Choose an appropriate size and volume type.

---

### Task 3: Attach EBS Volume to EC2 Instance

Attach the created EBS volume to the running EC2 instance as an additional block device.

---

### Task 4: Format the EBS Volume

Connect to the EC2 instance using SSH and format the attached volume with a file system (for example, ext4).

---

### Task 5: Mount the EBS Volume

Mount the formatted volume to a directory in the EC2 instance (for example, /data or /mnt/ebs).

---

### Task 6: Store Data in EBS Volume

Create files and directories inside the mounted EBS volume and store sample data.

---

### Task 7: Verify Data Persistence

Reboot the EC2 instance and verify that the data stored in the EBS volume is still available after reboot.

---

## Workflow (Student Explanation)

First, I logged in to the AWS Management Console.

I navigated to the EC2 Dashboard.

I explored the Elastic Block Store (EBS) section under EC2.

I observed different volume types such as General Purpose SSD (gp2/gp3), Provisioned IOPS SSD, Throughput Optimized HDD, and Cold HDD.

I clicked on “Volumes” and selected “Create Volume.”

I chose the required volume type (General Purpose SSD – gp3).

I entered the desired storage size (for example, 8 GB).

I selected the same Availability Zone as my running EC2 instance.

I clicked on “Create Volume” to create the EBS volume.

After the volume was created, I selected the volume and clicked on “Attach Volume.”

I selected my running EC2 instance and attached the volume as a new device (for example, /dev/xvdf).

I connected to my EC2 instance using SSH from the terminal.

I checked the attached disk using the command lsblk to verify the new volume.

I formatted the attached volume using the command: sudo mkfs -t ext4 /dev/xvdf

I created a directory to mount the volume using: sudo mkdir /mnt/ebs

I mounted the volume to the directory using: sudo mount /dev/xvdf /mnt/ebs

I verified that the volume was mounted successfully using the df -h command.

I created sample files inside the mounted directory using: sudo touch /mnt/ebs/sample.txt

I stored some sample data inside the file.

I rebooted the EC2 instance from the AWS Console.

After rebooting, I reconnected to the instance using SSH.

I checked the mounted directory and verified that the stored data was still available.
## Output Screenshots (Attach 3)

### Screenshot 1: EBS Volume Created

<img width="584" height="607" alt="image" src="https://github.com/user-attachments/assets/4abd8f1b-b97c-455d-bf56-f544b31d19e1" />


### Screenshot 2: EBS Volume Attached to EC2

<img width="1003" height="535" alt="image" src="https://github.com/user-attachments/assets/d488a3ea-89bf-403c-bac5-b1055ad82ddd" />

<img width="1000" height="423" alt="image" src="https://github.com/user-attachments/assets/7a927281-9e35-4c69-bc2c-c4316eae2fa6" />

<img width="1003" height="413" alt="image" src="https://github.com/user-attachments/assets/dd035ee3-e091-4e67-a2f4-0c2bbe818089" />


### Screenshot 3: Mounted Volume with Data

<img width="1005" height="536" alt="image" src="https://github.com/user-attachments/assets/377b1799-4551-40f2-ad6e-fdb2222c44eb" />

<img width="1006" height="536" alt="image" src="https://github.com/user-attachments/assets/07f3d947-9951-4438-bb68-a3e1503482c8" />

## Result / Conclusion

This experiment demonstrated how Amazon EBS provides persistent storage for EC2 instances. By creating, attaching, formatting, and mounting an EBS volume, and by verifying data after reboot, the concept of durable block storage in the cloud was clearly understood.
