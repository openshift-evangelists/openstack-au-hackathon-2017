OpenStack AU Hackathon 2017 - Resources for OpenShift
=====================================================

This repository contains resources about [OpenShift](https://www.openshift.org/), for attendees of the OpenStack Hackathon being held in conjunction with [OpenStack Summit 2017 in Sydney Australia](https://www.openstack.org/summit/sydney-2017/).

Information on the hackathon itself can be found at:

* http://hackathon.openstack.org.au/

If you aren't intending to come as a competitor, but would like to participate as a mentor, you can find details about being a mentor for the event at:

* http://hackathon.openstack.org.au/mentors/

The hackathon is a 3 day community driven event where participants are invited to hack up the stack and create the best cloud application using the worlds leading open cloud platforms.

Unlike many hackathons, the event is not about coming up with new ideas. Instead, the purpose of the hackathon is to have teams bring existing applications and get them running on one of the cloud platforms which will be made available at the event. Teams will be judged based on not just their application, but also how effective a use they make of features of the cloud platform as part of both the development and deployment of their applications.

The cloud platforms which will be available at the event for teams to use are OpenShift, Agave and Cloudify. If you are going to bring a team to the event to compete, you will find information here to help you decide as to whether you want to choose OpenShift, as well as links off to resources on how to then use OpenShift. If you want to get hands on with OpenShift before the event to try it out, you will find details here on hosted OpenShift instances which are available which you can use, and how you can run OpenShift on your own computer to try it.

Why choose OpenShift
--------------------

OpenShift is a next generation platform for deploying web applications, databases or other network based services in a cloud environment. Applications are deployed to a containerised environment. You provide OpenShift with your application source code, or provide the location of an existing container image, and the platform will worry about the details of how to deploy it, keep it running, and make it available to users. Use OpenShift, and rather than wasting time on the operations aspects of deploying an application, you can focus on the development of your application.

The OpenShift platform is based around standards from the [Open Container Initiative](https://www.opencontainers.org/) for running applications in containers. It uses [Kubernetes](https://kubernetes.io/) to manage the cluster, and orchestration and scheduling of the containers which run your applications. Kubernetes being a platform targeting IT operations, OpenShift adds its own magic source on top, building in workflows and automation to make the platform much easier to use by developers.

A quick tour of OpenShift
-------------------------

If you want a quick tour of OpenShift and what it is like to use it, the easiest way is to jump on over to the OpenShift Interactive Learning Portal.

* https://learn.openshift.com/

Through this site you can work through a range of interactive tutorials on using different features of OpenShift.

For each tutorial, an instance of OpenShift will be started up for you. You will interact with OpenShift using the web console, as well as a command line client through a terminal session embedded right in your browser. This allows you to try out OpenShift without needing to install any software on your own computer, nor do you need to sign up for any OpenShift service. Once you have done the tutorials, you can use the OpenShift instance to run your own experiments. The OpenShift instance created for you will be automatically shutdown after one hour or when you leave the site.
