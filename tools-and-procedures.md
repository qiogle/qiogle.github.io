# Tools and Procedures

## Zendesk

We use two Zendesk products: 
+ Support 
+ Help Center

### Support

If you're new to Zendesk, you can reference their support site and [Getting Started Guide][4] while reading this documentation to understand Zendesk definitions and concepts.

##### Ticket Workflow

See diagram [here][8]. 

##### Macros

Shortcut for series of repetitive actions. Customizable [here][18]. Current macros include: 
+ Payment failed: sets status to pending, assigns ticket to current user, populates body and subject with text that says his/her payment has failed.
+ Valuables reminder: sent to people who are late on uploading valuables verification. We already send a series of three automatic reminder emails, so sending this manually through Zendesk is a last ditch effort in special cases. 

##### Triggers

Automatic action that happens when certain conditions are met. Customizable [here][17]. For example: 
+ Agent comments publicly on a ticket &rarr; user is notified with a Jetty branded email. Text of the email depends on the context (i.e. whether ticket has been solved). 
+ Agent sets the status of a comment to 'solved' &rarr; user is not notified

##### Net Promoter Score

We currently use a homemade Google form to administer NPS surveys to a customer after an interaction with customer experience. A link to the form is included in the Zendesk email sent to the customer after the ticket has been marked 'solved'. 

The survey is [here][6]. 

`Note`: This is distinct from the general customer [survey][7], which also has a NPS question but is owned by Marketing and is sent to customers regardless of whether they've contacted customer experience. 

##### Batch Emails

I wrote a Python script that calls Zendesk's API to send batch tickets. I used it with the June NJ pricing change, which affected 26 customers and for each, required the creation of a ticket with dynamic variables populated with personal infomation, such as refund amount. 

It's non-engineer code quality, so might be useful as reference for another non-engineer.

Located [here][10]. 

### Help Center

Zendesk Help Center is where we manage 50 FAQ articles located on our site at [www.jetty.com/faq](www.jetty.com/faq). 

Source of truth: articles themselves.

`Reference`
+ [Help Center][15]


## Britecore

`Reference`

+ Jetty processes: [Google Doc][5] *(How do I change start date? Add coverage?)*
+ Britecore official support: [Britecore Support Docs][1]

## Intercom 

Intercom is our chat tool. We subcribe to their 'Respond' and 'Engage' modules. The 'Engage' module provides basic chat functionality, which is supplemented by the saved responses, keyboard shortcuts, and API access from 'Respond'. 'Respond' additionally offers a team inbox to process incoming mail-based requests, which we don't use because we've configured Zendesk (rules, templated emails, etc) for that purpose. 

## Metabase

Friendly [database viewer][20]. Can write queries in SQL or use their UI. 

## Others

### Calendly

Calendly is a scheduling tool used to schedule meetings with external contacts. Within CX, we're using it to test out phone support for customers. 

Tracking calls here: [Google Sheet][9]

### Glossary

Created around 40 definitions. Managed on [Wordpress][16] and hosted on [www.jetty.com/101/glossary](www.jetty.com/101/glossary)

### Facebook

Checking and responding to customer comments on our posts. 

### Fullstory

Watch user sessions. Powerful search you can use to find the session you're looking for: in the ideal case, when email is known, you can search by email address. Otherwise, you can narrow down the list with city, state, or actions (if you know they were on a certain page or clicked a certain button) and go through the remaining sessions. 

Some sessions/events are not recorded but Fullstory fills in most of the gaps. 

### Auth0
 
#### Login as User

Login as specified user
+ Find user
+ Press 'Sign in as user' and core-api management
+ Choose 'https://www.jetty.com/app/login' as Callback URL
+ Press open button next to client-side app (nothing happens if you click the one next to server-side app)

### Stripe

Used to: 
+ Refund payments - e.g. customer changes from annual to monthly plan, customer cancels
+ Get receipt of refund
+ Add card if unable to collect on app — foreign billing address or technical issues

### Important Files

+ [Policy List][2]: Google sheet of policy and customer properties - one row per policy. Our temporary customer database. 
+ [Software Stack][3]: Google sheet of current software used in customer experience processes (e.g. Zendesk, Intercom, etc.) and leads to diligence. Links out to helpful internal documentation for each tool. 

## Procedures

> Logging common issues

Try to come up with a naive solution to each issue, to help the brainstorming process. Format up to you. 

My issue log [here][12]. 

> If a customer reports a technical error - *page wont load, can't click button*

Notify the technical point of contact. Currently through the #tech_general slack channel. Use [Fullstory](#Fullstory) to get more information. 

> If a customer wants a policy change

1. *(Optional)* Email customer acknowledging receipt  
2. Make changes in Britecore. See [Britecore](#Britecore) section for how to change.
3. Regenerate Jetty branded declaration page
4. Email customer to confirm that it's finished

> If we launch in a new state

Update FAQ 'Where is Jetty Available' Zendesk article [here][11]. 

> If we're looking for new software

I documented the pro/con analysis behind our current software stack - could work as a reference. See [Software Stack][3] for links out to these docs. 

> Giving people quotes for additional coverage

1. Go on their policy on Britecore
2. Create new revision
3. In 'Builder' tab, change coverage amounts
4. Press 'Rate and Save' at bottom to see impact on price
5. Delete revision

## Perspective

### Agents
+ Transparent: better to overcommunicate - let customers know when they should expect to hear back. Open a channel of communication. 
+ Forward-thinking: expect the user to make errors or not fully understand the problem. Provide contextual next steps. 
+ Conversational

### Customers
+ Tend to be relatively unfamiliar with insurance than other consumer products. As a result, more likely to postpone or give up. 
+ Looking for reassurance since its a financial product.  

### Other stuff

+ [Service recovery paradox][13]: When a very positive service recovery causes a level of customer satisfaction greater than that expected if no service failure had happened.

## Language

+ Switch to customer-facing vocabulary: "Checkout flow", "conversion", and other company jargon may seem foreign and cold to customers


## Adding or changing processes

+ Evaluate ROI
	- Clear objective
	- Define how objectives will be measured
	- [Article][14] about measuring ROI



[1]: https://briteedu.squarespace.com/
[2]: https://docs.google.com/spreadsheets/d/19JcM5BfVaNECSbxniXlsXY9G8H523OoHGMdGzO58s4E/edit#gid=0
[3]: https://docs.google.com/spreadsheets/d/1HMdRz2aLdiYW2p3gyMOrNXM9f7nZJaN58dSP6pvdQBU/edit#gid=937495940
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
[14]: https://segment.com/blog/measuring-the-roi-of-support/#how-much-does-our-success-team-cost
[15]: https://jetty.zendesk.com/hc/en-us
[16]: https://www.jetty.com/blog/wp-admin/
[17]: https://jetty.zendesk.com/agent/admin/triggers
[18]: https://jetty.zendesk.com/agent/admin/macros
[20]: http://jetty-metabase.us-east-1.elasticbeanstalk.com/