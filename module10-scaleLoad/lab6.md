# Important Steps
- In this lab we start with a very very similar infrastructure from lab 5. This time, we are using a load balancer to distribute the load into different AZ.

![](./images/1-architecture.png)

- We create the image so that it is scaled automatically:

![](./images/2-create_image.png)

- Now we create a load balancer, the main part of this lab. This load balancer will distribute the load between multiple EC2 instances. To do this, first we create the target groups that the load balancer will route packets to:

![](./images/3-target_group.png)

- Now we create an application load balancer that operates at request level (layer 7)

![](./images/4-load_balancer_creation.png)
![](./images/5-load_balancer_created.png)

- We create an EC2 instance template. When it needs to scale up and needs more instances, these instances will look like this template:

![](./images/6-ec2_template.png)

- The load balacner is configured correctly:

![](./images/7-ELB_config_1.png)
![](./images/8-ELB_config_2.png)

- The number of instances used will go from 2 to 6 depending on the load received. We can see there are 2 more instances now because the minimum set was 2:

![](./images/9-new_EC2_instances.png)

- Now we need to check it is working correctly. First we see the load balancer is chill because the CPU usage is low:

![](./images/10-target_group_correct.png)
![](./images/11-test_ELB.png)
![](./images/12-alarm_test.png)

- Then the CPU usage goes to 100% and it needs to rescale. Now we can see the alarms have been triggered and that there are more than 2 instances now:

![](./images/13-website_load_test.png)
![](./images/14-alarm_test_2.png)
![](./images/15-alarm_test_3.png)
![](./images/16-ec2_instances_scaled_up.png)