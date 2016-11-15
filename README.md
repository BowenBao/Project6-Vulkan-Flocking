Vulkan Flocking: compute and shading in one pipeline!
======================

**University of Pennsylvania, CIS 565: GPU Programming and Architecture, Project 6**

* Bowen Bao
  Windows 10, i7-6700K @ 4.00GHz 32GB, GTX 1080 8192MB (Personal Computer)

## Boids

![](/img/boids.gif)

## Questions
* Why do you think Vulkan expects explicit descriptors for things like generating pipelines and commands? HINT: this may relate to something in the comments about some components using pre-allocated GPU memory.

In Vulkan, the base binding unit is a descriptor. In generating pipelines and commands, it needs to know how data are stored in GPU memory, and thus it needs explicit descriptors to show the bounded data.

* Describe a situation besides flip-flop buffers in which you may need multiple descriptor sets to fit one descriptor layout.

Like in rasterization, we can have multiple descriptor sets each for color map, normal map and depth.

* What are some problems to keep in mind when using multiple Vulkan queues?
	take into consideration that different queues may be backed by different hardware
	take into consideration that the same buffer may be used across multiple queues

One of the problem to consider is how independent each queue is. If there are a lot of synchronization, race conditions between queues, it might not be as effective as expected.

* What is one advantage of using compute commands that can share data with a rendering pipeline?

Save I/O time for transfering data to render pipeline.

### Credits

* [Vulkan examples and demos](https://github.com/SaschaWillems/Vulkan) by [@SaschaWillems](https://github.com/SaschaWillems)
