# Create a load balancer

1. Launch EC2 dashboard
2. Load Balancers -> Create Load Balancer
   1. Select type (application, network, gateway, classic)
   2. Give name
   3. Choose internet-facing
   4. Select vpc
   5. Select subnet mappings
   6. Create new security group
      1. Set rule allowing traffic on desired port from anywhere (e.g. 80)
   7. Create new target group
      1. type: instances
      2. set name
      3. change port to target port (e.g. 3000)
      4. Next -> Select instances for target group
      5. Create
   8. Select newly created target group

## Enable session stickiness

This is useful to make sure that a user connecting to one load balancer stays logged in and doesn't logout by switching to a different load balancer. When enabled the user will consistently be sent to the same load balancer.

1. Target Group
2. Details -> Attributes -> Edit
3. Check Stickiness

# Creating an auto-scaling group (ASG)

1. Auto-Scaling group
2. Create auto-scaling group
3. Create a new launch template
   1. Select AMI
   2. Select instance (free: t2.micro)
   3. Select keypair (don't do this for production)
   4. Select VPC
   5. Select ec2 security group
   6. Advanced details
      1. Use user data section to start application on startup automatically

```
#!/bin/bash
echo "starting node app"
cd /home/ec2-user/pizza-luvrs-main
npm start
```

7\. Select launch template

8\. Select vpc & all subnets

9\. Attach to an existing load balancer

10\. Select target tracking policy, e.g. average network out and a value, then next until done.

## Update launch template

Select launch template -> Actions -> Set default version -> Choose new version.

## Access Load Balancer URL

1. Load Balancers
2. Select LB
3. Description -> DNS Name

# Test Load Balancer

The command `ab -n 100 -c 5 http://<loadbalancer-url>/` can be used to generate enough load to trigger the load balancer.

