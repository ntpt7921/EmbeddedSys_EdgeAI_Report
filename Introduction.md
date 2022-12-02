# The edge

The history of computer networks has been a gigantic tug of war. In the first systems—individual computers the size of a room—computation was inherently centralized.

Eventually, however, computers were connected to terminals. Over time, terminals became more and more sophisticated, taking over more and more functions that were previously the job of the central computer. The processing had been pulled to the opposite extreme—from the center of the network to the _edge_.

The growth of the Internet, along with web applications and services, made it possible to do some really cool stuff. Over the past decade, most of our computing has become centralized again—this time in the “cloud”. When the Internet goes down our modern computers aren’t much use!

But the computers we use for work and play are not our only connected devices. Much of these devices are embedded systems. There are some major benefits to being at the edge of the network. For one, it’s where all the data comes from!

# Artificial intelligence (A.I.)

Artificial intelligence is a very big idea, and it’s terribly hard to define. But to define AI, we have to define intelligence—which turns out to be particularly tough. What does it mean to be intelligent? Since this isn’t about philosophy, let' s accept a quick-and-dirty definition of intelligence

> Intelligence means knowing the right thing to do at the right time.

- Taking a photo when an animal is in the frame
- Applying the brakes when a driver is about to crash
- Informing an operator when a machine sounds broken
- Answering a question with relevant information
- Creating an accompaniment to a musical performance
- Turning on a faucet when someone wants to wash their hands

# Machine learning

The best way to introduce machine learning is through an example. Imagine you’re building a fitness tracker—it’s a little wrist band that an athlete can wear. It contains an accelerometer, which tells you how much acceleration is happening on each axis (x, y, and z) at a given moment in time.

To help your athletes, you want to keep an automatic log of the activities that they are doing. For example, an athlete might spend an hour running on Monday and then an hour swimming on Tuesday.

Since our movements while swimming are quite different from our movements while running, you theorize that you might be able to tell these activities apart based on the output of the accelerometer in your wrist band. To collect some data, you give prototype wrist bands to a dozen athletes and have them perform specific activities—either swimming, running, or doing nothing—while the wrist bands log data.

Now that you have a dataset, you want to try to determine some rules that will help you understand whether a particular athlete is swimming, running, or just chilling out. One way to do this is by hand: analyzing and inspecting the data to see if anything stands out to you. Analyzing data by hand can be tricky, and it generally requires expert knowledge about the domain (such as human movements during sport). An alternative to manual analysis might be to use machine learning.

With an ML approach, you feed all of your athletes’ data into a special training algorithm. When provided with both the accelerometer data and information about which activity the athlete is currently performing, the algorithm does its best to learn a mapping between the two. This mapping is called a _model_.

Hopefully, if the training was successful, your new machine learning model can take a new input—a sample of accelerometer data from a particular window in time—and tell you which activity the athlete was performing. During training, the model has learned the characteristics that distinguish running from swimming.

There are lots of different machine learning algorithms, each with their own strengths and drawbacks—and ML isn’t always the best tool for the job. Later in this chapter we’ll discuss the scenarios where machine learning is the most helpful. But a nice rule of thumb is that machine learning really shines when our data is really complex.


# Edge AI

There are many places that ML would like to go but, has a difficult time reaching. This is because many state-of-the-art machine learning models require significant computing resources and power consumption (thus its prevalance as a cloud service).

Embedded ML is the art and science of running machine learning models on embedded systems. TinyML is the concept of doing this on the most constrained embedded hardware available—think microcontrollers, digital signals processors, and field programmable gate arrays (FPGAs).

When we talk about embedded ML, we’re usually referring to machine learning _inference_ - the process of taking an input and coming up with a prediction (like guessing a physical activity based on accelerometer data). The training part usually still takes place on a conventional computer.

Embedded systems often have limited memory. This raises a challenge for running many types of machine learning models, which often have high requirements for both read-only memory (to store the model) and RAM (to handle the intermediate results generated during inference).

They are often also limited in terms of clock cycles. Since many types of machine learning models are quite processor intensive, this can also raise problems.

Luckily, over the past few years there have been many advances in optimization that have made it possible to run quite large and sophisticated machine learning models on some very small, low power embedded systems.

# Benefits of edge AI - BLERP

## Bandwidth

IoT devices often capture more data than they have bandwidth to transmit. This means the vast majority of sensor data they capture is not even used—it’s just thrown away! 

If we had a lot of bandwidth, we could send the sensor data up to the cloud and do some kind of analysis to understand whether a failure is imminent. In many cases, though, there isn’t enough bandwidth (or energy budget) available to send a constant stream of data to the cloud. Bandwidth limitations are very common. Of course, it’s also quite common for devices to have no network connection at all!

