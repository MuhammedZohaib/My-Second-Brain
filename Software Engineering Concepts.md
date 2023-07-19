# Software Engineering Concepts
Most People Learn The coding part but they are not familiar with the software engineering concepts. This can work for small scale projects that we go out and start building but suppose we assume that our project is a bridge we just can go with workers and cement and start building, for building process to start there will be serveral months of planning and permits and other steps before the construction actually start, during the process of planning we consider the things like security of bridge, maintenance and cost , same goes for large organizational projects. The construction part is less important than the Engineering part.

## Important Points:

* A developer spends 3.8 hours per week on debugging bad code and 13.5 hours in technical debt (Poor implementation which causes issues later) which cost $85 billion dollars anually which can be used to build better quality softwares.
* 1 hour saved can cost 20+ hours later.
* 20% of projects fail due to poor development practices.
* ROIC -> Return on Investment
* Desiging is important because it can be expanded and collaborated on.
* If we give 0% upfront time to our project, then our cost overrun(**Time and Money both**) will go to 200% but if we give 10-20% of our time as upfront time the cost overrun will be brought to 40% and this cost overrun cannot be brought to zero. 30-40% cost overrun is normal for all projects unless the budget is very tight. 

 
## Software Development Life Cycle
There bunch of ways to develop a software and these ways are known as models. However below steps are crucial in all models and are important for developing any software.

1. Requirement (*What we are building?*)
2. Design (*How we are going to build it?*) **Important**
3. Implementation (*Start Building*)
4. Verification (*What we built, is it what we wanted?*) or (*Testing*) 
5. Maintenance (*Create a lifecycle plan, Fixing Bugs or Additional Little Features*)

1. Initiation
2. Requirement Gathering
3. Analysis
4. Design
5. Development
6. Testing
7. Deployment
8. Maintenance

## Phases of SDLC


# Requirement
`A way of  figuring out the exact specifications of what the software should do or A process for finding out the goals of the System.`
In this Step we focus on **What** and not on **How**. The Requirement Document Contains All the Project Documents.

***Golden Rule In Engineering*
"Spending time strategically upfront, reduces cost and time later on".

 **Requirements Vs Specifications**

Requirements is the non-technical definition of  something that user requires from the system and it is written in plain words so that even a non-technical person can understand. **No JARGON**
Requirements are further divided in two types:
1. Functional Requirements
2. Non-Functional Requirements

Specifications are basically technical specifications that needs to be done to meet requirements. Just keep it simple we are trying to design it here. We talk about basic constraints of the System. 

-> User Requirements (What user wants) **Client Requirements**
-> System Specification (What we want from the system) **Developer Notes**

## Requirements Gathering:
- In requirement gathering we focus on two main things what is needed and what is no need
- What is required is further divided into 
	- Functional Requirements
	- Non-Functional Requirements
* Constraints are limitations by the client which we must follow while building or solving software problems.
* Before gathering actuall requirements it's important to make assumption about the system, environment and real world.
- Business Requirements are gathered.
- Project Manager and Stake Holders are involved.
-  Meetings with managers, stake holders  and users are held in order to detemine the requirements like: 
	- Who is going to use system?
	- How they will use the system?
	- Data input of the system?
	- Data output of the system?
After Requirement gathering an analysis is carried out in which we separate wish and want and convert our requirements into a software specification document. Also the software development model is chosen here and the testing team take the software specification document to prepare for software testing and they follow software testing life cycle. 
Remeber the testing methods depend on software model which we choose for development.

## Models:
- WRSPM
- Waterfall Model
- V Model
- Incremental Development
- Rapid Application Development
- Agile
- Iterative Development
- Spiral Development
- Prototyping
- RAD


Models are basically different approaches to solve or design softwares.

### WRSPM Model:
This model is known as the world machine model. In this model we make a venn diagram to relate the system and the enviorment. The left side of when diagram is enviornment while the right side of the venn diagram is for the system we are desigining. The World and requirements are the part of the left side of the venn diagram. "*The enviornment creates a problem*".

