+++
title = 'Good observability is simply more important than good testing'
date = 2020-02-23T23:23:45+01:00
draft = false
+++

In most cases, good observability is simply more important than good testing. As we all know

> There is no system that immune to failure, so we need to be ready to recover

Being able to recover from failure quickly, is pretty much how important observability is. In this case, I would slightly mention 3 phases of incident

![](https://cdn.alileza.me/public/1_JXnV4KDEuLQXn2syWE2Ujw.webp)


1. **Alert fired,** it can come from system or user, if it comes from the user, that’s a pretty good sign that we don’t have a good alert rules
2. **Observe the issue,** it is the phase where we try to figure out what is wrong with the system
3. **Fix the issue,** it is a phase where we execute a task to bring us to a healthy state

From the picture above, we can see that having **good observability will help reduce the Mean Time to Recover**, and it gives us the leverage to be able to make changes more rapidly because our ability to recover from problems is good enough. Which makes the cost of the error that we use less.

Of course, it all depends on the error budget that we budget for the system that we operate. And when we explore deeper about rapid change, it will lead us to learn how to fail gracefully.

![](https://cdn.alileza.me/public/1_RJQf0KQYIA-Py3ED-iuV3g.webp

And having good testing would prevent the frequency of failure over time (reducing Mean Time to Failure). Understanding that, **we know that observability and test in a system are essentials.**

# So what good observability looks like?

There would be no single answer to this, it all depends on the system that you’re working with. But in this case, I’d like to share common patterns of consumption of information that helps us to observe our system.

## Metrics

Metrics is a measure of quantitative assessment that commonly used for assessing, comparing, and tracking the performance of a system. It enables us to do a real-time exploration of the aggregate system behavior.

![Example of metrics, in 3 forms, counter, histogram, and gauge](https://cdn.alileza.me/public/1_d_p_NHo4lxU3atAvY6x2UQ.webp)


It gives you a way to see an overview of a system, such as _how is average memory usage across all datacenters, or how is error rate across multiple applications._

## Logging

Logging is a process of recording an event that happens to a system. It usually describes what the system is doing given time and some context. It enables us to get a deeper knowledge of what happens to a system.

![Example of logs from an application](https://cdn.alileza.me/public/1_otgDgDQRn4vsxBy__OxC7w.webp)

The screenshot above shows a list of events that omitted by an application, showing a context of what is happening on the application.



## Tracing

Tracing is a series of connected logs in a single transaction. It is giving quite similar value as adding transaction id on event logs. Usually it helpful for debugging a distributed system when there are multiple services.

![Example of tracing using Jaeger](https://cdn.alileza.me/public/1_B3j8Gihf7RSNBI2CVUk8KQ.webp)

Traces would be a single transaction, and span would represent every checkpoint that its transaction visits. For example, load balancer (`span1`) hitting an application (`span2`), then application reading a database (`span3`).

![](https://cdn.alileza.me/public/1_IPRFjr9QyeyL1PegX-ci4A.webp)

# What to do with this data?

## Visualization

Visualization is one valuable thing you can do with the data that you have, by grouping information based on what is important for your organization. That would be helpful for understanding the health of the system, making technical/business decisions, finding an anomaly, and other stuff.

## Alerting

In order to keep your system as you expect it to be. Setting up an automated alert on the specific condition of your system, based on metrics or logs would be very important to keep your system reliable.

The most common issue of alerting from my experience is, either we're having too many alerts that are not actionable, and people start ignoring it because it's becoming normal. Most of the time the reason

In order to avoid that, I like to classify alerts on its severity, such as:

- Informational, which you might be interested to be informed
- Warning, for condition of the system that is becoming unhealthy
- Critical, for serious issues that need immediate attention

For example:

- On informational, notify my team
- On warning, notify me only during a specific time period, for instance (08:00-20:00), since the importance of warning probably not worth to wake you up at night.
- And critical is simply something that would wake you up at 04:00 in the morning.

Why do we need a warning at all? it's simply giving you some space to do something before something really bad actually happens.

And over time on each alert, we should do a small evaluation

- Is it helpful?
- Is it triggered on the right threshold?

Those questions should help you modify your alerting rules towards more accurate alerting rules.

## Debugging

Debugging is the process of finding sources of problems with the system. In this process, we will be confronted with questions that lead us to the answers, what causes problems with the system? And metrics, logging & tracing will be very important to answer these questions.

Oftentimes we don't realize how important the ability to debug a system that we operate in is in production. Meanwhile, what happens in production is the only thing that defines the performance of our system.

Remember, we should create videos that can provide insight into debugging when only time that the debugging, therefore cannot be taught.

# Conclusions

Some of the things discussed above are not necessarily a silver bullet to achieve good observability. Ben Sigelman, provides an interesting perspective on the approach we can take to achieve good system observability in the [Three Pillars video, Zero Answers: We Need to Rethink Observability]

In conclusion, good observability would be gained over time by learning on each system failure. That should give us a precise direction of improvement towards a more resilient system.