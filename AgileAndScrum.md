# Agile

## Agile Process
Time boxed, iterative approach to software dev, to deliver the product incrementally, instead of all at once.

Software is a combination of features (functionalities)

### Phases
Plan -> Implement -> Test -> Review

Functionality 1 - Plan - Implement - Test - Review
Functionality 2 - Plan - Implement - Test - Review
Functionality 3 - Plan - Implement - Test - Review

If the Review is satisfactory we add it to the Build (code base), if not restart the phase for the Feature.

## Agile Terminologies

### Epic
High Level overview
What are we trying to achieve?

### Story
Non technical.
What is required to achieve the Epic?

### Task
Technical.
Tasks required to fulfill those requirements (Story).

## Scrum Roles

### Product Owner
Epic
- Understands the requirements of the customer
- Great vision for the final product
- Balances the need of the other stakeholder
- Maintains the product backlog
- Release management

### Scrum Master
Story
- Responsible for "gluing" everything together
- Sometimes act as an intermediatory between the product owner and dev team
- Helps in planning and breaking down work
- Manages backlog, ensures completion
- Ensures transparency

### Scrum Team
Task
- Consits of Software Developers and Quality assurance
- Break down the work into subtaks
- Deal with planning, implementation, testing and preliminary reviewing of goals
- Esure timely delivery, with Quality Assurance
- Communicate their progress with the Scrum Master

### Example

Product owner talks to client and creates backlog, Epic: As a customer, I want to able to pay for my orders through online wallets.

Scrum Master teaches and ensures Scrum practices to the Team, 

Scrum Team learns and maintains Scrum practices, breaks Epic down with the Master to stories: Story, derived from Product owner's Epic: As a customer I want to be able to pay with PayPal.
After the Epic has been broken down to Stories, Scrum team breaks Stories down to Taks: #1 Add "pay trough online wallet" option, #2 Integrate with PayPal API.

## Sprint activities
Columns of the Scrum board:
Stories - To Do - In Progress - Testing - Done

> A sprint takes 1-4 weeks
> Daily 15 minutes of Scrum meeting to discuss present day goals and previus day's work

### To Do 
Not yet started tasks

### In Progress
Tasks that are currently being worked on

### Testing
Feature that is being currently testing

### Done
Completed tasks.

## Scrum ceremonies

### Sprint planning
Happens before a sprint starts.
Takes 1-2 hours, for a one- or two-week sprint.

During the sprint planning session, the team consults the backlog, which is a list of all desired features and bug fixes that the team can select from as they determine what to accomplish during the sprint.

### Daily stand up
Happens daily.
Takes 15 minutes.

These stand-up meetings are informal gatherings designed to help identify any roadblocks and allow team members to describe their current tasks, goals, and obstacles.

### Sprint review
Happens at the end of the sprint.
Takes who knows how long.

The Scrum team, Scrum Master, and product owner meet with other teams, managers, and executives to showcase what they accomplished during the sprint.
The sprint review should last as long as necessary to fully demonstrate the team’s new technology and have a productive conversation with stakeholders. After the sprint review, Scrum teams move on to the sprint retrospective.

### Sprint retrospective
Happens after sprint Review.
Takes who knows how long.

Using feedback from stakeholders and the Scrum Master, the team should identify how it can improve its processes to have more effective sprints in the future. Agility and adaptability are core values of the Scrum process, so teams should strive to identify potential improvements without blame or judgment.

## Definition of Done
DoD consists of 3 main components:
- Business or Functional requirements
- Quality
- Non-Functional Requirements

### Functional requirements
This is the standard business requirement that is assumed to carry value in the Product as functionality and this can also be written in the form of User Stories and it carries acceptance criteria as well.

- Should authenticate user
- Should be able to search for flight
- Should be able to pay with PayPal
- Confirm payment
- Add miles/kilometers to passanger profile

### Quality requirements
Quality is largely aligned to the coding language/Rapid Application Development (RAD)/technical tools to build the Product. Quality is owned by the Development team to ensure that the product is of the maximum quality. These quality standards can be subjective, and also data-driven.

- Unit Test Coverage
- Maintainability Index
- Technical Debt
- Design Principles

### Non-Functional requirements
These are the standard characteristics or attributes of the Product that might not add direct business value but without which your Product can’t move. These quality assurance attributes of the Product can be considered under the quality component too.

- Availability
- Maintainability
- Performance
- Reliability
- Scalability
- Security
- Usability
- Compliance/Regulatory
- Legal