**Points**:
* W stands for the world in it we make assumptions about the enviornment that what sort of environment we are building our software for example if we are making a software for an ATM so the assumption such as "ATM must be supplied electricity 24x7" indicates that the enviornment must have constant supply of electricity else we need to take measures. These types of assumption help us understand our software.
* R for Requirements are like conceptual idea "What are we building?". "What is it trying to accomplish?". 
* S for Specifications goes in the middle, the overlap of system and the enviornment. "Specifications are the defined details of the system." Includes Technical details about the system. Its basically an interface or connection between the system and enviornment.
* P stand for the Program. Its actually the code part of the software where we start solving the real problem. 
* M stands for the machine, It helps us understand what hardware the software is running on. We need to understand the machine on which our software will run. 
* There also sub-overlapping portions known as `eh` (Enviornment Hidden) ,`ev` (Envioenment Visible) and `sv`  (Software Visible) `sh` (Software Hidden). These are detailed things like these are parts of the environment which are visible and hidden like we have pin number in ATM but it's kept hidden. Enviornment visible are the aspects of the system that are visible to the enviornment. 
* If You are ever in doubt about gathering requirements then go around with a use case where you'll use that system. How you'll interact with that system. How would you want system to interact.

### Waterfall Model:
Waterfall model is most traditional and very old model. It is also known as `Linear Sequential Life cycle model`. In this model the testing only start once the development is completed due to which many failures and defects are reported at the end so the cost of fixing these issues are very high. 
In waterfall model each phase must be completed before the next phase begins.
This model is used where the project is small and there are no uncertain requirements. This model is simple and is easy to understand. Easy to manage due to high rigidity of model. Phases do not overlap one phase at a time. No working software is produced during the life cycle of the software development which means product is at the end of the life cycle. High amounts of risk and uncertainty.
Not preferred for complex and object oriented projects. Poor model for long-term projects.
This model is no longer used.

- Requirement Gathering
- System Design
- Implementation
- Testing 
- Deployment
- Maintenance

### V Model:
V model means Verification and Validation Model. 
`Verfication: Basic Functionality testing of the components`
`Validation: Compare results to the initial requirements.`
Each Phase shoulde be completed before the next phase begins. 

 ```
 - Developer Verification                       - Tester Validation
  - Business Requirement Specification        - Acceptance Testing
   - System Requirement Specification        - Sytem Testing Plan
    - High Level Design                     - System Integration Testing
     - Low Level Design                    - Component Testing
       - Coding                           - Unit Testing
                          - Code
```

On the right there are activites of Testers and on the left there are activites of Developers. Integration Testing is the ability of modulse to work together.
Simple and easy to use model. Testing is carried along with each phase of SDLC hence higher chances of success. Low chances of failures. Saves a lot of time. Defects are found at early stages. Useful for small projects.
Very rigid and less flexible. No early prototypes are produced. Since no prototypes are produced hence very high risk of not meeting customer expectations.
Use when requirements are clearly defined and project is small to medium sized.

### Incremental Model:
In incremental model whole requirement is divided into various builds. Multiple development cycle takes place in this model. Also known as `Multi-Waterfall Model`.
Our software is divided in smaller working modules and after one iteration a working module is formed and then the SDLC is repeated for the next model. We get a working software in early stages of software development. The previous working model add functions to the next module throughout the iterations. In this model we keep on adding completed pieces until the system is completed. More flexible model and costs less in case of change in scope and requirements.
Easier to test and debug. Lowers intial delivery cost. Risk management is easy to handle.
This model requires good planning and design. Needs clear and complete definition of the system.
This model is costly. 
Use this model when requirements are clearly defined. When quick product is required. When new technology is being used.

### RAD Model:
RAD stands for rapid application development model. Reduced development time. Increases reusability of components. Quick initial reviews occur. Encourages customer feedback. Integration from very beginning solves a lot of integration issues.
• Depends on strong team and individual performances for identifying business requirements  
• Only system that can be modularized can be built using RAD  
• Requires highly skilled developers/designers  
• High dependency on modelling skills  
• Inapplicable to cheaper projects as cost of modelling and automated code generation is very high

### Agile Model:
Agile model is also a type of incremental model. Software is developed in incremental, rapid cycles.
Results in small incremental releases where each release is built on previous release functionality. Each release is throughly tested and software quality is maintained. 
It is used for critical time applications. Extreme Programming is one of the famous SDLC in agile model.

- Kickoff
- Sprint Planning
- Development
- Test
- Demo
Recursive process back to Sprint Planning. 
Deployment is optional after on rapid cycle. Customer satisfaction due to rapid continous delivery of softwares. People and interactions are emphasized rather than process and tools. Working software is delivered frequently -on weekly basis.
Changes in requirements are also welcomed. Less emphasis on deisgn and documentation. Project can easily go off track if requirements are not clear enough. Only senior programmers are able to make decisions for development hence no place for newbie developers. Require less Planning to begin. 
We use agile model when new changes are to be implemented. 

