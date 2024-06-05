---
layout: post
title: Service Levels
description: "Explaining Service Levels Objectives, Agreements and Indicators, what they are and how they are useful."
image: "/images/posts/2020/04-09.jpg"
date: 2020-04-09
tags: ["2020"]
---

---

<center>
<h3> Objectives, Agreements and Indicators. </h3>
</center>

---

<br/>

In order to know if a system is working, we have to know what working looks like and how to measure it. This is not only a technical concern, but also a product and/or business need. We make things for customers and clients, and as such, part of knowing if something is working includes knowing how these users are impacted and if they are receiving the "right" level of service.

How can we define what working looks like and measure a system in a way that satisfies all these concerns? This is where Service Level Objectives (SLO), Service Level Agreements (SLA) and Service Level Indicators (SLI) come into play. These measures are explored <a href="https://landing.google.com/sre/sre-book/chapters/service-level-objectives/" rel="noreferrer" target="_blank">in Chapter 4 of the Google SRE (Site Reliability Engineering) book.</a>

Determining these measures can be more difficult than first anticipated and they will change over time. Nonetheless, the are important to track.

> _"These tools aren’t just useful abstractions. Without them, you cannot know if your system is reliable, available or even useful. If they don’t tie explicitly back to your business objectives, then you don’t have data on whether the choices you make are helping or hurting your business." - Google SRE Book_

In this post, we will go through how these measurements are linked, what they are and how they can be defined and measured. Throughout this post I refer to "service". It is most likely your SLOs and SLAs will be set around domain boundaries, but it depends on how your system is architected and organised. For the purpose of this high level exploration, service/ system can refer to a technical component, domain or product, depending on your system.

For SLOs and SLAs you will most likely be discussing them with product / the wider business at a feature, product, project or domain level.

### Quick definitions

- **SLO (Service Level Objectives):** Defined and measurable expectations of the service. These are measured by SLIs and sometimes "enforced" by SLAs.
- **SLA (Service Level Agreements):** Contracts agreed with consumers, users and other parties determining the consequences of not meeting certain levels of service. These may link to higher level objectives and are measured by SLIs.
- **SLI (Service Level Indicators):** A quantifiable measure of some level of service provided. Help to measure if SLAs and SLOs are met.

### How these are linked

SLOs are agreed in terms of business and product requirements. They are how the a service is expected behave as a good average, and not be a measurement of perfection or stretch goals.

These help when agreeing SLAs. By knowing what the expected behaviour of a service or system is, you can then set reasonable and achievable SLAs with your users, clients, consumers and third parties.

Whether SLAs and SLOs are met and achieved are measured using SLIs.

Another way to look at this is SLOs set the expectations, SLAs determine consequences to some of those expectations not being met and SLIs are how we measure if the expectations are being met.

<br/>

---

# Diving into each

Now we have established the basics of what each are and how they are connected; lets dive into each of them in a bit more detail.

<br/>

## Service Level Objective (SLO)

The top tier of these measurements and contracts is the Service Level Objective (SLO). An SLO sets the expectation for how available a service is and how it should perform. By no means are SLOs purely technical measurements. They require the input of a business and should be linked to both product and overall business expectation.

SLOs are measurable, numerical values of systems availability/reliability. They go hand in hand with <a href="https://landing.google.com/sre/sre-book/chapters/embracing-risk/#xref_risk-management_unreliability-budgets" rel="noreferrer" target="_blank">error budgets, which are targets for the maximum amount of time a service is unavailable/unreliable in a quarter</a>.

When it comes to discussing work, a team and product can refer back to SLOs to help determine it's value and purpose. This is assuming it is a well defined "good" measure which doesn't increase work for a team because it's too stretched.

### Setting SLOs

There are a number of considerations for setting SLOs including what is technically and financially achievable and what your end consumer would expect/need. Setting objectives is not purely a technical exercise and will need the inclusion and buy in of product and the business.

It is advised that objectives are limited. This helps determine what behaviour is the priority for the business/consumer, as often there will be some pay off depending on whether a focus is scalability, availability, resilience, performance or otherwise.

Most importantly, the objectives need to demonstrate what the reasonable expectations of a service is. They need to be achievable and focused.

### Determining SLOs

There are a number of factors when defining and determining SLOs. As mentioned SLOs have to tie into business and product need, as well as the technical considerations such as feasibility of measurement and cost.

<strong>Simple and discrete</strong>

Ideally, there should be a limited number of these measures and they should be measures that aren't over complicated. The more complex the measurement and the more moving pieces, the more likely it is that something will be missed or misinterpreted. Likewise, too many measures hide what it is important and can be difficult to keep track of.

<strong>Not a measure of perfection</strong>

As mentioned previously, SLOs are measures of what is expected of the service. Common mistakes with SLOs are to set them too high or too low.

SLOs are meant to be achievable, not set as stretch goals or what the system can achieve in a perfect world. If you are rarely or never achieving an SLO, it defeats the purpose of having it as a measure of if the service is meeting it's expected behaviours to be "available".

