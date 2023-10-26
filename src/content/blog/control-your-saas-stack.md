---
title: "It’s important to control your SaaS stack"
description: "When you aren't in control of the technologies in your early-stage startup, you are forced into paying more for a solution that doesn't fit your needs."
pubDate: "Jun 17 2021"
heroImage: "/programming.png"
tags: ["startup", "saas", "development", "business"]
---

_This article was originally posted on Medium where it was published to multiple tech journals. I have since revised it and posted it here so that it can be read without a Medium subscription._

One of my responsibilities in our early-stage startup is to... well, do everything tech-oriented. I'm the only developer, so I'm responsible for building the product, managing the infrastructure, and everything in between. This means that all tools used by our company have to be compared and analyzed to find the best fit.

My co-founder is a seasoned entrepreneur that has done very well in life launching and growing scalable businesses. One of the biggest things that I have learned from him is how important control of your business is. If you are in a business where you have very little control of the operations, you are in a position where you can be shut down easily, have your website revenue drop off in a night, get your commission rate slashed 50%, etc.


## You NEED to control your startup stack.

This is a mistake that I definitely have made in the past. I see a lot of developers who are not as concerned with this, but they should be. You need to control your vertical integration of your technology.

There’s no question that Google Firebase, AWS, Apple, Digital Ocean, etc provide great toolsets for getting off the ground and running. However, you should look at their tendencies to lock you into their infrastructure. The Apple ecosystem is designed to lock you into buying more Apple products because they work seamlessly with each other. This is a great thing for consumers, but it can also be a dangerous thing because leaving the ecosystem becomes more complicated. The development tools created by the same companies are designed in much the same way.

I answered a question earlier today on Reddit about starting an MVP with serverless infrastructure. Serverless infrastructure is still, in my opinion, very hard to move away from, and it forces you into using other services in a lot of cases. When you sign a terms of service agreement with a company, you are most likely not the winning party. It’s a checkbox, not a negotiation. Most terms of service agreements state “we can do whatever we please and whenever we please.” Your serverless infrastructure can increase in price any time. In most cases, it starts out more expensive than traditional hosting, and it has the unlimited potential to price you out of your business model. You can see the same problem exists with no code/low code PaaS models.

## Our design decisions
We decided that the technology we use needs to be first and foremost replaceable. For example, we use PostgreSQL on Amazon RDS. We can spin up a PostgreSQL database on any server located anywhere and move our data without any true migration problems, and without risking code-breaking changes.

We also are using an n-tier service hierarchy to develop our business logic, which allows us the ability to change anything about our data infrastructure. We made sure to limit dependencies to a very small number unless they have a trivial function.

There are some libraries and services that simply do too much for you. When you rely on them, you are getting added development speed (sometimes, lol). You are sacrificing control over those functions in your application. You can run into weird bugs or weird design, and it turns out that it wasn’t your fault, it’s how the underlying code was written.


## It's a balancing act

No, you should NOT write everything from scratch. If you are a software developer, you will probably be wasting a lot of time if you’re trying to laser cut the walls of your server rack unit.

I am simply making the point that control is a major aspect of your startup. If your user experience is degraded because of a version update on iOS, you used too many abstractions. If your user experience is degraded because the serverless functions take too long to ping back to the user, you used too many abstractions. Unfortunately, these are abstractions that are hard to remove and control.

All abstractions on 1’s and 0’s are ultimately just pieces of compiled code that someone wrote. You can’t really control the device ecosystems and their wonkiness, but you can always write your own abstractions if you’re unhappy with how a library, SaaS, or service accomplishes a task.


## My Conclusion
My conclusion
Make design decisions that give you the most control over the product/service you provide without sacrificing too much of your developer effort and time. Reinvent the wheel **IF** you think it makes your car **better**.
