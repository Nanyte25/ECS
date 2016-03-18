# ECS
study guide for AWS ECS and Docker


AWS ECS (EC2 Container Service)

Collection of templates, docs and notes related to ECS during my studies
Notes

    Docker Containers can run only one process at a time. If you are running on your docker container something that does multithreading, it won't work, unless you find a way to adapt everything into the same process (like adapting apache/nginx)

ECS

    Manages starting of taks over many instances
    ECS scheduler ensures a Desired Count of Docker Containers is always running
    Automated Integration with ELB

ECS competitors:

    kubernetes.io
    mesosphere.gihub.io/marathon/
    coreos.com/using-coreos/clustering
    docs.docker.com/swarm/multi-manager-setup/
    docs.docker.com/compose/overview

ECS Components:

    Cluster
    Container instance
    Task definition
    Scheduler
    Service
    Task (Execution of your task definition)
    Container
    ECS Agent: It's written in go (github.com/aws/amazon-ecs-agent). It also has its own API, which can be used to pull details about what it is tracking and can see. Example: curl http://localhost:51678/v1/metadata

Common Issues

    User not specifying a correct cluster name in /etc/ecs/ecs.config
    When ECS instance is terminated, the agent is not de-registered.
    Port conflicts
    Container exiting before expected

Advanced topics

    Logging (there's a logdriver that allows you to push logs to plenty of places, such as cloudwatch)
    Service Discovery (It tries to identify container automatically)
    Persistence of Data

Goals

    Understand Docker
    Learn how it integrates with AWS
    Understand how ECS works under the hood

Features

    Only runs under VPC
    Integrates with ELB for your ECS clusters
    All launchings are done through CFN stacks with pre-defined CFN templates. Just like ElasticBeanstalk

Limitations

    Doesn't run under EC2-Classic, which may be a problem for old aws customers
    The console doesn't show any error details whenever a container can't be created

Tips and A-HA moments
Tools
Documentation