As with everything in life, perfection is always impossible. There will be downtime due to errors, deployments and other events which call lead to a loss in availability. Likewise, the expectation that things will never fail can cripple innovation and experimentation, which can be detrimental to progression. It's worth accounting for these as part of determining your SLOs.

As mentioned, it is also possible to set objectives which are too low. When a service is demonstrating behaviours which are considered problematic or broken to users or a business need, SLOs shouldn't pass. Negative impact to a customer or consumer should not be considered as acceptable for an expected level of availability.

<strong>Costs versus reliability</strong>

One of the reasons why perfection is unattainable is that is it is expensive. Operation costs increase the more reliable and available you want your service to be. As such, it is suggested in the Google SRE book that the lowest level of reliability that can be achieved while still making dependants, clients etc happy with the level of service, should be stated as an SLO.

There may also be costs outside of operational costs that would need to be considered when trying to meet certain objectives. If to achieve an SLO the service needs rewriting, a system re-architecting or an unachievable budget requirement needs satisfying (i.e. new tooling etc) - it's not a suitable SLO.

<strong>Flexibilities of measures</strong>

Over time a service's purpose can change, as can the expectations of that service. For example, changes in code or tooling could change the level of average performance. Likewise, there can be additional or reduced features from product. Over time, it is best to review and adjust SLOs and related SLAs and SLIs.

<strong>Accounting for error budgets</strong>

Error budgets are explored <a href="https://landing.google.com/sre/sre-book/chapters/embracing-risk/#xref_risk-management_unreliability-budgets" rel="noreferrer" target="_blank">in Chapter 3 of the Google SRE (Site Reliability Engineering) book.</a> They are closely tied to SLOs. It is a metric covering how much time in a quarter a service can be "unreliable".

This budget accounts for down time due to deployments, production issues and unexpected events. It also allows time for teams to experiment and innovate in a controlled manner where failure (in a regulated amount) is not an issue. As previously mentioned, an SLO of 100% availability and reliability isn't possible, but we can plan and aim for achievable goals and measures.

<br/>

## Service Level Agreement (SLA)

These are contracts (which can be explicit or implicit) for what can be expected from a service in terms of it's reliability, performance and behaviour. These are tied into SLOs, as the objectives outline the expected service levels agreed by the business, whereas SLAs are the contractual agreements that these service levels will be met.

SLAs normally have some form of consequence when they are not met. This can be financial remediation, but can come in other forms as well. These contracts can also be with multiple forms of third parties. It can be with external clients, internal teams - anyone using your service/product.

They are a good way to have clear and strong relationship with your customers, consumers and clients using your service. This is because they increase the transparency around expected interactions and levels of service agreed by both parties.

### Setting SLAs

Although SLAs can be linked to SLOs they are often not matched to each other. The agreements tend to be set at a more relaxed level than the objectives.

In order to set SLAs you will first need to measure baselines of how you service normally behaves and what its capable of. This may be done through monitoring your system or testing it.

The next step is to talk to the direct consumers/customers of your service. Find out what sort of service they expect/need, why and if it's achievable. Find out which behaviours of your service are of highest priority to them - availability, throughput, response time etc. All of this will help limit and define your final SLAs

The above should provide enough information to create drafts of your SLAs. With the information you should now know what is achievable by your service, what behaviours are of highest importance to your consumers, if these are compatible and what service levels can be agreed to.

Once these draft SLAs are written they need to be proposed to the business to be refined and approved. If the agreements align well with the objectives, it will be easier to discuss them in terms of the businesses goals. The business will be impacted by any consequences of not meeting SLAs as well, so have to be involved in the process.

For internal SLAs, the expectation of how different services/domains interact can effect a users journey end to end. It can be beneficial to consider overall contracts at a high level in certain circumstances to get an idea of a "worst case" for all SLAs. I.e. what the slowest agreed journey is end-to-end for your consumer/customer given all components and domains involved are meeting their maximum SLA for latency.

All of this process involves the cooperation of multiple departments in your company. For example:

- Tech will be impacted by what is currently achievable with what they have built and if SLIs are in place to measure the agreed contract is being met.
- Product could be impacted by trying to meet consumer/customer/clients needs and discussions around that.
- Finances and the business as a whole could be impacted by the consequences of a SLA not being met.

### Determining SLAs

Throughout this process there are a few things that can make the SLAs easier to measure and track.

<strong>Simple and discrete</strong>

In order to have clear communication and expectations with your consumers, the SLAs themselves need to be clear. They need to be easy to measure and easy to understand. As such, aim to have simple SLAs without too many interconnected, moving parts.

<strong>Temporal Concerns</strong>

SLAs don't have to be set at a 24/7 rate. It might be that your consumers want to set expectations for distinct periods of times. This could be times of day or seasonal, which allow for the services to have further expected downtimes or slowing in service.

<strong>Consider dependencies</strong>

