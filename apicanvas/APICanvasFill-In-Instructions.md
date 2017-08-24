---
layout: page
title: API Canvas instructions
permalink: /apicanvas/apicanvasinstructions/
parenturl: /apicanvas/
---

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

What is the [API Business models](../APIBusinessModels.md) of this API?

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
