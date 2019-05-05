## Email sent when preparing for brainstorming for the next architecture

```
Hi all,

I hope you guys prepared some material before we attend the meeting tomorrow. In order to build something that works, we need to know what does not work for us.

Please ask yourself this questions:

- How does the current architecture looks like? Do we have a diagram (visibility) on all our current services?
- Is the current revision of the architecture known to all members? 
- What is the bottleneck of the current architecture?
- What is standard performance of our current architecture (email delivery rate, error rate, match rate)?
- How many times does this architecture fail (where, why)?
- What is the pain point when running this architecture?
- What is out testing standard?
- Is it easy to integrate A/B testing?
- Is it easy to revert changes/fix issues?
- Do we have visibility on failures?
- How do we handle failures?
- What are the technology stacks we are using?
- What technology stack we plan to use?
- What are the bad practices we have in our current architecture/what good practices do we have?
- What features we have and are they delivering the right value (how do we track em)?
- What insights do we get from our system? Is it transparent enough? Does it adds value?

Most important of all, what do we want our next architecture to be able to support?

Please come up with the answers by tomorrow. Prepare any diagrams, architecture suggestion and technology suggestions too.

Regards, 
Alex Tan Hong Pin
```


## Roles in development 

(I've written them quite a while ago on how to build a core tech team). 

During development, tasks segregation is very important to ensure the quality is well controlled. 
Do not let a person hold many roles at the same time - this will introduce a single point of failure. That is, that you might not be able to find a replacement for that person once he or she is gone. Instead, introduce role rotation. Assign the sifus to mentor those below him. That way, you always ensure that there will be someone who is able to handle the tasks for you at critical time (when someone take a leave).

There are a numbers of roles that can be hold by a single person. What characteristics do you want to have in the people that is working with you?

- Specialise in one field, but eager to learn other fields when required (need T-shape skills)
- Able to recognise the strength and weaknesses of the members
- Time management and planning is more important that just blindly carrying out the tasks
- Document oriented - able to voice out your thoughts are more important that keeping everything in your head
- Able to research and work on new solutions
- Understands what they are doing
- Able to test different scenarios and cater them
- Able to provide feedbacks as they work
- able to justify on the course of actions taken
- able to complement other members capabilities 


Hierachy
- Functional/requirement team
- Business analysts
- Scrum masters
- Stakeholders
- Business/marketing
- Frontend team
- Backend team
- UI team
- UX team
- QA team
- Big data team
- Testing team
- Public users
- Legal team
- Multilingual team

### Functional/requirement team

- should communicate with stakeholders regarding the business requirements
- should document the requirements to a friendly format
- should evaluate the complexity of the requirements

There are a few approaches for planning requirements. His include Agile Stories planning, in which features re divided into epics.

Another is using a domain specific language called Gherkins and the framework Cucumber.
What you didn't know about requirements. The products are progressive - they will keep upgrading. If your product has a limited lifespan, then just do a one shot, else it will keep improving over time through continuous feedback cycles. 

(updated) After reading on UML and writing use cases, I've concluded that anyone can find/tinker with the requirements. Gathering requirements is an end-to-end process - whenever there are changes, teams must be able to move fast and deliver it, not resist against it. One thing to avoid when gathering requirements are distractions - I tend to want to draw those fancy uml use case diagrams to (assumably improve understanding on the thought process/flows), but I was wrong. It is time-consuming to come up with such diagram (not to mention updating them when requirements changed) when the text-based equivalance provide just the same amount of information.


### Business Analysts
- analyse the business prospects that the products can deliver
- Monetising the product

### Scrum Masters
- should conduct daily stand-ups
- should only communicate with matters regarding the progress
- should rotate scrum masters so each of them will have experience handling the tasks at hand
- Note down the task at hand of each members 

### Stakeholders
- communicate businesss ideas
- see the 6 thinking hats

### Business/marketing
- should seek the value of the application

### Frontend team
- Architecture design
- Technology stack
- Carry out task based on requirements
- Report issues faced 

### Backend team
- Define and justify the technology stack
- Design the database schema
- Design API services
- Cleaning dirty data and patching data
- API testing for different platforms
- Business requirements 
- Validations

### UI/UX Team
- should do research on user testing
- should carry out user testing
- should validate the behaviours of the page/components
- should study the behaviour of the app/page/components
- designing the ui for each page
- create reusable patten libraries
- assets management
- ui flow
- animations and component interactions
- user research


### QA 
the QA will deak with the unit testing and quality (check the real role of qas)

For this amount of time, there are a few things that we have to consider:

(Success Rate? it this the best practices?)
What these storypoints doesn't cover is the time required for Unit Testing and also time for the UI design to be completed. It does however cover the time for Backend to provide services.

The sprint works in a way that the scope for this sprint task will be completed by the designer and backend team. 
Difficulty that arise:
- When the backend or designer UI does not completely fit the requirement, but the task is handed to us.
- Changes to services are required as we carry out the task in the sprint (CR: Change Request requires extra storypoints, developers should not include it in the planned sprint time).
-Change in ui requirement (Addition of logic to the UI due to unforeseen requirement/issues that exist with the existing UI)

Most of this issues are encountered during developement, which could be time consuming. Developers are expected to deliver the confirmed requirement so that they can meet their deadline.
Any change in the UI or Services should require extra storypoints and have to be informed to the Team Lead.

To trace this issue early, developers have to go through the UI, requirement, and services before carrying out the task. Developers in the team should be willing to raise questions and challenge the requirements to see if they received everything before even starting with the developement.  

Once everything is confirmed, the developer will start with the task on hand. 

## Issues with dependencies
It's best to split the task a according to the strength of individuals, and at the same time do not introduce a single point of failure. A single point of failure is defined by having a single person working on a specific task which does not have replacement. It is best to have other individuals to look into that matter too, by introducing task rotation. 


### Architecture of the best team

Problems faced
- There is no single authority to decide on something. It's always a do and try first
- No single person deciding on the architecture - 
- Unplanned things are not catered. Only cater for the present.
- Everyone's opinion should be considered
- Do not introduce a single point of failure
- Flattened orgranization
- Kanban 
- Present research (or deliver fast)
- Keep things dynamic - simple and dynamic until everything is defined
- Story should be handpicked
- Ignore dateline 
- transparency
- UI/UX  
- pair programming to improve skill
- there's no documentation
- UI, UX, Backend, Requirement, QA
- Create a simple prototype
- Always refer back to the appropriate person


Problem: No single source of truth.

It’s hard to carry out tasks when things are not documented. Good documentations are short and concise, and helpful for everyone. Team lead can continuously update the requirements, QAs can add in missing scenarios during testing, developers have a clear understanding of the difficulty of the task present and are able to give a better estimation, and UI/UX should have a standardised design guideline. 

As we develop, this documentation will serve as a live documentation. Mistakes that we have done should be engraved in the documentation too, so that we won’t repeat it. 

BA: Business requirements 
QA: Testing scenarios 
Frontend: Platform specific handling, best practices, architecture, methodologies
Backend: REST API documentation, error messages
UI: Pattern Library, color scheme
UX: Microinteractions
IA: Structure and hierarchy of the content
Multilingual: Language documentation

Problem: Slow decision making processes.

A lot of time is spent discussing issues that could be fixed either through minor modifications on the UI or UX, or flow, which normally ends up without conclusion. The issues are not fixed and appears over and over again in production. E.g. No email for users that registered on Facebook with their mobile phone.

Ego can hurt the development process badly. When the people working on the product takes criticism personally, it's hard to move forward.

Problem: Too many dependencies in Waterfall-like process.


Problem: Introducing technical debts
What happens when there are issues that needs to be fixed immediately but requires time and consideration to design a solution? The easy way is to just go with the fastest solution (normally hardcoded), which introduces technical debt. And what happens next? A total redo which then takes developer’s time when they need to work on a new feature. 

Problem: Product, design and engineering

Functional team, UI/UX team, developers and QA should sit side by side, and work to achieve harmony. What is harmony? For me, there should be a give-and-take between the functionality, the user experience and the enabling techology. Once the team understand this, then you have an A-Team. How does a B-Team works? They sit in their respective functional areas, and ask others make requests for their services in the form of documents and scheduling meetings. 

Lack of Prototypes
Development team should be allowed to try the discovery prototypes from UI/UX team so that they can contribute their thoughts on how to make the product better. A bad team will only show their finalised prototypes during sprint planning so they can estimate. The price for making any changes in the UI/UX is a lot once the development process begins.

the need for speed: Everyone understands the need to be efficient, to be able to release the product on time, and this speed comes from the right technique and not forced labor. Poor team complains they are slow because their colleague are not working hard enough.
redo instead of learning: This is your concern. From our side, we always question ‘Is it necessary to redo the entire thing?’ Do we really understood the problem well enough to create a better solution, or are we just changing skin to cover other flaws? If the problem is not well understood, there’s no point of investing time doing a makeover. The right mindset is, what have we learnt from our past mistakes that we can utilise to make a better product? 
unable to accept criticism - do note that I always provoke (not criticise) others, not because I enjoy doing so, but it’s because I see the potential in them and the need to bring them out of their comfort zone. It’s easy to get comfortable with the position we have and deliver a just-good-enough work that no one cares about. It’s important that the people I work with grow and develop over time. I’m not gonna apologise for making them better.
Start with code. When designing a requirement, it's bad to assume it will be the final product that the team expected. Things will change, and the cost to change it during the development process is high. Plan things well and create fast prototypes and avoid coding early. Your development team can help in the process, but should not start coding.
Lack of transparency. Not aware of current task, difficulty present and other matters related to development and requirements. Most people only wants to hear what he wants to hear.

Problem: Problems are not taken seriously
Issue with UI and UX, there are a lot of complaints from Development team that is not taken seriously. Dev&QA team have reported a lot of missing dependencies, weird UX, which will definitely be raised when it is out. But the PM fail to realise the issues. Next time means never.


Problem: Slow deployment
This can be a huge issue, especially when aiming for faster releases. A slow release will hold up lots of items, and a lot of time to retest. Aim for quicker, smaller releases with steady improvements.

Problem: Focusing too much on new features rather than fixing old dependencies can be an issue too.
Problem: Not understanding the need for the feature being developed.
Is the feature useful? Are we building the product right and doing it the right way?

Ego is holding back developemnt. The need to release everything perfect can backfire, because of the assumption that the thing we develop is perfect and exactly what the users want. Instead the right approach is to learn from feedbacks, mistakes and observation.


Agile Meetup 20160727

- conway's law, definition, examples
- group people by product lines
- Spotify model (?), flaws ?
- group people by function
- sprint formation, squad design its sprint by formation (4-3-2, 6-2-2)
- Single piece flow
- Sprint - how does it apply to people with different experience/background ?
- Is testing part of the sprint?
- Who handles the documentation?
- Who handles testing? Developers or QA?
- Estimation 
- Strategic items or collections are grouped into epics
- Managing angry people (lol) in sprint
- Single point of failure? Availability 
- Velocity optimisation through decomposition or WIP reduction 
- Built to forecast - built to orders (btf or bto)
- ask yourself - does this make sense?


## Documentation

Project Manager/Stakeholders: Should include all the requirements/features to be worked on
QA: Should include testing scenarios for specific devices/browsers/platforms etc
UI: Should include Pattern Libarary and Design Guideline
UX: Should include microinteractions and the why 
Frontend: Should include technical details on how the solution will be designed
Backend: Shold include the technical implementation, REST api documentation, error messages etc

Documentation should be short and concise. It should also be constantly updated with the update date recorded. There are several questions that can be asked in the making of the documentation.

- What documentation can be created?
- What is the connection between different documentation


This documentation will serve as the following: 

- Reference for future users
- Problems faces, and potential solutions
- Mistakes learnt, and how to avoid it
- Best practices for the team
- Avoid redoes through documented work
- Black and white agreement on what has been decided
- Served as a single source of truth


## Other problems encountered

- mvp first: the idea of building a minimum viable product often leads to software designs that doesn't work. most of the time, this narrow point of view will lead to design with flaws when it's time to scale. This is especially true when working with a RDBMS, since the schema design is hard to change, and without sufficient knowledge in data migration, this can quickly develop into a legacy. The worst thing I've seen is the design of the db is tightly coupled to the Frontend, since the logic for storing the dynamic forms and translation lies in the db. MVP works, but it doesn't need to leak out to the software side - we can for example send out surveys and get feedback from the open first whether or not the product makes sense. If it does need to be develop, care is needed when designing the schema. Better be safe than sorry! (redoing will take more toll and wasted development time when what you want is to develop more features)
- because team lead (put the person's name) says so: this is one of the worst thing that I could have heard when working in a team. Just because someone says so, doesn't mean you have to do it. If the person tells you to jump down a 30 storey building, would you do so? Aha, and now suddenly you have the brain to think about it. Good teams are proactively looking for solutions to the problems they face, and not just solutions that work, but one that can stand against the test of time. If the team is only looking for a quick gain, they are bound to suffer huge losses in the future.
