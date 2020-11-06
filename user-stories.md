# Use Cases, Stories, Problem Frames, Specifications by Example
Différentes stratégies peuvent être utilisées pour définir des requirements. 



## (Agile) Functional Decomposition (Divide and Conquer)

-> Breaks things down into hierarchy


1. Epics
2. User Stories
3. Tasks



![](https://scrumandkanban.co.uk/wp-content/uploads/2014/01/Theme-Epic-Story-Task.jpg)


[https://scrumandkanban.co.uk/wp-content/uploads/2014/01/Theme-Epic-Story-Task.jpg](https://scrumandkanban.co.uk/wp-content/uploads/2014/01/Theme-Epic-Story-Task.jpg)

**Epic**

An epic is a large story that cannot be simply achieved in a single sprint. Usually, it takes months to accomplish an epic. It typically refers to a set of requirements that have not been rationalised into user stories yet. Think of it as a big goal that is yet to be simplified and divided into several tasks for your agile team to work on them.
[Epics](https://www.linkedin.com/pulse/agile-theme-epic-user-story-tasks-krishnaji-singh) are usually broad in scope, lacking in details, and are meant to be split into multiple, smaller stories before they can be worked on. Epic is usually regarded as the ‘top tier’ or a work hierarchy. Breaking it down into daily tasks, called ‘user stories’, helps an organisation achieve its overall business goals.
[Important guidelines when creating an epic](https://www.atlassian.com/agile/project-management/epics):

- Create epics that managers and executes would want to track.
- An epic could be a product feature, customer request or business requirement.
- Let your organisational culture dictate the size of your epic.
- Epics should not take too short or too long to complete.
- Burndown charts can be used to measure epics and give an actual and estimated amount of work to be done.

Examples of Epics:

- As a bank, we want to extend our services by offering life and health insurances.
- We want to add a biometric recognition to increase security without hassle.
- As the marketing department, we want to create an interactive app to cater to more customers.


![](https://www.scaledagileframework.com/wp-content/uploads/2019/09/Epics_F02_web.png)


[https://www.scaledagileframework.com/wp-content/uploads/2019/09/Epics_F02_web.png](https://www.scaledagileframework.com/wp-content/uploads/2019/09/Epics_F02_web.png)

**User Story**

The [User Story](http://www.agilemodeling.com/artifacts/userStory.htm) is simply the list of items that need to be done within a project. Think of it as a to-do list. This is owned by the Scrum Product Owner. The Scrum master, stakeholders and the scrum team contribute to the completion of the backlog items. The idea is to break down a product into shippable pieces so that the large project can be done successfully. Epics can involve [multiple teams and multiple projects](https://www.atlassian.com/agile/project-management/epics), and can be tracked on multiple boards.
A user story is very high-level definition of the project requirements. It contains just enough information to give the Scrum team proper context as to what the final product should be like, and for them to calculate an estimation for the completion. It is an agile approach that helps shift the focus from writing to talking about them.
Important guidelines when writing a user story:

- User stories are short, simple descriptions written throughout the agile project.
- Although it is owned by the PO, anyone can write the user story.
- It is expressed in plain language so the customer can understand what the final product is all about (in case of software, what it should accomplish).
- It answers the ‘who’, ‘what’ and ‘why’ of a project in a simple language.
- User stories are regarded as the “heart of Scrum” because they serve as the ‘building blocks’ of the sprint.

[Template for writing a user story](https://www.mountaingoatsoftware.com/agile/user-stories):
As a < type of user >, I want < some goal > so that < some reason >.
Examples of User Stories

- As a user, I want to migrate all my data backup in a cloud system to free up my device.
- As a student, I can order official transcripts online to save time.
- As a consumer, I want to shop grocery items from a mobile app so that I could skip the lines in the store.
![yodiz-agile-corner-user-story-card](https://yodiz.com/help/wp-content/uploads/2013/06/yodiz-agile-corner-user-story-card.jpg)

- User Story — https://www.martinfowler.com/bliki/UserStory.html
    -  [INVEST mnemonic](http://xp123.com/articles/invest-in-good-stories-and-smart-tasks/) to describe the characteristics of good stories:
        - **Independent**: the stories can be delivered in any order
        - **Negotiable**: the details of what's in the story are co-created by the programmers and customer during development.
        - **Valuable**: the functionality is seen as valuable by the customers or users of the software.
        - **Estimable**: the programmers can come up with a reasonable estimate for building the story
        - **Small**: stories should be built in a small amount of time, usually a matter of person-days. Certainly you should be able to build several stories within one iteration.
        - **Testable**: you should be able to write tests to verify the software for this story works correctly.
    - Conversational Stories — https://www.martinfowler.com/bliki/ConversationalStories.html and not Decreed Stories — https://www.martinfowler.com/bliki/DecreedStories.html




**Task Scenario**
Below each epic is a more detailed set of user stories. And for those stories to turn into workable components, the Scrum team has to identify and sort tasks.
[Scrum tasks](https://docs.servicenow.com/bundle/geneva-it-business-management/page/product/sdlc-scrum/concept/c_ScrumTasks.html) are detailed pieces of work that are necessary to complete a story. Tasks can range from a few hours to several hours (usually up to 12) and are assigned to team members who have the skills or expertise to do them. Take note that a story is not considered complete until all tasks under it are done.

User stories come with acceptance criteria, 

**Acceptance Criteria** 


![](https://image.slidesharecdn.com/pmi-acp-2014-3d-rick-150227144457-conversion-gate01/95/pmiacp-training-deck-72-638.jpg?cb=1425048424)


[https://image.slidesharecdn.com/pmi-acp-2014-3d-rick-150227144457-conversion-gate01/95/pmiacp-training-deck-72-638.jpg?cb=1425048424](https://image.slidesharecdn.com/pmi-acp-2014-3d-rick-150227144457-conversion-gate01/95/pmiacp-training-deck-72-638.jpg?cb=1425048424)

They can be expressed as automated tests with a Given-When-Then formula:


- (Given) some context
- (When) some action is carried out
- (Then) a particular set of observable consequences should obtain

An example:


- Given my bank account is in credit, and I made no withdrawals recently,
- When I attempt to withdraw an amount less than my card’s limit,
- Then the withdrawal should complete without errors or warnings

Tools such as JBehave, RSpec or Cucumber encourage use of this template, though it can also be used purely as a heuristic irrespective of any tool.



![](https://miro.medium.com/max/1750/1*BXGeqp4bP0yfUYXpNztDxg.png)


[https://miro.medium.com/max/1750/1*BXGeqp4bP0yfUYXpNztDxg.png](https://miro.medium.com/max/1750/1*BXGeqp4bP0yfUYXpNztDxg.png)



![image](http://gwb.blob.core.windows.net/liekhus/Windows-Live-Writer/Behavior-Driven-Development-BDD-and-DevE_12CB4/image_thumb_2.png)




**Useful References**
Specification by example — https://martinfowler.com/bliki/SpecificationByExample.html
UseCase model: writing requirements in context — https://www2.cs.duke.edu/courses/cps108/spring04/readings/usecaseslarman.pdf



## Problem Frames

Problem Frames - Michael Jackson

- Information
- Transformation
- Workpiece
- Control
- Connection

**Information Problems**

- answers queries about a contained part of the real world
- -> Requestors / Real world.

**Transformation Problems**

- input -> output via transformation rules

**Workpiece Problems**

- Software as a tool for creating objects that exist only within the software (as little is used to create wooden workpiece)

**Control Problems**

- Software responsible for ensuring that part of the world behaves in accordance of specified rules (agents making decisions via sensors and update effectors)
- Access rules -> Monitoring

**Connection Problems**

- Connection between domains that do not really share phenomena

**Combining Problem Frames**


- Total problem as a a set of smaller problems that overlap slightly - sharing only one or a few domains - is your most important weapon against overwhelming complexity in a requirement document.

**Useful References**

- Composing Requirements Using Problem Frames https://citeseerx.ist.psu.edu/viewdoc/download?doi=10.1.1.1.6490&rep=rep1&type=pdf
- A Tutorial on Software Development Problem Frames Part 1 https://www.ifi.uzh.ch/dam/jcr:ffffffff-fd5f-cdf8-0000-0000107bd6fb/Jackson2006.pdf


## Non functional requirements

Non-functional requirements should often be considered “constraints” on a system. They can include:

- Performance 
- Quality
- Accuracy
- Portability
- Reusability 
- Maintainability 
- Interoperability 
- Capacity 



## Roles

**Product Owner => Adrien**

![](https://www.yodiz.com/blog/wp-content/uploads/2018/05/agile-product-owner-guide-by-yodiz.jpg)


[https://www.yodiz.com/blog/wp-content/uploads/2018/05/agile-product-owner-guide-by-yodiz.jpg](https://www.yodiz.com/blog/wp-content/uploads/2018/05/agile-product-owner-guide-by-yodiz.jpg)


## 



## Iterative Process


![Features, stories & tasks – iceScrum](https://www.icescrum.com/wp-content/uploads/2017/10/just-story-workflow-825x302.png)



Sprint goals: 

**SMART**

- Specific, 
- Measurable, 
- Achievable, 
- Relevant 
- Time-bound. 

**Task Board**

Tasks are placed on a Task Board for easy tracking. Generally, the Task Board is composed of the following categories:

- Not started – the tasks that are yet to be worked on.
- In progress – tasks that the Scrum team are doing.
- Done – tasks that are completed.


![](https://www.infodiagram.com/diagram_images/kanban_outline/z/1/8-columns-Kanban-board.png)


[https://www.infodiagram.com/diagram_images/kanban_outline/z/1/8-columns-Kanban-board.png](https://www.infodiagram.com/diagram_images/kanban_outline/z/1/8-columns-Kanban-board.png)


![](https://i.pinimg.com/564x/10/24/f9/1024f904cc16320bb45d70318d7b9334.jpg)


[https://i.pinimg.com/564x/10/24/f9/1024f904cc16320bb45d70318d7b9334.jpg](https://i.pinimg.com/564x/10/24/f9/1024f904cc16320bb45d70318d7b9334.jpg)




## Pour référence, concepts souvent mentionnés. 

(pas nécessaire de lire ces liens)

- Domain-Driven Design — https://martinfowler.com/tags/domain%20driven%20design.html
- Bounded Context — https://www.martinfowler.com/bliki/BoundedContext.html
- Yagni (You are not gonna need it)  — https://www.martinfowler.com/bliki/Yagni.html