### Iterative Model:
We begin with small piece of specifications and after one iteration a rough product is produced which is further refined after each iteration. Whole product is developed step by step.

- Design 
- Implemetation
- Analysis
Above steps represent one iteration. Defects can be tracked in early stages.We can effectively use customer feed back to improve our product. Less time is spent on documenting and more time is spent on designing. Each iteration is rigid with no overlaps. Can result in costly system or design issues. Requirements of the system are clearly defined and understood. Used for big projects.

### Spiral Model:
Similar to incremental model but more emphasis on risk analysis.

- Planning 
- Risk Analysis
- Engineering 
- Evaluation
Software continuously passes through these spirals. Good for large and critical projects. Strong approval and documentation. Changes can be made. Software is produced early. Costly model. Risk analysis require high expertise. Project's success is highly dependant on risk analysis phase. Doesn't work for small projects. 
When risk evaluation is imporatant. Long term projects. Users are unsure of their needs. Requirements are complex and not clear. for new products.

| Model            | Key Features                                                                                                                                                                                                                                               | Advantages                                                                                                                                    | Disadvantages                                                                                                                                                                                                          |
|-------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------|-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| WRSPM Model       | - Uses a venn diagram to relate the system and the environment.<br>- Assumptions about the environment and requirements.<br>- Specifications and program are defined in the middle.<br>- Considers machine and hidden aspects of the environment.                          | - Helps understand the software and its environment.<br>- Defines system details and specifications.<br>- Considers hidden aspects of the environment.                                                    | - Requires thorough understanding of the environment.<br>- Complex for gathering requirements.<br>- Dependency on use cases for requirement gathering.                                                                              |
| Waterfall Model   | - Linear sequential life cycle where testing occurs after development completion.<br>- Phases must be completed before the next phase begins.                                                                                                            | - Simple and easy to understand.<br>- Easy to manage.<br>- Suitable for small projects with well-defined and stable requirements.                 | - High cost for fixing issues at the end due to late testing.<br>- No working software until the end.<br>- High risk and uncertainty.<br>- Not suitable for projects with evolving or uncertain requirements.                     |
| V Model           | - Verification and Validation Model with a corresponding set of testing activities for each development phase.<br>- Phases must be completed before the corresponding testing phase can begin.                                                                 | - Testing is carried out with each phase, increasing the chances of success.<br>- Defects are found at early stages, reducing rework and cost.  | - Rigid and less flexible due to the strict sequence of phases.<br>- No early prototypes produced for feedback and validation.<br>- High risk of not meeting customer expectations if requirements are not clearly defined. |
| Incremental Model | - Divides requirements into builds or modules and delivers them incrementally.<br>- Multiple development cycles take place, each building upon the previous cycle.<br>- Offers flexibility and allows for changes in scope and requirements during each iteration. | - Early availability of working software modules.<br>- Easier testing and debugging of smaller modules.<br>- Cost savings in case of scope changes. | - Requires good planning and design upfront to define the modules.<br>- Coordination and integration challenges as the system evolves.<br>- Can be costly if the overall architecture is not well-designed.                   |
| RAD Model         | - Rapid application development with emphasis on iterative prototyping and early user feedback.<br>- Encourages active user involvement throughout the development process.<br>- Integration of components from the beginning to address integration issues early.        | - Reduced development time and faster time-to-market.<br>- Increased reusability of components.<br>- Customer satisfaction through early feedback. | - Dependency on highly skilled developers/designers for rapid prototyping.<br>- High cost of modeling and automated code generation.<br>- Limited applicability to projects with modest budgets.                              |
| Agile Model       | - Incremental and iterative approach with rapid cycles and continuous delivery of working software.<br>- Emphasizes collaboration, adaptability, and customer satisfaction through early and continuous involvement.<br>- Agile methodologies like Scrum and Kanban.    | - Customer satisfaction through continuous delivery of valuable software.<br>- Embraces changes in requirements and priorities.<br>- Early detection of issues through frequent testing and feedback.         | - Requires clear and well-defined requirements to manage iterations effectively.<br>- Less emphasis on design and documentation can result in technical debt.<br>- Lack of predictability in long-term planning and scheduling.                 |
| Iterative Model   | - Step-by-step development approach where a rough product is produced after each iteration.<br>- Each iteration involves design,implementation, and analysis stages.<br>- Allows for feedback and improvement through multiple iterations.                                  | - Defects can be tracked and addressed in early stages.<br>- Effective use of customer feedback for continuous improvement.<br>- More time spent on designing and refining the product.                 | - Costly if the system or design issues arise during iterations.<br>- Rigid iterations without overlaps may hinder flexibility and responsiveness.<br>- Requires a clear understanding of the requirements upfront.                   |
| Spiral Model      | - Iterative and risk-driven model that emphasizes risk analysis and mitigation throughout the development process.<br>- Continuous iteration through planning, risk analysis, engineering, and evaluation phases.                                                  | - Suitable for large and critical projects with complex risks and requirements.<br>- Early software production and integration of risk management.<br>- Allows for changes and mitigates potential risks. | - Costly due to the extensive risk analysis and evaluation phases.<br>- Requires expertise in risk analysis and management.<br>- Not suitable for small projects with limited resources or projects with well-defined requirements.     |