It may be that outages from external dependencies can mean that SLAs aren't met. As there are consequences to SLAs, financial or otherwise, you don't want to be impacted by problems with dependencies. This can be covered in the agreements with your consumers, dependencies or both.

<br/>

## Service-Level Indicators (SLI)

Lastly, we come to SLIs. These are the measures of level of service, which help us determine if we are meeting the SLOs and SLAs. SLIs can include measurements of availability or downtime as well as metrics about how your service is performing.

If you have some baselines of metrics currently in place in your system, some of these SLIs may already be covered. Common measurements often include errors, duration of calls and rate of throughput. Some of these measures are covered in my previous posts <a href="{{site.baseurl}}/blog/practicaldashboardspart3-post" rel="noreferrer" target="_blank">Metric Baselines For APIs</a> and <a href="{{site.baseurl}}/blog/practicaldashboardspart2-post" rel="noreferrer" target="_blank">Metrics Baselines for Services
</a>.

In order to measure SLAs and SLOs, SLIs need to be put into place. Objectives and agreements are often tracked by percentage over time, and as such SLIs are often aggregated and measured in the same way to see if expectations are met.

### Setting SLIs

In some way or other you will need to set up monitoring to track whether your SLAs and SLOs are being met. This could be with dashboards and with alerts for when thresholds are under threat. If an SLA or SLO is in danger of not being met, it is likely there will be some work needed and communication sent out to remediate the issues.

If there are any measurements missing for the purpose of measuring if SLAs and SLOs are being met they will need to be implemented.

### Determining SLIs

The indicators required to measure whether the objectives and agreements are being met will need to be implemented. With these being closely linked to SLAs and SLOs, a lot of the principles when defining them overlap.

<strong>Simple and discrete</strong>

Not over-complicating measurements means that it will be less likely to have erroneous or missed measurements.

<strong>Impact of measurement</strong>

It's most likely some tooling will be required in order to implement SLIs. When picking and implementing tooling you'll need to consider the cost of hosting and running and if the tool itself will have any impact on your measurements (such as latency of calls).

<br/>

---

# Transparency

One of the most important aspects of defining and measuring service levels is transparency and communication.

Firstly, they help with communication. SLOs and SLAs are great for clarifying expectation and can be referred to whenever changes are being asked for. It might be that you are fighting to do work that may enable these service levels being improved or met. Maybe they have been missed a few times and work needs to be done to fix up a product. Another possibility is that you may refer to the effect on expected service level when new functionality is being proposed.

In terms of production support, if service level is defined and the impacts of detriment to service level is well documented, it helps determine the urgency of work and the communication that needs to be distributed. Objectives make it clear what a service needs to achieve and to what level. They also demonstrate potential impact to consumer. Agreements demonstrate the consequences of these levels not being met. Indicators help when trying to determine if these levels are being met, and if not, where service levels are being impacted.

Further to this, using SLIs you can demonstrate that you are meeting business or consumer requirements. Using dashboards or other forms of communication you can make it visible to the business how a system is performing against the service level objectives which they've helped set.

<br/>

---

# Conclusions

Objectives, agreements and indicators are important for communicating and measuring service levels. They are intrinsically intertwined. For a simplified example:

- _Pizza SLO:_ 99% of pizzas will be delivered within 4 hours.
- _Pizza SLA:_ If a pizza isn't delivered within 4 hours, you will be refunded half the cost.
- _Pizza SLI:_ Timer from order to delivery.

For measuring if a system or service meets it's required business need, having SLOs, SLAs and SLIs are essential. They also help direct the work needed to keep a system maintained to a level where businesses and consumers are satisfied with its performance. They help direct conversations about priority internally and externally around service and also give a sense of purpose. When it's made clear what the business value is and what impacts there are to consumers, it is easier to define and direct conversations around the value of your service.

<br/>

---

# References

- <a href="https://landing.google.com/sre/sre-book/chapters/service-level-objectives/" target="_blank">Google SRE - Chapter 4 Service Level Objectives</a>

- <a href="https://cloud.google.com/blog/products/gcp/sre-fundamentals-slis-slas-and-slos" target="_blank">SRE fundamentals: SLIs, SLAs and SLOs</a>

- <a href="https://cloud.google.com/blog/products/gcp/availability-part-deux-CRE-life-lessons" target="_blank">SLOs, SLIs, SLAs, oh my - CRE life lessons</a>

- <a href="https://docs.honeycomb.io/working-with-your-data/slos/" target="_blank">Define and manage Service Level Objectives (SLOs)</a>

- <a href="https://www.circonus.com/2018/07/a-guide-to-service-level-objectives/" target="_blank">A Guide To Service Level Objectives, Part 1: SLOs & You</a>

- <a href="https://blog.newrelic.com/engineering/best-practices-for-setting-slos-and-slis-for-modern-complex-systems/" target="_blank">Best Practices for Setting SLOs and SLIs For Modern, Complex Systems</a>

---

<div style="text-align:center" markdown="1">
<img src="{{site.baseurl}}/images/logo.png" alt="Logo">
</div>