-> Leading to edge processing

It’s not just about available connectivity—it’s also about power. Networked communication is often the most energy-intensive task an embedded system can perform, meaning that battery life is often the limiting function. Some machine learning models can be quite compute intensive, but they tend to still use less energy than transmitting a signal.
    
## Latency

Transmitting data takes time. Even if you have a lot of available bandwidth it can take tens or hundreds of milliseconds for a round-trip. Edge AI solves this problem by removing the round-trip time altogether. A great example of this is a self-driving car.
    
## Economics

Connectivity costs a lot of money. By processing data on-device, edge AI systems reduce or avoid the costs of transmitting data over a network and processing it in the cloud.
    
## Reliability

Simplicity and reliability go hand-in-hand. Adding connectivity to a product makes it vastly more complex. Systems controlled by on-device AI are inherently more reliable than those which depend on a connection to the cloud.

For some applications, this might be tolerable. But in other cases, safety is paramount. Imagine an AI-based system that monitors an industrial machine to make sure that it is being operated within safe parameters. If it stops working when the Internet goes down, it could endanger human lives. It would be much safer if the AI is based entirely on-device, so it still operates in the event of a connectivity problem.
    
## Privacy

Over the past few years our society has become used to the idea that there’s a tradeoff between convenience and privacy. If we want our technology products to be smarter and more helpful, we have to give up our data.

This may be fine for some applications. But for other applications, privacy is a huge concern.

# Key differences between Edge AI vs regular AI

## Training on the edge is rare

A lot of AI applications are powered by machine learning. Most of the time, machine learning involves _training_ a model to make predictions based on a set of labelled data. Once the model has been trained, it can be used for _inference_: making new predictions on data it has not seen before.

When we talk about edge AI and machine learning, we are usually talking about _inference_. Training models requires a lot of computation and memory, and it often requires a labelled dataset. Both of these things are hard to come by on the edge, where devices are resource-constrained and data is raw and unfiltered.

For this reason, the models used in edge AI are often trained before they are deployed to devices, using relatively powerful compute and datasets that have been cleaned and labelled—often by hand. It’s technically possible to train machine learning models on the edge devices themselves, but it’s quite rare—mostly due to the lack of labelled data.

## The focus of edge AI is on sensor data

The exciting thing about edge devices is that they live close to where the data is made. Often, edge devices are equipped with sensors that give them an immediate connection to their environments.

By its nature, sensor data is very messy. For this reason, digital signal processing is a critical part of most edge AI deployments.

A lot of traditional machine learning and data science tools are focused on tabular data—things like company financials, or consumer product reviews. In contrast, edge AI tools are built to handle constant streams of sensor data. It’s a whole different world.

## ML models can get very small

Edge devices are often designed to limit cost and power consumption. The constraints of the target devices mean that, when machine learning is used to implement edge AI, the machine learning models must be quite small. On a mid-range microcontroller there may only be a hundred kilobytes or so available to store a model’s weights, and some devices have far smaller amounts of ROM. Since larger models take more time to execute, the slow clock speeds of devices can also push developers towards deploying smaller models.

Making models smaller involves some trade-offs. To begin with, larger models have more capacity to learn. When you make a model smaller it starts to lose some of its ability to represent its training dataset, and may not be as accurate.

That said, not all applications require big, complex models. The ones that do tend to be around things like image processing, since interpreting visual information involves a lot of nuance. Often, for simpler data, a few kilobytes (or less) of model is all you need.

## Compute is diverse and heterogeneous

The majority of server-side AI applications run on plain old x86 processors, with some graphics processing units (GPUs) thrown in to help with any deep learning inference. There’s a small amount of diversity thanks to Arm’s recent server CPUs, and exotic deep learning accelerators such as Google’s TPUs (tensor processing units), but most workloads run on fairly ordinary hardware.

In contrast, the embedded world includes a dizzying array of device types:

- Microcontrollers, including tiny 8-bit chips and fancy 32-bit processors
- System on Chip devices running embedded Linux
- General purpose accelerators based on GPU technology
- Field programmable gate arrays (FPGAs)
- Fixed architecture accelerators that run a single model architecture blazing fast

Each category includes countless devices from many different manufacturers, each with a unique set of build tools, programming environments, and interface options. It can be quite overwhelming.

The diversity of hardware means there’s probably an ideal system for any particular use case. The hard part is choosing one! We’ll cover this challenge in a later chapter.

## “Good enough” is often the goal

With traditional AI, the goal is often to get the best possible performance—no matter the cost. The benefits of edge AI come with some serious constraints. Edge devices have less capable compute, and there are often tricky choices involved with trading off between on-device performance and accuracy.