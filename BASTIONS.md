# Bastions

- These are special servers (EC2 instances in this case) that are designed to be the primary access point from the internet.

- It acts as a proxy to other EC2 instances

<br>

## Why do we need them?
- As the number of EC2 instances grows, so too does the number of administrative access points to those instances.

- Depending on where admins connect from, it is a good idea to enforce stronger network-based access controls

- A best practice in this area is to use a bastion

<br>

## How we used them
- We created an instance within our public subnet within our VPC. This would act as the bastion

- I then removed access from everywhere for the database (so for the NACL and SG etc.)

- Configure the permissions for the database so only the bastion can SSH inside it and it will send traffic