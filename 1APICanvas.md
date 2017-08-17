---
title: API Canvas
slug: APICanvas
---

API Canvas is a tool to Visualize, Design and Test how to create value for customers. It directs user to understand the full API life-cycle and to think how to communicate and support the API consumers and give them access to the API. It also focuses on how to monetize the API and add value; like customer retention or cost savings. Main benefit of API Canvas compared to for example project scoping tools is that it **treats the API as a product**. This means that it tries to find the needs of several API Consumer segments, not just the one at hand. API Canvas was adapted from Alex Osterwalder's Business Model Canvas and optimized for the API Development.

APIOps&reg; Cycles design book starts withe visual chart templates for discovering key business and technical value, tasks and resources.
- **API Value Proposition Canvas** and
- **API Canvas**

## API Value Proposition Canvas (AVP)

The **Value Proposition Canvas** is composed to two parts, the **API Consumer View** and **API Provider View**.

With the **API Consumer View** you describe the tasks the consumer needs to achieve. Describe step by step tasks API consumer needs to achieve. Highlight your consumer **pains** which prevents or makes it difficult to get the task done. You can describe pains, risks and negative outcomes consumer want to avoid or dissatisfaction of existing solutions. Outline customer **gains** which describe how customers measure the success for job well done. In Gains section, describe concrete results, benefits, positive outcome and even aspirations which customer hopes to achieve. 

With the **API Provider View**, you list the **API products or services** your value proposition builds on. Describe in which way these products, services and features are **pain relievers**, how they eliminate, reduce or minimize pains consumers care about. Outline in which way they are **gain creators**. How they produce, increase or maximize outcomes and benefits that your consumer expects.

The value proposition makes explicit how the API's relieve pains and create gains. Use it to design, test and iterate your value proposition until you figure out what resonates to consumers. You achieve fit by creating a clear connection between what matters to customers and how your products, services and features ease pain and create gains.

## API Canvas

The **API Canvas** is composed of nine areas, which have almost the same titles as in Business Model Canvas. Canvas is composed to four parts, **Value Proposition**, **Infrastructure**, **Consumers** and **Finances**.

With the **Value Proposition** you describe the features  and services to meet the needs of the API Consumers. The value proposition provides value through various elements such as newness, performance, customization, "getting the job done", design, brand/status, price, cost reduction, risk reduction, accessibility and convenience and usability. 

With the **Infrastructure** related part you describe **Key Activities** in executing the value proposition, **Key Resources** that are necessary to create value for the API consumer and **Key Partners**, people or resources needed to realize API-features in practice.

With the **Consumers** part you describe which **API Consumer Segment** the Value Proposition tries to serve. Various set of consumers can be segmented based on the different needs and attributes to ensure appropriate usage and implementation of the API. In **Relationships** section identify the type of relationship you want to create with consumers, how to ensure API is usable from consumers perspective. In **Channels** section describe how the API is delivered to its targeted consumers, end-users and developers. Efficient channels will distribute the the value proposition in ways that are fast, efficient and cost effective.

With the **Finances** part you describe the financial aspects of the value proposition. In **Cost Structure** section describemost important monetary consequences related to operating the API, In **Revenue Streams** section describe ways the company makes income from each customer segment.

**API Canvas** is the **master document** for next phases, including architecture design. The simpler API Value Proposition Canvas helps to create value proposition and related information to the API Canvas.You should share the API Canvas with all relevant stakeholders. This includes external developers and other partners you need to work with.

Start with the API Value Proposition Canvas. ****It’s a great interviewing tool**.** Use it when finding and validating requirements with API Consumers.

## Step 1: API Value Proposition Canvas

The AVP Canvas discovers what APIs and other services are you need. It starts from the API consumer's tasks, expected benefits (gains) and problems. Then it guides you to design your API features as solutions to those expectations. Start from the right side of the AVP Canvas.

See instructions below, with corresponding letters. Don't be afraid of a few iterations with the templates. Use them also for interviewing required people, partners and teams to confirm ideas.

### Section A: Tasks

What does the potential API consuming application need to do? Fill in a workflow of tasks of situation where there is no API.

### Section B: Gains - benefits for using API

Look at the task list. Analyze what are the benefits of using an API to do the tasks. Think from the API Consuming application team's perspective. What do they not need to do them selves (assuming they even could do it)?

### Section C: Pains- problems using API

Why would the team use the API? What problems do they see? Problems could be related to identifying end-users, privacy, security, response times, agreements, costs or feature compatibility.

### Section D: Gain enabling features of the API

Match the expected gains with the gain enabling features of the API

### Section E: Pain releaving features of the API

Match the expected pains with the pain releaving features and resources (for example SDK, instructions…)

### Section F: APIs and Services offering the gain enabling and pain releaving features

List the APIs and other services required to fulfill the feature list. Remember no API is an island. Your API will need identity and authentication services, other APIs, backend integrations, storage, API management, developer portal etc.

## Step 2: API Canvas – Center & Right

If you looked already at the API Canvas –template, you noticed the areas are numbers. You should fill in all key information in the numbered order. Don’t be afraid to do a few iterations though. 

### Value proposition (1)

Summarize the "who, what, why" with one short sentence based on the fields D and E  and copy the feature fields D and E from the AVP Canvas to the **Value proposition (1) field** in API Canvas.

### API name

Copy the main API(s) you are now focused on creating/updating to the **API name field**

### API Consumer Segments (2)

You have now looked at the problem from at least one customer segments perspective.  Fill in **API Consumer segments (2):** what was the segment you thought about when doing the AVP Canvas? Who else could also use this API?. This is a good place to talk to the persons in charge of business developement and partner relationships. Don’t forget also marketing and vendor management people. If you find it helpful you can also list the end-user segments of the applications you need to support for the API.

### Developer relations (3)

How do developers find the API? How to ensure API is usable for them, how to understand what it can be used for? How to test drive it? How is their subscription approved? Do they have to sign an agreement? How do they give feedback, see roadmap, participate in discussion?

### Channels (4)

Think of this in different perspectives, a) the channels i.e. the technical applications with which the end-users are interacting with the API and b) the channels from which the developers find and can find, buy/request access to your API.

### Revenue streams (5)

What is the [API Business models](APIBusinessModels) of this API?

*   How does the API help you as an API Provider to create revenue (directly or in-directly)?
*   How can you reduce costs by offering an API?
*   How can the API Consumers create revenue or reduce costs by using the API?  

## Step 3: API Canvas – Left side

### Key activities (6)

Look at the features in the Value proposition field. What do you need to build or create to achieve the features? Don’t forget platforms, testing environments and other supporting elements. You might need to create also other non-functional elements like agreement templates, marketing materials etc.

### Key resources (7)

Take a look at the **field F in the AVP Canvas**. Are there any existing APIs or other services that you can use to create the new API –features? What existing platforms, backend integrations, document templates etc. will you use?

### Key partners (8)

Think about partners in this case as internal and external people outside your team. Look at the Key activities, Key resources and all the API Consumer related fields. Who do you need to co-operate with to make these API –features alive and usable for the intended API Consumers?

### Cost structure (9)

You can either **estimate the real costs** (which could be difficult at this stage before architecture has been designed or all the team assembled) **or set target based** on the profit margins defined by the revenue and cost-savingsin the Revenue streams –section. Remember the fixed monthly costs for architecture components and maintenance are probably the highest costs (unless your platform requires licenses). The variable costs will start to matter when your API has 1M+ users.

### Next stop:

*   Stakeholder approvals

*   [Collecting architecture requirements](CollectingArchitectureRequirements)
