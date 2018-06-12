# JIRAs

The JIRA should be used as a working history/progress tracker of your work. Basically summarizing what was done during the full SDLC.

## Description
The description field by now should be a full description of what the change was so anyone that reads it would have an idea of what was done and why.

It is also helpful to summarize before doing any development as to ensures you understand the problem/requirements and clarify/identify issues or gaps.

**Please see the attached emails IS NOT AN ACCEPTABLE Description**

## Comments and Work Log
Comments should be used to attach supplemental information such as followup discussions, reason why something was done or any issues that arose.

*It may also be useful to list the projects/packages changed/added*

## Attachments
All JIRAs for release should include:
1. Business approvals
2. Test evidence
3. Design artifacts like initial requirements and Visios

# Unit/Functional Tests
Testing requirements depend on the project/language and the specific change.

If you are testing during development, consider creating a reusable unit test. *This also affects the design and a key reason for Test Driven Development. By making all components testable from the start, it ensures modularity and loose coupling (it's inputs can be replaced with Mocks). There is some overhead as the the testing frameworks so the actual design is different for each language and thus a large context-switching cost.*

# Code Quality
1. Check Sonar and ensure there are no Major+ issues added. Minor issues should also be checked and fixed.

2. There should be no God functions (in general functions that span more than 1.5 screens in height, "doing 50 different things that can and should be refactored into smaller functions")

3. Variables should be well named and descriptive. I should not have to jump around and between methods and classes to figure out what something is for or doing (this is a big problem in JS/Python because there is no strong typing and `params` pretty much can include anything, *see JS Style Guidelines*).

4. Public methods should be documented using JSDocs, JavaDocs, etc. It makes it easier for others to reuse the code without having to reinvent the wheel or reverse engineer the function to ***maybe*** understand what it's doing.

	> Design for re-usability by making functions and classes easy-to-be picked up and re-used by others.

# Documentation
- Prefer in-code/in-script comments
- For system design, process flow, or "how-to use", create a Word document and/or Visio.
	
	We may create a `docs` folder in the project repos (easiest to change/update) but you can also create a Wiki and/or attach to the JIRA (hardest to update).

- The idea of documentation is to ensure that everyone is on the same page and not stepping on top of each other.

I generally like to keep documentation as close to the code as possible. *I think this is general idea of microservices and small apps. You store the documentation in the repo so can easily update it when the component changes. And other developers know exactly where they can find the information... unlike our Wiki (we have like 4 of them I think)*

## The benefits of documentation
1. Write it down while it's fresh so you don't forget important details later

2. Help you understand the problem better before you code (especially design diagrams)

3. Can give to someone else or even Support to read rather than having to explain to M people N times

4. Any team member can refer to it to debug issues even if they did not write the code. It reduces the time and amount of rework/effort needed

5. Reading/skimming a document is faster than watching a video (KTs take a lot of time and most of it can usually be replaced with a well written documents)
	
	> People will always prefer the easiest, least painful way of doing something. So if you want people to do something the right way, you need to make it easy for them to do.

	*This also applies to code quality... if there are no standards, they have no incentive to write clean code especially if they know they won't have to deal with the issues.*
