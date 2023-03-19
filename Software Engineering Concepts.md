# Software Engineering Concepts
Most People Learn The coding part but they are not familiar with the software engineering concepts. This can work for small scale projects that we go out and start building but suppose we assume that our project is a bridge we just can go with workers and cement and start building, for building process to start there will be serveral months of planning and permits and other steps before the construction actually start, during the process of planning we consider the things like security of bridge, maintenance and cost , same goes for large organizational projects. The construction part is less important than the Engineering part.

## Important Points:

* A developer spends 3.8 hours per week on debugging bad code and 13.5 hours in technical debt (Poor implementation which causes issues later) which cost $85 billion dollars anually which can be used to build better quality softwares.
* 1 hour saved can cost 20+ hours later.
* 20% of projects fail due to poor development practices.
* ROIC -> Return on Investment
* Desiging is important because it can be expanded and collaborated on.
* If we give 0% upfront time to our project, then our cost overrun(**Time and Money both**) will go to 200% but if we give 10-20% of our time as upfornt time the cost overrun will be brought to 40% and this cost overrun cannot be brought to zero. 30-40% cost overrun is normal for all projects unless the budget is very tight. 

 
## Software Development LifeCycle
There bunch of ways to develop a softwares and these ways are known as models. However below steps are cucial in all models and are important for developing any software.

1. Requirement (*What we are building?*)
2. Design (*How we are going to build it?*) **Important**
3. Implementation (*Start Building*)
4. Verification (*What we built, is it what we wanted?*) or (*Testing*) 
5. Maintenance (*Create a lifecycle plan, Fixing Bugs or Additional Little Features*)

### Requiremnts
`A way of  figuring out the exact specifications of what the software should do or A process for finding out the goals of the System.`
In this Step we focus on **What** and not on **How**. The Requirment Document Contains All the Project Documents.

***Golden Rule In Engineering*
"Spending time startegically upfront, reduces cost and time later on".

#### Requirements Vs Specifications

Requirements is the non-technical defination of  something that user requires from the system and it is written in plain words so that even a non-technical person can understand. **No JARGON**
Requirements are further divided in two types:
1. Functional Requirements
2. Non-Functional Requirements

Specifications are basically technical specifications that needs to be done to meet requirements. Just keep it simple we are trying to design it here. We talk about basic constraints of the System. 

-> User Requirements (What user wants) **Client Requirements**
-> System Specification (What we want from the system) **Developer Notes**
# Requirements Gathering
* Constraints are limitations by the client which we must follow while building or solving software problems.
* Before gathering actuall requirements it's important to make assumption about the system, environment and real world.


# Models:
Models are basically different approaches to solve or design softwares.
# WRSPM Model:
This model is known as the world machine model. In this model we make a venn diagram to relate the system and the enviorment. The left side of when diagram is enviornment while the right side of the venn diagram is for the system we are desigining. The World and requirements are the part of the left side of the venn diagram. "*The enviornment creates a problem*"
## Points:
* W stands for the world in it we make assumptions about the enviornment that what sort of environment we are building our software for example if we are making a software for an ATM so the assumption such as "ATM must be supplied electricity 24x7" indicates that the enviornment must have constant supply of electricity else we need to take measures. These types of assumption help us understand our software.
* R for Requirements are like conceptual idea "What are we building?". "What is it trying to accomplish?". 
* S for Specifications goes in the middle, the overlap of system and the enviornment. "Specifications are the defined details of the system." Includes Technical details about the system. Its basically an interface or connection between the system and enviornment.
* P stand for the Program. Its actually the code part of the software where we start solving the real problem. 
* M stands for the machine, It helps us understand what hardware the software is running on. We need to understand the machine on which our software will run. 
* There also sub-overlapping portions known as `eh` (Enviornment Hidden) ,`ev` (Envioenment Visible) and `sv`  (Software Visible) `sh` (Software Hidden). These are detailed things like these are parts of the environment which are visible and hidden like we have pin number in ATM but it's kept hidden. Enviornment visible are the aspects of the system that are visible to the enviornment. 
* If You are ever in doubt about gathering requirements then go around with a use case where you'll use that system. How you'll interact with that system. How would you want system to interact.


