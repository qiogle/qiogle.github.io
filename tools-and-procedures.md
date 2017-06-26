# Tools and Procedures

## Zendesk

We use two Zendesk products: 
+ Support 
+ Help Center

### Support

If you're new to Zendesk, you can reference their support site and [Getting Started Guide][4] while reading this documentation to understand Zendesk definitions and concepts. You might also find it helpful to dedicate 15 minutes before reading this to the getting started guide above.

##### Ticket Workflow

See diagram [here][8]. 

##### Macros

TODO

##### Triggers

TODO

##### Net Promoter Score

We currently use a homemade Google form to administer NPS surveys after he/she has an interaction with customer experience. A link to the form is included in the Zendesk email sent to the customer after his/her ticket has been marked 'solved'. 

The survey is [here][6]. 

`Note`: This is distinct from the general customer [survey][7], which also has a NPS question but is owned by Marketing and is sent to customers regardless of whether they've contacted customer experience. 

##### Batch Emails

I wrote a Python script that calls Zendesk's API to send batch tickets. I recently used it with the NJ pricing change, which affected 26 customers and for each, required the creation of a ticket with dynamic variables populated with personal infomation, such as refund amount. 

It's non-engineer code quality, but might be useful as reference for another non-engineer. 

Located [here][10]. 

### Help Center

TODO

Source of truth are the articles themselves 

`Reference`
+ 


## Britecore

`Reference`

+ Jetty processes: [Google Doc][5] *(How do I change start date? Add coverage?)*
+ Britecore official support: [Britecore Support Docs][1]

## Intercom 

Intercom is our chat tool. We subcribe to their 'Respond' and 'Engage' modules. The 'Engage' module provides basic chat functionality, which is supplemented by the saved responses, keyboard shortcuts, and API access from 'Respond'. 'Respond' additionally offers a team inbox to process incoming mail-based requests, which we don't use because we've configured Zendesk (rules, templated emails, etc) for that purpose. 

## Metabase


## Others

### Calendly

Calendly is a scheduling tool used to schedule meetings with external contacts. Within CX, we're using it to test out phone support for customers. 

Tracking calls here: [Google Sheet][9]

### Glossary

### Facebook

Checking and responding to customer comments on our posts. 

### Important Files

+ [Policy List][2]: Google sheet of policy and customer properties - one row per policy. Our temporary customer database. 
+ [Software Stack][3]: Google sheet of current software used in customer experience processes (e.g. Zendesk, Intercom, etc.) and leads to diligence. Links out to helpful internal documentation for each tool. 

## Procedures

> Logging common issues

Try to come up with a naive solution to each issue, to help the brainstorming process. Format up to you. 

My issue log [here][12].

> If a customer reports a technical error - *page wont load, can't click button*

Notify the technical point of contact. Currently through the #tech_general slack channel. 

> If a customer wants a policy change

1. *(Optional)* Email customer acknowledging receipt and 
2. Make changes in Britecore
3. Regenerate Jetty branded declaration page
4. Email customer to confirm that it's finished

> If we launch in a new state

Update FAQ 'Where is Jetty Available' Zendesk article [here][11]. 

> Choosing new software

I documented the pro/con analysis behind our current software stack. See [Software Stack][3] for links out to anaylsis by functional area. 

## Perspective

### Agents
+ Transparent: better to overcommunicate - let customers know when they should expect to hear back. Open a channel of communication. 
+ Forward-thinking: expect the user to make errors or not fully understand the problem. Provide contextual next steps. 
+ Conversational: 

### Customers
+ Tend to be relatively unfamiliar with insurance than other consumer products. As a result, more likely to postpone or give up. 
+ Looking for reassurance since its a financial product.  

### Other stuff

+ [Service recovery paradox][13]: When a very positive service recovery causes a level of customer satisfaction greater than that expected if no service failure had happened.

## Language

+ Switch to customer-facing vocabulary
	- "Checkout flow", "conversion", and other company jargon may seem foreign and cold to customers


## Adding or changing processes

+ Evaluate ROI
	- Clear objective
	- Define how objectives will be measured
	- [Article][14] about measuring ROI



[1]: https://briteedu.squarespace.com/
[2]: https://docs.google.com/spreadsheets/d/1HMdRz2aLdiYW2p3gyMOrNXM9f7nZJaN58dSP6pvdQBU/edit#gid=937495940
[3]: https://docs.google.com/spreadsheets/d/19JcM5BfVaNECSbxniXlsXY9G8H523OoHGMdGzO58s4E/edit#gid=0
[4]: https://support.zendesk.com/hc/en-us/articles/203921213
[5]: https://docs.google.com/document/d/1G-Z1EulI0vzjHhu8JsMsLqkY8R96yN52NsG1v3sse0A/edit#
[6]: https://docs.google.com/a/jetty.com/forms/d/1h8WAbeS5ypXtFcyYh9gfOdyV0GFfgcy8O60IyzYat58/edit
[7]: https://docs.google.com/a/jetty.com/forms/d/1h8WAbeS5ypXtFcyYh9gfOdyV0GFfgcy8O60IyzYat58/edit
[8]: https://docs.google.com/drawings/d/1suEPMv8edEyBBpYTp7XtKKp6pgskZgnzhvSXiU1Ue-E/edit
[9]: https://docs.google.com/spreadsheets/d/1TKG4d3eeNohZuwfHErKuox31MLAZkADr2Y7bQD6ttlA/edit#gid=34160161
[10]: https://www.dropbox.com/s/bq5jeyuljmkr7qr/batch.py?dl=0
[11]: https://jetty.zendesk.com/hc/en-us/articles/115003920667-Where-is-Jetty-available-
[12]: https://docs.google.com/document/d/1NwEyjH8mligR8HlbVyTZsOQyR4n61ux8L5WragSnot4/edit#
[13]: https://www.groovehq.com/support/how-to-deal-with-an-angry-customer
[14]: https://segment.com/blog/measuring-the-roi-of-support/#how-much-does-our-success-team-cost-