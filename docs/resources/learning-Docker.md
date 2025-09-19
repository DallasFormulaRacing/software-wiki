# Introduction

Unlike [Python](https://www.python.org/) and [Git](https://git-scm.com/), [Docker](https://www.docker.com/) isn't necessarily required that you know how to "program" in it (AKA, write `.dockerfile`s), more so that you know what it is, and how to use it to its fullest potential.

A quick and dirty explanation of what docker is in a practical sense is a method of **virtualizing** and **containerizing** our various software products. 

---

**What is virtualization?**

Virtualization is a method of taking one computer and splitting it into many smaller computers. Of course these smaller computers all have to share the same resources that the original computer had, so it may be best to think about it as if the original computer was a pie, and each of the virtual computers is a slice of that pie. Essentially we take one much more powerful computer, and split it into little chunks that allow us to run one of our software products on an individual slice of that virtual pie. Overall though, I suggest you read about how virtualization works and why its beneficial in [this article from IBM](https://www.ibm.com/topics/virtualization).

**What is containerization?**

In essence containerization is the ability for an application to be condensed into a single "executable." What this means in regard to [Docker](https://www.docker.com/) is that when you are creating an application for a [Docker](https://www.docker.com/) environment, you are effectively taking your entire codebase and condensing it into a single "file," of which in this case is called a [Docker](https://www.docker.com/) Container. For a more in depth exploration of what containerization is, please check out [this article from IBM](https://www.ibm.com/topics/containerization).

---

## Where do I begin?

Many people come to DFR, and the workplace, having never used or even heard about [Docker](https://www.docker.com/), so don't think you're alone. [Docker](https://www.docker.com/) is a very unique concept for most, and the goal of the below resources is to help guide you into learning at the very least how to utilize [Docker](https://www.docker.com/) in your workflow. Then come time to deploy any applications that you might make while you are at DFR, you will know how to build your application for the [Docker](https://www.docker.com/) environment. 

### Text resources

!!! Info "Notice"
    Out of both of these resources, the [Docker 101 tutorial](https://www.docker.com/101-tutorial/) is easily the most important / useful. When learning [Docker](https://www.docker.com/) for the first time it is highly recommended that you cross reference the tutorial at least once.

|Name|Description|URL|
|---|---|---|
|Docker 101 Tutorial|A "self paced, hands-on tutorial" straight from the horse's mouth. This "short" tutorial will educate you on how to understand the concepts of the [Docker](https://www.docker.com/) environment, while also giving you practical knowledge on how to use the [Docker](https://www.docker.com/) environment locally.|[docker.com/101-tutorial](https://www.docker.com/101-tutorial/)|
|awesome-docker|Like `awesome-python`, this is a repo designed to educate you through all the in's and out's of [Docker](https://www.docker.com/) on a beginner to advanced level, and can be utilized by anyone regardless of their experience with [Docker](https://www.docker.com/).|[github.com/veggiemonk/awesome-docker](https://github.com/veggiemonk/awesome-docker)|


### Video resources

#### Docker in 100 Seconds - Fireship
<iframe width="560" height="315" src="https://www.youtube.com/embed/Gjnup-PuquQ" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>

---

#### 100+ Docker Concepts you Need to Know - Fireship
<iframe width="560" height="315" src="https://www.youtube.com/embed/rIrNIzy6U_g" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>