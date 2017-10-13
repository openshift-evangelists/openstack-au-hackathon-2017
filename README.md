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

Deploying your applications
---------------------------

You can deploy any stateless 12 factor or cloud native applications, as well as more traditional stateful applications where local persistent storage is required. As persistent storage is available and can be associated with applications, you can also deploy databases, both traditional SQL databases, or newer no SQL data stores or key/value databases.

For your own applications, OpenShift provides you with a number of different ways you can deploy your application. These are:

**Deploy an application from an existing container image:** In this scenario, you would create your container image outside of OpenShift. This can be constructed from a ``Dockerfile`` with tools such as ``docker build`` from the [Moby](https://github.com/moby) project, or indirectly by tools such as [Source-to-Image (S2I)](https://github.com/openshift/source-to-image) from application source code. The container image can be pushed to OpenShift's internal image registry, or hosted on an external image registry. OpenShift can then deploy the container image. This is utilising OpenShift as a Container as a Service (CaaS).

**Build a container image from a Dockerfile and deploy it:** In this scenario, instead of create your container image outside of OpenShift, you can have OpenShift build it for you from a ``Dockerfile``. OpenShift can build the container image from a Git repository hosting the ``Dockerfile`` and any other source files it requires, or you can use a binary build to push the source files from a local directory into OpenShift. Once the container image has been built within OpenShift, it can then be deployed. This is utilising OpenShift as a Container as a Service (CaaS), but where the container image is built within OpenShift for you.

**Build a container image from application source code and deploy it:** In this scenario, you provide OpenShift with your application source files via a Git repository or binary build, and it will construct a container image from it using a Source-to-Image (S2I) builder appropriate for the language or application stack you are using. In this case, you do not even need to know how to write a ``Dockerfile`` to create a container image, as the S2I build process will do everything for you. Once the container image has been built within OpenShift, it can then be deployed. This is utilising OpenShift as a Platform as Service (PaaS), where the platform does the hard work of converting your application source code into a suitable container image.

Whichever mechanism is used, OpenShift wraps the build and deployment mechanism with an automated workflow. When this is linked up to a hosted Git repository using a webhook as callback, you need only worry about working on the code for your application. Whenever you commit and push changes back to your hosted Git repository, OpenShift will automatically re-build the container image for your application and re-deploy your application.

For more complicated workflows, a Jenkins pipeline can be configured, allowing you to integrate testing and migration approval steps, giving you more control over the steps needed to get your application deployed into production.

If you need a database or data store, OpenShift provides a range of pre-defined container images for PostgreSQL, MySQL, MongoDB, Redis and more.

Any container images you bring for applications and services should be able to be run provided they follow best practices, don't require ``root`` access to run and can run as an assigned user ID. If a container image doesn't quite meet these requirements, you will be able to discuss issues around running the container image with the OpenShift mentors who will be present and we can guide you as to how the container image can be made to run, or on a case by case basis create special service accounts under which you will be able to run the container image with any extra privileges required.

Leaning about OpenShift
-----------------------

If you are new to OpenShift and want to learn the basics, we recommend you first download and read the following free eBooks.

* [OpenShift for Developers](https://www.openshift.com/promotions/for-developers.html) (https://www.openshift.com/promotions/for-developers.html)
* [DevOps with OpenShift](https://www.openshift.com/promotions/devops-with-openshift.html) (https://www.openshift.com/promotions/devops-with-openshift.html)

These will get you up to speed on how the platform works and how to use it, before delving down into the OpenShift documentation. Just be aware that the books were originally written for an older version of OpenShift, so you may find the web console of the version of OpenShift you will be using a little bit different.

Want to get your hands dirty and experiment with OpenShift prior to the hackathon, you have a number of different choices. The two we recommend are:

**[OpenShift Online](https://www.openshift.com/get-started/) (https://www.openshift.com/get-started/):** This is Red Hat's public hosted OpenShift instance. You can sign up to a free starter account which gives you a minimal set of resources suitable for experimentation and development. Just be aware that due to security restrictions in the platform, you are restricted to deploying existing container images, or deploying from application source code using S2I builders. There is also a paid pro account you can get for OpenShift Online if you need more resources.

**[Minishift](https://www.openshift.org/minishift/) (https://www.openshift.org/minishift/):** This allows you to run up an instance of OpenShift inside of a virtual machine on your own computer. Native virtualisation systems on Linux (KVM), MacOS X (xhyve), or Windows (HyperV) are supported, or you can use Virtual Box.

Need more details and you can access the official OpenShift documentation. You will be using OpenShift 3.6 for the hackathon.

* [OpenShift 3.6 Documentation](https://docs.openshift.com/container-platform/3.6/welcome/index.html) (https://docs.openshift.com/container-platform/3.6/welcome/index.html)

Setions of the documentation which will be most relevant to you as a developer are:

* [CLI Reference](https://docs.openshift.com/container-platform/3.6/cli_reference/index.html)
* [Developer Guide](https://docs.openshift.com/container-platform/3.6/dev_guide/index.html)
* [Creating Images](https://docs.openshift.com/container-platform/3.6/creating_images/index.html)
* [Using Images](https://docs.openshift.com/container-platform/3.6/using_images/index.html)

With discussion of particular programming languages supported by the S2I build mechanism found at:

* [Java](https://access.redhat.com/documentation/en-us/red_hat_jboss_middleware_for_openshift/3/html-single/red_hat_java_s2i_for_openshift/)
* [.Net Core](https://docs.openshift.com/container-platform/3.6/using_images/s2i_images/dot_net_core.html)
* [Node.js](https://docs.openshift.com/container-platform/3.6/using_images/s2i_images/nodejs.html)
* [Perl](https://docs.openshift.com/container-platform/3.6/using_images/s2i_images/perl.html)
* [PHP](https://docs.openshift.com/container-platform/3.6/using_images/s2i_images/php.html)
* [Python](https://docs.openshift.com/container-platform/3.6/using_images/s2i_images/python.html)
* [Ruby](https://docs.openshift.com/container-platform/3.6/using_images/s2i_images/ruby.html)