| SDLC Model       | Scenarios for Usage                                                                                                                                      |
|------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------|
| Waterfall Model  | - Projects with well-defined and stable requirements.<br>- Small projects with no uncertain requirements.<br>- Projects where the scope is unlikely to change.|
| V Model          | - Projects with clear and well-defined requirements.<br>- Projects where risk analysis and validation are critical.<br>- Small to medium-sized projects.  |
| Incremental Model| - Projects with evolving or uncertain requirements.<br>- Projects that require frequent iterations and feedback.<br>- Projects where early delivery is desired.|
| RAD Model        | - Projects with tight timeframes and rapid development requirements.<br>- Projects with a strong and skilled development team.<br>- Small to medium-sized projects.|
| Agile Model      | - Projects with dynamic and changing requirements.<br>- Projects that require continuous customer involvement and feedback.<br>- Projects where rapid and incremental delivery is important.|
| Iterative Model  | - Projects that can benefit from frequent feedback and continuous improvement.<br>- Projects where requirements are not fully known upfront.<br>- Projects with a clear understanding of the overall system architecture.|
| Spiral Model     | - Large and critical projects with complex risks and requirements.<br>- Projects where risk analysis and mitigation are paramount.<br>- Projects with long-term development and maintenance phases.|



It's important to note that the choice of SDLC model depends on various factors, such as project size, requirements clarity, development team expertise, project timeline, and customer involvement. The table above provides general guidance on the scenarios where each SDLC model is commonly used, but it's essential to evaluate the specific project context before selecting an appropriate model.
# Design:
Design : How to achieve what is needed?
All the software specifications are converted into Design Specifications. All Technical details are listed like what technologies to be used, project constraints and team capabilities.
Most important and difficult part in this stage is that the design should not have any vulnerabilities.
In this phase software design is prepared from requirement specifications.
System design help us decide system and hardware requirements which help us understand the overall software architecture. New changes can be implemented on very small cost.
In design phase system testers come up with strategies like what to test and how to test.





## Software Architecture:
The very top level design is know as Architecture and the Architect is the link between the idea and reality. Architecture is something that cannot be fixed once implemented. Good programming cannot fix bad architecture. Sometimes we have to scrap a project and start over again in software engineering. Architecture is very very important suppose we make an app later we notice that over server is insecure but the server is our core of application either we have to replace the whole application or abandon the software.

Software Architecture is all about breaking larger system into smaller focused systems.
- Good Architecture is hard.
- Maintainable software has good architecture.
- Architecture mistakes are almost impossible(cost more time and money) to fix once coding is started.
- Good architecture allows faster development and smarter task allocation.
- Allows companies to decide where to buy and where to build.
- Reduces overall idle time
- A good architecture avoids problems like merge conflicts.
- a software with good architecture is easy to debug.

If you don't focus on architecture you write something that's known as sphaggeti code. 

# Phases of Software Development
1. Requirement Gathering
2. Design
3. Implementation
4. Quality Assurance
5. Deployment


## Development Models:
Development models are also known as lifecycle models. We select the one specific model for software development depending on our desired objectives. The model we select also choose the methods which we used to test our software. 


### How to select the right Software Development Life Cycle Model
The right SDLC Model Depends on certain factors while making a software.
- Uncertainty :
	- Unclear Technologies: 
		- Waterfall : 0% chance
		- V Model :  0% chance
		- Prototyping: 50% chance
		- Spiral : 100% chance
		- Iterative and Incremental : 50% chance
		- Agile: 100% chance
	- Unclear Requirements
		- Waterfall : 0% chance
		- V Model :  0% chance
		- Prototyping: 100% chance
		- Spiral : 100% chance
		- Iterative and Incremental : 50% chance
		- Agile: 0% chance




