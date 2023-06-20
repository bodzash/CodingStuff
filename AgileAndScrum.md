# Agile

## Agile Process
Time boxed, iterative approach to software dev, to deliver the product incrementally, instead of all at once.

Software is a combination of features (functionalities)

### Phases
Plan -> Implement -> Test -> Review

Functionality 1 -> Plan -> Implement -> Test -> Review
Functionality 2 -> Plan -> Implement -> Test -> Review
Functionality 3 -> Plan -> Implement -> Test -> Review

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

                  -> Story -> Task
Epic -> Feature <           -> Task
                  -> Story <
                            -> Task

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