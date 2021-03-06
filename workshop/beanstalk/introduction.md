# Beanstalk

[Elastic Benstalk](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/Welcome.html) is an AWS service that allows us to deploy a web app without having to worry about what combination of AWS services might be needed. All we have to do is describe what we need and let Beanstalk do the rest (create security groups, setup a load balancer, etc).

Beanstalk also have some nice tools that aren't available in other AWS services that really add value other than the automatic setup, those are:

- The ability to manage different environments for the same app (dev, prod, testing, etc).
- Centralized panel to handle the setup for each environment.
- Great monitoring metrics.
- Detailed health status.
- Really easy to setup new environments quickly.

At the time of writing this, Beanstalk support apps developed in Java, PHP, .NET, Node.js, Python, Ruby out of the box and you can build your custom containers for other platforms all running on Amazon Linux.

In this section we are going to use Beanstalk to setup a _production environment_ (this means with an [external RDS](https://docs.aws.amazon.com/elasticbeanstalk/latest/dg/AWSHowTo.RDS.html)) replacing our current Elastic Load Balancer (ELB) and Auto Scaling Group (ASG) setup with a Beanstalk-handled setup.

It's important to remember not to make manual changes over the components generated by Beanstalk because it could prevent the correct clean up if we decide to remove an environment in the future. So to start fresh we need to remove some things before creating our new environment.

---
**Next** [clean up current setup](/workshop/beanstalk/01-clean-up.md)